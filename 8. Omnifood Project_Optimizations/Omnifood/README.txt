1. Introduction to Javascript
   Javascript - Programming language of the web

   <!-- To link javascript file with the html -->
   <script defer src="js/script.js"></script>

   We can select elements from our html page just like we can select them in CSS. So, basically using the exact same selectors just as we write them in CSS. To do that, we write document.querySelector() in case we only have one element, and then here we can define a string. Then, we can make use of class selector to select the element.

   const h1 = document.querySelector(".heading-primary");  // This selects the h1 element in our project
   console.log(h1);

   We have selected the element. We can also change the content of the element using Javascript.
   h1.textContent = "Your compressors works just fine with us!";

   We can also manipulate the CSS. The property name should be given in camelcase.
   h1.style.backgroundColor = "red";
   h1.style.padding = "5rem";

   Lets make it so that the above styles get applied once we actually click on the h1 heading. Thats kind of a simple dynamic effect. In javascript, we can respond to an event like a click by basically listening for that event on a certain element. In this case, we want something to happen when we click on the h1 heading and so we can listen for the click event on the h1.

   h1.addEventListener("click", function () {
    h1.textContent = "Your compressors works just fine with us!";
    h1.style.backgroundColor = "red";
    h1.style.padding = "5rem";
   });

   Making use of Javascript in our project
   ---------------------------------------
   Updating the current year in the footer:
   <p class="copyright">
            Copyright &copy; <span class="year">&nbsp;</span> by Omnifood, Inc.
            All rights reserved
   </p>

   /* Updating the current year in the footer */
   const yearEl = document.querySelector(".year");
   const currentYear = new Date().getFullYear();
   yearEl.textContent = currentYear;


2. Making the Mobile Navigation Work
   We need to select the relevant elements from html in the Javascript. We need the button to listen for the click event and also the header element because that is where we are going to add and remove the "nav-open" class.

   Steps: We will listen for the click event on the button. And we write a function which gets executed when we click on the button. When we click the button, we need to add and remove the class on the header element. ie. If the nav-open class is already present we need to remove it, and if not we need to add it.

   const btnNavEl = document.querySelector(".btn-mobile-nav");
   const headerEl = document.querySelector(".header");

   btnNavEl.addEventListener("click", function () {
   headerEl.classList.toggle("nav-open");
   });

   Also, we observed that the close-icon on the navigation is not present on the white overlay by observing the focus state. What we can do is we can make the close icon appear above the white overlay by providing higher z-index.

   .btn-mobile-nav {
    display: block;
    z-index: 9999;
   }


3. Implementing Smooth Scrolling
   How to make the links lead to different section of the page. We can do that just by using html.
   Name the section which we want to be redirected using an id. And in the link, for the href we can specify #id. ie. If the id of a particular section is cta then href="#cta". By doing this, we are creating a page anchor.

   If all we cared about was the Google Chrome browser and also Firefox, then we wouldnt need any Javascript at all to now animate these scrollings. We can actually animate scrolling behavior just using CSS.

   In the html, we can specify scroll-behavior.

   html {
    font-size: 62.5%; 
    overflow-x: hidden;
    scroll-behavior: smooth;
   }

   The problem is it doesnt work on current version of Safari. The problem with this is Safari is the only browser that is available on the iPhone and iPad. So even Google chrome on these devices actually uses Safari as the rendering engine. And so on all these devices, so on all iPhones out there, it will not work.

   So, we should now write some Javascript to implement this functionality on all browsers. Not even the code we are going to write in Javascript alone will work in Safari. But there is a fix for that. We need to include below loc in our html.

   https://unpkg.com/smoothscroll-polyfill@0.4.4/dist/smoothscroll.min.js  - This is what we call a polyfill, which is basically a javascript library which implements this functionality for Safari.

   We need to add this before our script tag which we added for linking js with html.
   <script
      defer
      src="https://unpkg.com/smoothscroll-polyfill@0.4.4/dist/smoothscroll.min.js"
    ></script>

   Javascript code:

   // Selecting all the links in our html page
   const allLinks = document.querySelectorAll("a:link");

   // Iterating over each link element and adding eventListener for each link individually
   allLinks.forEach(function (link) {
   link.addEventListener("click", function (e)  // Getting access to event to prevent the default behaviour 
   {
    e.preventDefault();  // By default, it jumps harsly. So preventing the default behaviour

    const href = link.getAttribute("href");  // Getting the href attribute from the link element

    // Scroll back to top
    if (href === "#") {
      window.scrollTo({ top: 0, behavior: "smooth" });
    }

    // Scroll into sections
    if (href !== "#" && href.startsWith("#")) {
      const sectionEl = document.querySelector(href);  // Consider href="#cta". This is similar to id selector. We can take that to our advantage
      sectionEl.scrollIntoView({ behavior: "smooth" });
    }

    // Close Mobile Navigation
    if (link.classList.contains("main-nav-link")) {  // If we are clicking links from mobile navigation, then it should be closed once done.
      headerEl.classList.remove("nav-open");
    }
   });
   });


4. Implementing a Sticky Navigation bar
   First starting to style sticky navigation bar

   .sticky {
    position: fixed;  // What it does is it will fix the element basically in the view port, and will not move it as we scroll.
    top: 0;
    bottom: 0;
    width: 100%;
    background-color: #fff;
   }

   <header class="header sticky">
   ....
   </header>

   This is kind of already what we are looking for.
   Problem 1: It stays behind some elements because some element has position set to relative and some has higher z-index. So, to stay on top of all we really need to give high z-index value.

   .sticky {
   position: fixed;
   top: 0;
   bottom: 0;
   width: 100%;
   z-index: 999;
   background-color: #fff;
   }

   We can see some space has been lost for the header. ie. now the header is overlapping the hero section and it lost its own space. Now, the page is starting from the hero section and the header is on top of that. And that is because, the header, so the entire element, has been taken out of the flow just like with position absolute. When we position an element with position absolute, it is taken out of the flow of the page and therefore, it is as if it doesnt even exist. And so then the rest of the element fill the remaining space. And so with position fixed, the exact same thing happens. We will have to fix that at some point.

   Providing fixed height and box-shadow:
   .sticky {
   position: fixed;
   top: 0;
   bottom: 0;
   width: 100%;
   z-index: 999;
   background-color: rgba(255, 255, 255, 0.97);
   height: 8rem;  // Providing less height than the actual header
   padding-top: 0; // Remove padding if exists
   padding-bottom: 0;
   box-shadow: 0 1.2rem 3.2rem rgba(0, 0, 0, 0.03);
   }

   It is important to give fixed height here.

   We dont always want the navigation to be sticky. So we want it be sticky only after the hero section. Only once the hero section goes out of the view port we want the navigation to be sticky. And so now, we can use Javascript to do exactly that. So, basically to add the sticky class as soon as the hero section is no longer visible.
   And the way we do this is by using a very modern way, which is called the intersection observer. There would be multiple ways of doing this, but this is the most performant way, and also the most modern and best way.

   Inside IntersectionObserver, we need to specify two things. First, what we want to happen ie. we will define a function. And then second, we will specify some options.
   new IntersectionObserver(function() {}, {});
   
   We can then save this IntersectionObserver into a variable.
   const obs = new IntersectionObserver(function() {}, {}); because now we need to actually do obs.observe(). Inside observe, we now need to basically observe some element in the HTML using this observer (obs) that we specify here. And so, in our case that is the hero section.

   const sectionHeroEl = document.querySelector(".section-hero");
   obs.observe(sectionHeroEl);


   Then defining options
   ------------------------
   1. The first thing is the root. And the root is basically simply where this element should be appearing or not. So we will just set it to null. And what that means is that we will observe the hero section inside of the view port. So, basically as it moves through the view port.
   2. Next we need to set a threshold. And we set this one at 0. And 0 basically means that this will fire ie. we will have an event as soon as 0% of the hero section is inside of the view port. Here, we could also specify multiple values. It could also be 1 and then we would get the event whenever the hero section is completely inside of the viewport.
   const obs = new IntersectionObserver(function() {}, {
      root: null,
      threshold: 0
   })

   And for now, that is it.
   And so now we need to actually specify what we want to happen when this is the case. So, whenever we have the threshold of 0 in the viewport.

   And the function get access to basically something called an array of entries. And there's gonna be one entries for each threshold value. But here we just have one and so we can simply use entries[0]. When we log this entry into the console, we get bunch of data and the most important is isIntersecting. We can use that condition to check for whether the hero has crossed the intersection and add the sticky class appropriately.
   const obs = new IntersectionObserver(function(entries) {
      const ent = entries[0];
      if(ent.isIntersecting === false) {
         document.querySelector(".header").classList.add("sticky");
      }
   }, {
      root: null,
      threshold: 0
   });

   We have added sticky class to the header and now only when the intersection becomes false ie. when the hero section is out of the view port sticky class is added to the header. But now the problem is when we move out of the hero-section, we can see sticky navigation appears with a big jump. And that is because, as told earlier sticky navigation position is set to fixed and it is basically taken out of the flow from the page so it lost its height ie. header will lose its height once the sticky class is added. So, now we need to add margin-top to the section-hero to compensate for the lost height. How can we do that?

   .section-hero {
      margin-top: 9.6rem;  // 9.6rem is the height of the actual header. And so adding same margin to compensate for the lost height.
   }

   But how can we relate that to the sticky class which has been added to the header. Because, only when the header has sticky class, we need to add this spacing. But how to add that condition. Because since header is not a parent of section-hero, we cannot do this ie. .sticky .section-hero. Instead what we have to do is to always add the sticky class not to the header but to the body, which is the parent element of both the header and section-hero.

   Then we can apply styles for the sticky class just like this.

   .sticky .header {
   position: fixed;
   top: 0;
   bottom: 0;
   width: 100%;
   z-index: 999;
   background-color: rgba(255, 255, 255, 0.97);
   height: 8rem;  // Providing less height than the actual header
   padding-top: 0; // Remove padding if exists
   padding-bottom: 0;
   box-shadow: 0 1.2rem 3.2rem rgba(0, 0, 0, 0.03);
   }

   Now, the above styles get applied to the header only if the sticky class is present on one of its parent element which in this case is the body. Then we can do the same.
   .sticky .section-hero {
     margin-top: 9.6rem;
   }

   And in the Javascript we need to add sticky class to the body, and not to the header.
   const obs = new IntersectionObserver(function(entries) {
      const ent = entries[0];
      if(ent.isIntersecting === false) {
         document.body.classList.add("sticky");
      }
   }, {
      root: null,
      threshold: 0
   });

   Now, with this we get a sticky navigation as soon as we move out of the hero section. But that is immediately overlapping the featured-in section. So, what we can do is when hero section is still available on the viewport, ie. when it is available exactly on the height of the sticky navigation we make it so that the sticky navigation starts to appear from there so there it wont immediately overlap the featured-in section. And so, we can specify third option which is the rootMargin. And, so that margin is then basically applied outside of the root. And the rootMargin should be specified in px, as a string.

   const obs = new IntersectionObserver(function(entries) {
      const ent = entries[0];
      if(ent.isIntersecting === false) {
         document.body.classList.add("sticky");
      }
   }, {
      root: null,
      threshold: 0,
      rootMargin: "-80px"  // Height of the sticky navigation
   });

   We set the rootMargin exactly to the height of the sticky navigation. And it is the reason why we need to manually set the height of the sticky navigation. And not let the content decide the height.

   Final code from the Javascript:
   ----------------------------------
   const sectionHeroEl = document.querySelector(".section-hero");

   const obs = new IntersectionObserver(
   function (entries) {
    const ent = entries[0];
    // console.log(ent);

    if (ent.isIntersecting === false) {
      document.body.classList.add("sticky");
    }

    if (ent.isIntersecting) {
      document.body.classList.remove("sticky");
    }
   },
   {
    root: null,
    threshold: 0,
    rootMargin: "-80px",
   }
   );
   obs.observe(sectionHeroEl);

   Styles applied from css:
   ----------------------------
   .sticky .header {
   position: fixed;
   top: 0;
   bottom: 0;
   width: 100%;
   z-index: 999;
   background-color: rgba(255, 255, 255, 0.97);
   height: 8rem;
   padding-top: 0;
   padding-bottom: 0;
   box-shadow: 0 1.2rem 3.2rem rgba(0, 0, 0, 0.03);
   }

   .sticky .section-hero {
   margin-top: 9.6rem;
   }


5. Browser Support and Fixing Flexbox gap in Safari
   With the latest effects that we just implemented using Javascript, we can now basically consider that the design and planning step of our project is finished. Now we are ready to move on to the next step, which is the test and optimize phase.

   Browser support used to be a hugely important topic some years ago. But fortunately, not so much any more. Browser Support means basically how different web browsers support different CSS properties. Back in the day, like 10 years ago, there used to be a ton of inconsistencies between browsers. So our websites would look completely different in different browsers, and that was simply because some browsers didnt implement some of the modern properties that we were using at the time. Now, those days are fortunately over, atleast for the most important CSS properties, and if we consider that our users are usually using the latest browser versions. However, there will of course always be some users that are left behind using some very old browsers, like some old IE, or stuck on some older Safari version, and so there some of the things on our website might not work as we intend. So, to help developers with that, there is a very, very handy tool that we can use to basically see how different CSS properties are supported by different browsers.

   Tool: caniuse.com
   Here, we can input any CSS property that we want to check.

   The Internet Explorers, they were always very big problems for web designers and web developers. So, supporting them used to be really a nightmare, and we can be really glad that those days are over. Right now, basically the main browsers that matter to us are Microsoft Edge, Firefox, Chrome and Safari. And so, if all the properties that we use are supported in these four browsers, then everything is fine and they should also be supported on their mobile versions. Eg: Safari on iOS, Chrome for Android, Firefox for Android. So, these mobile browsers are also important to keep in mind as more and more of the internet traffic is shifting to mobile.

   Checking flexbox support on browsers:
   Flexbox has better support at 96%, and if we added prefixing, then that would increase to almost 97%.

   What is prefixing?
   Consider the property backdrop filter. This is the property that we havent used yet. This is quite a modern one. So, in Safari it is supported only with prefix webkit in some particular version.

   .main-nav {
    background-color: rgba(255, 255, 255, 0.7);
    backdrop-filter: blur(10px);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;

    transform: translateX(100%);

    display: flex;
    align-items: center;
    justify-content: center;
    
    transition: all 0.5s ease-in;

    opacity: 0;
    pointer-events: none;
    visibility: hidden;
   }

   This element is absolutely positioned on top of header with the background color as we know. We are using the backdrop-filter here and what it does is it will blur the content behind it. So, on testing in Safari it doesnt blurs the content behind it. But as said earlier, it is supported only with prefix webkit.

   To use prefix in practice
   Add -webkit- vendor prefix at the property.
   
   .main-nav {
    background-color: rgba(255, 255, 255, 0.7);
    -webkit-backdrop-filter: blur(10px);
    backdrop-filter: blur(10px);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;

    transform: translateX(100%);

    display: flex;
    align-items: center;
    justify-content: center;

    transition: all 0.5s ease-in;

    opacity: 0;
    pointer-events: none;
    visibility: hidden;
   }

   There are also other prefixes for other browsers like -moz- for Firefox. For eg, for appearance property.

   Fixing flexbox gap property in safari : Check JS code


6. Testing Performance With Lighthouse
   The Lighthouse tool is basically an automated tool that we can use to improve the quality of our pages. It was developed by Google and therefore it is available in our devtools.

   On the devtools, select Lighthouse tab.
   Select all categories except Progressive Web App and select Device -> Desktop. And Generate Report.


7. Adding Favicon and Meta Description
   Meta-Description
   Its basically a short summary of our websites content and its also the text that will appear for each of the search results in Google and other search engines.
   To add that to our page, we once again use the meta element.

   <meta
      name="description"
      content="Omnifood is an AI powered food subscription that will make you eat healthy, 365 days per year. Its tailored to your personal taste and nutritional needs"
   />

   Favicon
   We can see all the websites hosted on internet has some icon on title bar which is something called favicon. The default one (earth icon) looks bad. Never leave that as it is. We need to change that to our own favicon.

   We have favicon image on our folder. But we will resize it as per our need. Because we need multiple versions of the favicon.
   Resizing images in windows:
   Open the image using paint app -> Select Resize and Skew in Toolbar -> Specify height and width in px

   Favicon for browsers
   To add an favicon to the titlebar, we need to include that in the head using the link element. We need to specify "icon" for the rel attribute and the path to the image for the href attribute.
   <link rel="icon" href="img/favicon.png" />

   We have added favicon to the browser but actually we are not done here yet. We are done with the browser part but there are actually ways of adding a website basically as a favorite to iOS devices and also to Android devices. There is actually an option on both these operating system that we can basically add a website to the home screen. And so for that, we will need to provide a special icon.

   Icon for Home Screen in Android and iOS
   Lets start with iOS:
   Specfiying dimensions here for favicon: The dimension should be 180*180. Its kind of a hard rule for the Apple.
   And we need to include link element as below
   <link rel="apple-touch-icon" href="img/apple-touch-icon.png" />

   Android:
   For Android, we need two favicons with different dimensions. ie. 192*192 and 512*512
   And the process is different for Android. We need to create a brand new file in home folder called manifest.webmanifest and include below loc

   manifest.webmanifest - This is kind of a file extension that is used for Android to recognize a different favicons, basically.

   {
   "icons": [
    {
      "src": "img/favicon-android-192.png",
      "type": "image/png",
      "sizes": "192*192"
    },
    {
      "src": "img/favicon-android-512.png",
      "type": "image/png",
      "sizes": "512*512"
    }
   ]
   }

   And then include link element as below
   <link rel="manifest" href="manifest.webmanifest" />


8. Image Optimizations   
   Image Optimization both in terms of image dimensions and also of the actual file size in terms of kilobytes.

   Optimizing in terms of dimensions:
   Take the image at the bigger layout because at that point the images will be in bigger size that they will ever be. As we scale the layout down, the images will only get smaller. And so its important that we do this analysis at the biggest size that the image will ever be.

   Remember the lecture about images from way back in the design section: The actual image size, so of the image file itself should always be double of the size that is actually displayed on the screen. The reason is that these high density screens actually need two pixels of the image to display one pixel in the design, so in the layout. The actual image size, we can get it by hovering over the image in the devtools. ie. intrinsic size is the actual image size.
   
   Consider the app screen images which is already optimized
   Actually the rendered size is 188 × 379 px. Here, the intrinsic size ie. actual size is 400 × 809. That is because, we rounded the rendered size into 200 and doubled the image itself ie. made 400. So, basically the process is this. We start with a really big image if we have it. So, in this case, it was probably like 1000 px wide. And then, once the design is finished, we need to check out the largest width that the image will ever have. And thats again 188 px. And then we can round that and need to double that. And then we need to go ahead and resize the image to have a width of just 400px.

   Optimizing Hero image dimension:
   Currently the intrinsic/actual size of the hero image is 1479 × 1459 px. But the rendered size is only 570 × 562 px (at the biggest layout). We need to optimize this in terms of dimensions. We round the rendered size into 600px and double it which is of course 1200px and resize the image. Now the optimized hero image in terms of dimension is 1200 * 1184 px. Thats the first half of the image optimization. The other half is to actually compress the image in order to actually reduce the file size because it still has 1.8MB which is way too much.

   Optimizing in terms of file size:
   We can check out the entire size of the page basically by coming to the network tab in devtools and then reloading. We can see below some information which says it transferred 3.6MB (disable cache). And again, thats way too much. So, the tool that we can use to compress images is called squoosh.

   Toolbox:
   Squoosh - Image Compression

   Go to the squoosh website and select the image that we want to compress.

   It starts with JPEG format and compresses a lot. But this is not going to work because with JPEG we cannot have basically transparent parts of the image.

   Lets try with Browser PNG. Here, we dont have a lot of compression.

   Lets try OxiPNG. It did reduce by 16%. Lets try to increase the effort. But it doesnt changes anything. Then we have to play around a little bit with different options that we get for each of the image files. Then trying to reduce the palette. Indeed, the file size went down a lot like 75%. But the image doesnt look much great anymore.

   We can actually do something else. And something which is much better, which is to instead of using PNG, we can use a very new and modern image format called WebP. Lets try WebP and out of the box immediately we get a compression of 95%. Then we increase the quality of the image and downloading this format of the image. And using it in our code.

   <img
              src="img/hero.webp"
              class="hero-img"
              alt="A women eating in a classy restaurant"
   />

   However, there is one problem with this. We need to check browser support for WebP (using caniuse.com). Safari had only partial support till 2022 which was not long ago and mobile Safari has support only from iOS 14 which was released on 2020. So, if we use webP our image will not be displayed on these devices which is really bad. We dont want to happen that at all. So, theres something we can do about that, fortunately.

   Instead of using <img> directly to display image, we can make use of picture element.
   <picture>
              <source srcset="img/hero.webp" type="image/webp" />
              <source srcset="img/hero.png" type="image/png" />

              <img
                src="img/hero.png"
                class="hero-img"
                alt="A women eating in a classy restaurant"
              />
   </picture>

   Inside picture, we will define the two possible images that we have. So, the webP image and the png image. We define it by using source element.
   Here, we could also actually define vedios. So, we need to define the type using type attribute. So, what happens now is that a browser will basically select which of the two images here it can display the best. So, for those browsers who cannot display the webp, will simply select the other one. But if the browser is able to render the webp, which is most of the browsers, then it will render that. But where the browser will actually render it? So, we need to specify <img> inside picture element. The browser will basically simply replace whatever src we have in img tag with one of the possible images. And inside img src, we actually want the fallback. So, basically the one that will be displayed in case that the browser does not understand the source element because this is also something a bit newer. So, here we will provide version that all browsers should be able to render which is normal png. This is how we can select basically two different images and let the browser decide which one works best.

   This is how we can use high performing image format like webp to be able to really, really compress down images while maintaining their quality. And thats of course specially important for big images who take up a lot of space. We should not neglect this part when building our own websites. So, compressing images is really something that we must do for our users.


9. Deployment to Netlify
   netlify.com -> Sign up -> Free metered usage
   To deploy a new site,
   Go to sites -> browse and upload manually or we can do it via git.
   Once site is deployed, we can see the overview on the same site tab.

   We can change the site name to our custom name. Select the site for which we want to change the name -> Select site configuration -> Below site information, we will have the option to change the site name.


10.Making Form work with Netlify
   On the form which we want to connect with netlify, provide attribute netlify on the form element. And give the form a unique name. Also, for each input fields, give unique name which is necessary. And once done, we can redeploy it again into netlify by going into the particular site folder and selecting Deploys. And once again, we can browse and upload the same.

   Important: On the forms tab on the site folder, make sure form detection is enabled. Once deployed, now the form submission is possible. Go to the live website and submit the form with info. Once done, we can check it in Netlify under the Forms tab in particular site.