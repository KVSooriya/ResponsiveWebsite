1. Defining and Planning the Project (Steps 1 and 2)
   
   Our first "job"!
   👉 We were hired to design and build a website for a fictional company called Omnifood
   👉 Omnifood is a startup that uses AI to create and deliver custom healthy meal plans
   👉 They provided us with all the content for the website (content.md)
    
   In the content folder, we have all the images and content.md. md stands for markdown which is a special text format that we use many times in development. So, basically in markup, having one hash (#) like this is for the main-heading. Then two hashes (##) is for the secondary heading and so on and so forth. So, we have three hashes (###) which is a tertiary heading so its a little bit like h1, h2 all the way to h6 in html.

   Short description about Omnifood from content.md
   We are a technology company first, but with a major focus on consumer well-being through a healthy diet. Most people are very busy with their jobs, family and friends, and other important activities, which doesn't leave much time for cooking. This might lead to a poor diet and lasting health consequences. We want to solve this problem by using an AI-centric approach. Users can use our app to select their diet and foods they like and dislike, and our AI algorithm will create a custom and individual weekly meal plan. But we don't stop there. We partner with restaurants and other cooking partners to actually cook and deliver all meals from the generated meal plans, in selected cities. All this will be packed up in a monthly subscription, where users can choose between receiving one or two meals per day, every single day of the month.

   Now based on the content and on the Omnifood description, lets actually start planning our project.

   Step 1: Define the Project
   i.Define WHO the website is for   
     For a client, Omnifood Company in this case
   ii.Define WHAT the website is for   
      Business goal: Selling monthly food subscription
      User goal: Eating well effortlessly, without spending a lot of time and money    
   iii.Define target audience
      Busy people who like technology, are interested in a healthy diet, and have a well-paying job

   Step 2: Plan the Project
   i.Plan and gather website content 
     Already done
   ii.Plan out the sitemap
     In this case, not necessary. We will just build a one-page marketing website (oftentimes called a landing page), so no sitemap
   iii.Define website personality
     Based on the tech-centered target audience, as well as the actual product being sold, we will use the startup/upbeat personality. We might add some elements of the calm/peaceful personality, since the product is all about consumer well-being as well.
   iv.Plan page sections
     As said, our content should guide the design and planning of the sections
     
   Page Sections based on content
   - Navigation [Eventhough this page is only a single page website, we still want some kind of navigation, where the links can lead the user to different sections of the page. And that is useful because each of the sections will kind of be a mini page. So, back in the day, actually, websites were made like that where each page only had very little content and then each of the sections here could actually be its own page. But now, in modern design, and especially for landing pages, its quite common to simply have a very long page where the user simply keeps scrolling. So, a navigation can be helpful there]
   - Hero
   - Features
   - How it works 
   - Diets
   - Meals
   - CTA 
   - Pricing
   - Gallery
   - Testimonials
   - Featured in
   - Footer

   After planning sections,
   - Logo + Navigation
   - Hero
   - Featured in 
   - How it works
   - Meals (and list of diets)
   - Testimonials + Gallery
   - Pricing + Features
   - CTA
   - Footer


2. Sketching Initial Layout Ideas (Step 3)
   Common form of hero section: Image on one side and text (heading and summary) on other side
   Featured in logos placed side by side
   How it works section? Since the text is long, place in an z-pattern
   Meals (similar to cart)
   Testimonials - grid of 4 boxes and gallery - 3 by 4 images, both placed side by side


3. Responsive Design Principles
   
   What is Responsive Design?
   A technique that we can use to make a webpage adjust its layout and its visual style to any possible screen size (window or viewport size)
   This means that responsive web design makes website usable on all devices, such as Desktop computers, tablets and mobile phones.
   Responsive Web Design is not a seperate technology. Instead, it is really just a set of best practices and of techniques that we use in our regular CSS.

   And speaking of the set of best practices and techniques, there are essentially four big ingredients to responsive designs
   
   Responsive Design Ingredients 
   1. Fluid Layouts
      - This basically allow the webpage to adapt to the current viewport width (or even height). We have seen this behaviour with flexbox and CSS Grid.
      - And we can very easily create fluid layouts simply by using % (or vh/vw) unit for all elements that should adapt to the viewport. So, using % instead of px for all the elements that are usually part of any layout.
      - We should always use the max-width property instead of simply width.
   2. Responsive Units
      - This basically means that we should use the rem unit instead of px for most of the length that are in our CSS.
      - And using rem instead of px, will make it really easy for us to basically scale the entire page up or down automatically.
      - Helpful trick: setting 1rem to 10px for easy calculations
   3. Flexible Images 
      - By default, images behave different than text content because they do not scale automatically as we change the viewport. Therefore, we need to fix that.
      - We simply make images flexible by defining their dimensions in % and not using px, and also sometimes by using the max-width property and not using width.
   4. Media Queries
      - Media Queries is what brings all the other ingredients together and really brings responsive sites to life. Without media queries, responsive web design would not work at all.
      - That is because, media queries allow us to change styles on certain viewport width, which we call breakpoints. So basically, media queries allow developers to create different versions of a website for different types of devices because different types of devices have a different width.
      - However, media queries alone are completely useless. We really need to start creating fluid layouts from the very beginning, and the same is true for responsive units and flexible images. And in fact, we usually write media queries only at the end of building a certain page or a certain component.

   Desktop-First Vs. Mobile-First Development
   Desktop-First:
   👉 Start writing CSS for the desktop: large screens
   👉 Then, media queries shrink design to smaller screens

   This is the more traditional way of doing things, and its also the easier way to learn. We will use the desktop-first approach for Omnifood project

   Mobile-First:
   👉 Start writing CSS for mobile devices: small screen
   👉 Then, media queries expand design to a large screen
   👉 Forces us to reduce websites and apps to the absolute essentials. Since, we as a developer, have to think about the mobile experience for our users. We can do that by stripping away everything that is entirely not necessary. 

   And since we live in a mobile world now, this has actually become the more modern way of building websites these days.


4. How rem and max-width work?
   
   max-width:
   <div>Test</div>

   div {
   width: 1000px;
   background-color: red;
   padding: 100px;
   }

   If we simply use width, then the width stays fixed. ie. now we get horizontal scroll bar at the bottom of the window if we make the window smaller.

   div {
   max-width: 1000px;
   background-color: red;
   padding: 100px;
   }

   If we use max-width instead of width, then the width wont be rigid. ie. if we make the window smaller, the width adjust automatically based on the parent container. Then the scroll bar does not appears at the bottom.

   We can think we might use % for this case, but this wont create effect that we were looking for. Because up until 1000px, we actually want the element to be exactly 1000px wide. So, not any percentage of the view port. Only once we reach a width that is less than the actual width of the element, so only in that situation, we actually want the width to adapt to the parent element. So, basically occupying 100% of the width of the parent element.

   We can say that if the container width is larger than the specified max-width, then the width of the element is equal to the value that was specified for max-width. However, if the container width is less than the specified max-width, then the width of the element will be 100% of the container element width.

   rem unit:
   What does rem mean or what does it stand for? rem is the root element font size. The root of the document is the HTML element ie. basically the parent element of all the others. If we dont define any font size on the html element, then one rem is simply equal to the default browser font size, which is always 16px unless the user does actually change it.

   div {
   /* max-width: 1000px; */
   max-width: 50rem;    // width = 50 * 16px (default browser font size) = 800px
   background-color: red;
   padding: 100px;
   }

   We might find it strange that we define length in our design based on font size. But that is where exactly the strength of the rem unit lies. Because then we can simply change the font size on the HTML element, and that will then automatically change all the length that are defined anywhere in our CSS with the rem unit.

   In the end, before elements can be displayed on the page, all the relative units such as percentages or rems will be converted back to pixels.

   Now, on the html element, we set the font-size to just 10px. And so, then one rem will no longer be 16px but it will instead be 10px. 

   html {
   font-size: 10px;
   }

   So, what matters is that by changing the font-size, we can completely change the entire layout. If we try to double the font-size, then of course everything will get really big. So, the rem unit is really, really handy when we build responsive layouts. Because, for eg, when we have a smaller screen, then we want all the length to be a little bit smaller. And then instead of having to change all of the length values using media queries, we can simply change the font-size up in the html and that will then shrink everything down a little bit.  

   One useful trick: Setting font-size to 10px, then it is very easy to do calculations.

   However, this is still not perfect because by doing it like this, we will not respect user definition of the browser font size. Lets say the user changes the default from 16px to 20px, then of course they would expect that the font size on our page would increase. But with setup on root element, that would actually not happen. So, no matter what the user set the font size now, we would always have our default font-size, or our root font-size as 10px. And so this would create huge usability problems for users who for some reason have to increase/decrease the font size of their browsers. In order to avoid that, we will not set the font size to a fixed value like this, but instead to a percentage of the default font size of the browser. 
   
   html {
   /* font-size: 10px; */
   /* Percentage of browsers font-size setting */
   font-size: 62.5%; /* This is similar to setting 10px, because default font-size of browser: 16px and 10/16 = 0.625 which is same as 62.5%. And
   if the user changes the font size in browser it adapts automatically since we are using % */
   }

   And so by doing this, we did actually respect browsers font size setting. And in fact, many, many web designers and CSS developers use exactly this trick. It is something that is used widely in the CSS developer community.


5. Building a hero section

   <section class="section-hero">
      <div class="hero"> <!-- We could have used simply section-hero as a grid container but then we cannot use fixed width container because we want the hero section to have some background color that goes from left to right which we can achieve using section-hero. -->
        <div class="hero-text-box">
          <h1 class="heading-primary">
            A healthy meal delivered to your door, every single day
          </h1>
          <p class="hero-description">
            The smart 365-days-per-year food subscription that will make you eat
            healthy again. Tailored to your personal tastes and nutritional
            needs. We have delivered 250,000+ meals last year!
          </p>
          <a href="#" class="btn">Start eating well</a>
          <a href="#" class="btn">Learn more &darr;</a>
        </div>
        <div class="hero-img-box">
          <img src="img/hero.png" alt="A women eating in a classy restaurant" />
        </div>
      </div>
   </section>

   For the hero section, we are using css grid. Of course, we can use flexbox for building layout here since its a one-dimension but creating equal sized columns is quite easy using css grid. Also, we can use the same tool for layout across the entire page.

   We want to make the image flexible and we can do that by setting it in %.
   .hero-img {
   width: 100%;
   }

   100% will then fill the entire parent element which is the hero-img-box which is exactly one of the two columns of the grid. That column has half the size of the grid container.
 
   Regarding decreasing letter spacing in heading,
   .heading-primary {
   font-size: 5.2rem;
   font-weight: 700;
   line-height: 1.05;
   letter-spacing: -0.5px;
   }

   Here, however we are not using rem instead we use -0.5px and thats because this is just a very small distance here, and its also distance that we dont really need to scale up or down. And so then we can simply keep using pixels in those situations.

   Deciding background-color in hero section
   Remember that we're using the startup website personality here. And in that personality, its quite common to have very light background colors in some of the sections. Usually that is using a gray color. But here in this design, we actually also want to include some elements of the calm personality. So, it would be nicer to not use a gray color, which is a little bit colder, but actually use a very, very light shade or a tint, maybe of our primary color.

   Background colors for the buttons on the hero
   For the main button, giving bgcolor as primary color and on hovering giving a darker shade of that.
   For the secondary button, giving bgcolor as white and on hovering giving the same bgcolor as that of entire hero section. So, on hovering, the button kind of gets disappeared. For that, we are adding some kind of border around the button. And thats actually harder than it sounds.

   Trying,
   .btn--outline:hover,
   .btn--outline:active {
   background-color: #fdf2e9;
   border: 3px solid #fff;
   }

   On trying this, on hovering, the border kind of gets added to the outside. So, we can see the effect the entire layout jumps a little bit. And so, of course, we dont want that. 
   What we need basically is to add the border to the inside of the button. And for that, we can use a trick which is not using the border property, but the box-shadow property.


   /* Trick to add a border inside */
   box-shadow: inset 0 0 0 3px #fff;
   
   So, use the box-shadow without any offset in any direction. So, not horizontally and not vertically. We also dont want it to have any blur but we want to scale it basically by 3px. And we simply specify the color. Like this, it would basically create the same effect as border property which is basically border outside. Then, we have to add the inset keyword. With this inset keyword, the shadow will basically be added to the inside of the element.

   Right now, the hover effects dont look really nice and professional because if we were to go to a real-world website and hover over some button then we would actually see a nice animation from one color to the other. Now, it simply jumps basically from one color directly to the other one. 
   So, we can basically create a nice animation using just CSS. So, to do that, we basically come to the element, so to the rule, which has the original state. And that is, in this case, btn:link and btn:visited. So, this is the state before any hover. And here we can add the transition property. 

   Transition property is a property that allows us to do just what it says. So, to transition between two values using an animation. Then here we can specify multiple things but atleast we need two things. We need the property that we actually want to animate and we need to say over how much time we want the animation to happen.
   Here, we want to animate the background color.

   transition: all 1s;  // all - all the properties will be animated 
   or 
   transition: background-color 1s;

   We could also specify a third value to change the type of the animation but that is little bit more complex.
   Note: Always put transition on a original state

   Then, we need to fix space between the buttons. How we can do that?
   .btn-full needs to be reused at a later point on this site. So, therefore, we should not simply add margin to the right on that class. Another option would be to wrap two buttons into some flex container and then add some gap into that one. But that would be little bit too much work. Instead, we can add a special helper class to the button.

   <a href="#" class="btn btn--full margin-right-sm">Start eating well</a>

   .margin-right-sm {
    margin-right: 1.6rem;
    }

   This will be like a reusable and very generic helper class which we can add to multiple elements to give them some space on the right side.
   When we use a helper class like this, we really really want the style that it has to be applied no matter what other styles are already on the element. In order to ensure that, we usually then add the important keyword because it always has the highest priority. Not necessary but thats just a good practice to do.

   .margin-right-sm {
   margin-right: 1.6rem !important;
   }

   How to make the customer photos in the hero section overlap on one another?
   For that, basically we want to decrease the spacing between them. 

   .delivered-imgs img {
   height: 4.8rem;
   width: 4.8rem;
   border-radius: 50%;
   margin-left: -1.6rem;
   }

   .delivered-imgs img:first-child {
   margin: 0;
   }

   
6. Building the Header and the Navigation
   We have provided background color of the header same as that of hero section so it looks as a part of the same sections. Also, now the header seems like glued to the top of the page. For, that we need to provide some spacing.

   What we are going to do actually is to give the header a fixed height. Usually, we simply allow the content to define the height and then add some padding usually. But the reason now we are giving the fixed height is that because we actually want to make the navigation sticky a bit later. Which means as we scroll down the page it would stay at the same position. And for this to work, its a bit easier when the height is actually fixed.

   .header {
   display: flex;
   justify-content: space-between;
   align-items: center;
   background-color: #fdf2e9;

   /* Giving fixed height, so we can make the header sticky later easily */
   height: 9.6rem;
   padding: 0 4.8rem; // Padding only on sides
   }

   Navigation:
   The most semantic way of putting anchor/link inside nav: list of links grouped together. For that, we need to create an unordered list. And inside of that list, we need to add our links.

   Most of the websites add CTA at the end of the nav. So, we are doing the same and styling it a little bit different using the different class. And also to make sure the styles are applied without any confict, we are making use of and selector to give high priority.

   <li><a class="main-nav-link" href="#">Section 1</a></li>
          .....
   <li><a class="main-nav-link nav-cta" href="#">Section 5</a></li>

   The final link which is the cta, has both classes in common so it gets styles applied from both the classes. We might have some properties in common between them so to avoid such conflicts we have added and selector to provide higher specificity in order to get special styles applied to that link.

   .main-nav-link:link,
   .main-nav-link:visited {
   display: inline-block;
   text-decoration: none;
   color: #333;
   font-size: 1.8rem;
   font-weight: 500;
   transition: all 0.3s;
   }

   .main-nav-link:hover,
   .main-nav-link:active {
   color: #cf711f;
   }

   /* Placing cta at the end of the navigation */
   /* We want to style this with higher priority for this particular class,
   so using and selector, to avoid conflict between specificity */
   .main-nav-link.nav-cta:link,
   .main-nav-link.nav-cta:visited {
   background-color: #e67e22;
   color: #fff;
   padding: 1.2rem 2.4rem;
   border-radius: 9px;
   }

   .main-nav-link.nav-cta:hover,
   .main-nav-link.nav-cta:active {
   background-color: #cf711f;
   }


7. Building How it works section
   Centering the app screen inside the container. Lets do that by making use of flex
   <div class="step-img-box">
   <img src="img/app/app-screen-1.png" alt="App Screenshot" class="step-img" />
   </div>

   .step-img-box {
   display: flex;
   align-items: center;
   justify-content: center;
   }

   We wanted the text-box to be aligned vertically? How we can do that?
   We can do it in multiple ways.
   1. We can make it flex container but since it has multiple elements we need to change the flex direction and to align it vertically we need to use justify content and set it to center. However, thats two much of work.
   .step-text-box {
   display: flex;
   flex-direction: column;
   justify-content: center;
   }
   2. Since it is already a grid item, we can make the grid to align it themselves .ie. instead of aligning inside parent container, we can make grid to align by making use of align-self: center
   .step-text-box {
   align-self: center;
   }
   3. However, what we can do is to better align it from the parent container. For that, can we place align-items: center inside the grid class. No, because we want the grid class to be reusable and in future it makes it harder to reuse. So, for that we can create a helper class to provide setting for the grid. Its something like providing a setting for the grid.

   <div class="container grid grid--2-cols grid--center-v">
          <!-- STEP - 01 -->
          <div class="step-text-box">
            <p class="step-number">01</p>
            <h3 class="heading-tertiary">
              Tell us what you like (and what not)
            </h3>
            <p class="step-description">
              Never again waste time thinking about what to eat! Omnifood AI
              will create a 100% personalized weekly meal plan just for you. It
              makes sure you get all the nutrients and vitamins you need, no
              matter what diet you follow!
            </p>
          </div>
          <div class="step-img-box">
            <img
              src="img/app/app-screen-1.png"
              alt="App Screenshot"
              class="step-img"
            />
          </div>
   </div>

   .grid--center-v {
   align-items: center;
   }

   To make visually more interesting, adding circle to the background of the app screen image.

   Step 1. Adding square as child element of step-img-box so that we can make it circle and position it absolutely 

   /* Using pseudo element so that we dont want to pollute html just for visual styles. We cannot add pseudo element like after/before on img, because in html itself img cannot have child element */
   
   .step-img-box::before {
   content: "";
   display: block;

   /* 60% of parent elements width to make it flexible */
   width: 60%;
   /* height: 60%;   This does not work */
   /* However to make it squared*/
   padding-bottom: 60%; /* 60% of parent elements width to make it flexible */
   background-color: #fdf2e9;
   }

   Step 2: Position absolutely in relation to step-img-box and making it circle

   .step-img-box {
   display: flex;
   align-items: center;
   justify-content: center;

   position: relative;
   }

   .step-img-box::before {
   content: "";
   display: block;

   /* 60% of parent elements width to make it flexible */
   width: 60%;
   /* height: 60%;   This does not work */
   /* However to make it squared*/
   padding-bottom: 60%; /* 60% of parent elements width to make it flexible */
   border-radius: 50%;
   background-color: #fdf2e9;

   position: absolute;
   top: 50%;
   left: 50%;
   transform: translate(-50%, -50%);
   }

   Step 3: Currently the circle appears on top of the app screen image as we positioned it absolutely. But we want to appear it behind the image. How can we do that? 
   For that, we have a very handy property in CSS which is called z-index. z-index can be a little bit tricky to work with because there are many, many particularities to it, and the way it works is quite confusing actually. But when it does work, then basically elements that have a higher value of z-index will appear first, so will appear on top. So, what we are gonna do is to simply reduce the value of z-index on pseudo element. ie. we'll simply add a negative value
  
   .step-img-box::before {
   content: "";
   display: block;

   /* 60% of parent elements width to make it flexible */
   width: 60%;
   /* height: 60%;   This does not work */
   /* However to make it squared*/
   padding-bottom: 60%; /* 60% of parent elements width to make it flexible */
   border-radius: 50%;
   background-color: #fdf2e9;

   position: absolute;
   top: 50%;
   left: 50%;
   transform: translate(-50%, -50%);

   z-index: -1;
   }

   Adding another small circle behind the image and this time we use ::after because before can be used only once.
   And also we want small circle to be on top of larger circle. So, we need to provide appropriate z-index because element with the higher value of z-index will appear on top.

   .step-img-box::before,
   .step-img-box::after {
   content: "";
   display: block;

   position: absolute;
   top: 50%;
   left: 50%;
   transform: translate(-50%, -50%);
   }

   .step-img-box::before {
   width: 60%;
   padding-bottom: 60%;
   border-radius: 50%;
   background-color: #fdf2e9;

   z-index: -2;
   }

   .step-img-box::after {
   width: 45%;
   padding-bottom: 45%;
   border-radius: 50%;
   background-color: #fae5d3;

   z-index: -1;
   }


8. Building the Featured-in section
   Making the featured-in logo images gray. We can do that using some image manipulation program but here we are going to do using CSS trick.

   On images, we have a new property which is called filter. And with filter we can do all kinds of stuff. VS Code suggest us with many options and one that grabs our attention is grayscale. We can define a value between 0 and 1 or 0% to 100%.

   .logos img {
   height: 3.2rem;
   filter: grayscale(100%);
   }

   However, the images are not like completely gray. It is mixed with gray and black shade. We dont want that. We just want everything to be gray.

   We can play with images using filter property. Like to blur images by specifying in pixels and saturate images etc.,

   But what we are looking for here is, brightness.
   .logos img {
   height: 3.2rem;
   filter: brightness(0);
   }

   It makes the image completely black. Not partially black with gray shade.
   
   To make the images gray, we can use the opacity property along with filter set to brightness of 0. 

   .logos img {
   height: 3.2rem;
   filter: brightness(0);
   opacity: 50%;  // We could use 0.5 instead of 50% also
   }

   Opacity at 100% - The images look completely visible. Going down, at 0% the images become completely invisible. And we are using 50%, so it looks in an gray shade.



9. Building the Meals Section
   Inside the meal section, for each of the sample meal we have the category of meal like vegetarian or anything. Categories are many times a good fit for using tags. So, we can add that category of meals as a tag.

   Just like copyright, we have registered symbol which can be represented by html entity &reg;

   Placing icon for each of the list in the meal section
   Earlier we used icon pack which is heroicons. What we did there is to copy the svg code and used it in html. The problem with that is svg code is huge and it clutters up the html code and make it difficult to understand.

   Now, we can use icon pack which is ionicons.
   To use that in our html, we need to include script provided in ionicon page right before the closing tag of body. What it does is it gives access to special element called ion-icon. And then there we can simply use the name with the icon that we want to use. And so that will then basically automatically inject the svg into our page. 

   <!-- For making use of ion icons which gives access to special element called ion-icon  -->
   <script
      type="module"
      src="https://unpkg.com/ionicons@7.1.0/dist/ionicons/ionicons.esm.js"
   ></script>
   <script
      nomodule
      src="https://unpkg.com/ionicons@7.1.0/dist/ionicons/ionicons.js"
   ></script>

   When we style icons, we want to experiment with it a little bit because different icons pack work differently. For eg, to give icon a color we can use stroke/fill property and sometimes just color property. It depends on different icons from icon packs. Also, many times we specify height and width but sometimes we can also give them font-size similar to styling text.

   .meal-icon {
    height: 2.4rem;
    width: 2.4rem;
    color: #e67e22;
    }

   Next, we are designing tags
   We are wrapping tags inside a div because in second sample meals we have two categories. And if want to provide some spacing in bottom then we have to provide margin in both the categories. To avoid that we can wrap it inside div. And give margin-bottom to the div.

   <div class="meal-tags"><span class="tag">Vegetarian</span></div>
    
   .meal-tags {
    margin-bottom: 1.2rem;
   }

   .tag {
    display: inline-block;
    padding: 0.4rem 0.8rem;
    font-size: 1.2rem;
    text-transform: uppercase;
    background-color: #51cf66;
    border-radius: 100px;
   }
    
   Giving shadow to cards
   .meal {
    box-shadow: 0 2.4rem 4.8rem rgba(0, 0, 0, 0.075);
    border-radius: 11px;
   }

   After giving border-radius, we can observe the image still looks like an squared and the image is basically lying now on top of the rounded corners. The roundness is in the background but we cannot see it because the image is laying on top of that. So, its basically overflowing the element now but we can easily fix that. We can say that whatever overflows the container should be hidden.  

   .meal {
    box-shadow: 0 2.4rem 4.8rem rgba(0, 0, 0, 0.075);
    border-radius: 11px;
    overflow: hidden;
   }

   We want to apply some padding inside the card. Can we do it inside meal? No, because that will also apply padding to image. So whenever we are designing a card with an image at the top, we then need another box which contains basically the rest of the written content. So, we can apply padding to that.

   Note: When we are placing more than one card side by side, with image on top make sure the images have same dimensions or atleast same aspect ratio.

   We have used link so if the user wants to view all recipes then it will lead to different page. By default, links have an underline which we disable by setting it to text-decoration: none. But we recreate the same using border-bottom and the way why we do this is we can specify padding-bottom and then it will have some spacing between border which looks like underline, and text itself. In the case of default underline, we cannot do this. Thats why we normally follow this way.

   .link:link,
   .link:visited {
    color: #e67e22;
    text-decoration: none;
    border-bottom: 1px solid currentColor;
    padding-bottom: 2px;
   }

   currentColor - Why we used this. The border will get same color as that of text and it is especially useful when we change color during the hover state.

   When we hover over the link we want the underline (in this case, border) to disappear. Can we do this?
   .link:hover,
   .link:active {
    color: #cf711f;
    border-bottom: none;
   }

   No, since border is part of the element, when we do this on hovering the layout jumps a little bit which does not looks good. So instead we can set the border color to transparent which makes it invisible.

   .link:hover,
   .link:active {
    color: #cf711f;
    border-bottom: 1px solid transparent;
   }


   Adding nice hover effects on two cards. So the effect that we want to implement is that whenever we hover over the card element, we want the entire element to move up a little bit. So, for that we can use transform with translate property which moves the element around. And we can also manipulate the shadow here a little bit to make the effect bit more realistic. So, by moving up the element, we kind of simulate it moving closer to the source of the light. And so therefore, the shadow can then become a bit larger. So, we are making the shadow more diffused and bigger basically, also naturally should be lighter.

   .meal {
    box-shadow: 0 2.4rem 4.8rem rgba(0, 0, 0, 0.075);
    border-radius: 11px;
    overflow: hidden;
    transition: all 0.4s;
   }

   .meal:hover {
    transform: translateY(-0.8rem);
    box-shadow: 0 3.2rem 6.4rem rgba(0, 0, 0, 0.06);
   }



10.Building the Testimonials Section
   This section is going to go all the way from left side to the right side of the browser. So, not having a centered container but instead filling up basically the entire available width.

   figure element - It can be used to represent some self-contained content, and which sometimes has a caption. So, this is perfect for things like diagrams or photos or code listings or really anything that can have a caption and that is self contained. And the testimonial, that we are about to write qualifies nicely for that. We can see the figure element being used for this kind of thing all the time.

   blockquote element - For the actual testimonial content, we can use the blockquote element. So, blockquote, as the name says, is basically for representing quotes. So, things that someone else said. And so a testimonial is exactly that. And the same is true for something like a product review or even to quote someone in the context of an article or a blog post, for eg.

   For laying out 2*2 testimonials, we are not using resuable grids because it has way much spacing and only is suitable for bigger layouts.
   Also, for images here we are giving small fixed width instead of flexible percentage. Since, its just a small image basically.
   .testimonial-img {
   width: 6.4rem;
   border-radius: 50%;
   }

   For the heading of the section, we placed it inside the testimonial-container ie. above the grid of 2*2 testimonials

   For building gallery, this div is going to be the grid container. Of course, we can simply place all 12 images inside this div element directly. But since we want to create nice hover effect, we wanted a container for each of the 12 images.
   <div class="gallery">Gallery</div>

   We can notice a small space between each images and that is because the images are inline elements by default. And so if we make them a block element then this would disappear. This is something that we should know because sometimes we get these annoying white spaces around images. And then this is how we fix that.

   We want the top padding of images to be same as space ie. gap we provided in grid container. So, that the images will get same spacing around it. So, what we will do is to provide huge spacing only for testimonials and adjust the spacing for the gallery.

   /* Giving seperate padding for both testimonial and gallery instead of giving to the entire section */
   .testimonial-container {
   padding: 9.6rem;
   }

   .gallery {
   display: grid;
   grid-template-columns: repeat(3, 1fr);
   gap: 1.6rem;
   padding: 1.6rem;
   }

   We want our testimonial section to be wider than the gallery section but we dont want this.
   .section-testimonials {
   background-color: #fdf2e9;
   display: grid;
   grid-template-columns: 2fr 1fr;
   }

   We dont want the testimonial section to be twice as much as wider than gallery.

   One trick that we can use when using fr's is to use them as though they were percentages. So, remember the fr simply needs to be the same number in order to get the same sized column for both grids. For eg,
   .section-testimonials {
   background-color: #fdf2e9;
   display: grid;
   grid-template-columns: 50fr 50fr;
   }

   The above one looks little bit like percentages where first grid-column is 50% and the other one is 50%. So, we can use it as if it is percentage.
   .section-testimonials {
   background-color: #fdf2e9;
   display: grid;
   grid-template-columns: 55fr 45fr;
   }

   This makes the testimonial section little bit wider than gallery. The two need not want to add up to 100. The way we are doing this is to think in term of percentages.

   Nice hover effect on images:
   What we are going to do is whenever we hover the images we need to scale up the image. ie. they will become little bit larger.

   .gallery-item img:hover {
   transform: scale(1.1);
   }

   Now, just with this the effect doesnt look more nice. To make it nice, this is where container element comes into place. ie. the element into which we wrapped the images. As of now, if we scale up the image it overflows the parent container which is figure element. What we can do to prevent that is to simply set overflow to hidden on parent element.

   .gallery-item {
   overflow: hidden;
   }

   Now this creates a super cool effect of looking as if the image is moving towards the user when we hover it.


11.Building the Pricing and features section
   Fixing pricing-plan width:
   The pricing-plan is very, very wide and that is because we simply created a grid with two columns. So, they stretch across the entire grid cell because they are block level elements. However, we do not want that to fill the entire column. We can simply make them a little bit less wide.

   .pricing-plan {
   background-color: #fdf2e9;
   border-radius: 11px;
   padding: 4.8rem;
   width: 75%;
   }

   After making the width to 75%, it seems like both the pricing-plans are aligned to the left in their own grid cells and it looks like there is huge space between the pricing-plans. We want first pricing-plan to make it aligned right so it will have space basically between the two only of the gap and not due to the alignment. And the way we do that is by using justify-items property on the container. But if we do this it will align both the grid-items of the container. But we want only one grid-item to be justified. For that, we can make use of justify-self.

   .pricing-plan--starter {
   justify-self: end;
   }

   De-emphasizing plan 1 and emphasizing plan 2
   .pricing-plan--starter {
   justify-self: end;
   border: 2px solid #fdf2e9;
   }

   .pricing-plan--complete {
   background-color: #fdf2e9;
   }

   And by adding a border around the plan 1, we make a problem in alignment because the 2px is added on top of padding to the element 1 and if we take a look on button as we approach it on the end of the screen, one button seems like it has different alignment compared to the other. So, we need to adjust spacing between the pricing-plans so that both looks the same. So, instead of adding same padding on both the plans doing it seperately.

   .pricing-plan--starter {
   justify-self: end;
   border: 2px solid #fdf2e9;
   padding: 4.6rem;  /* We are giving 2px less padding on all sides, because 2px
   border is added on all sides now both the starter plan and complete plan looks as if they has same spacing */
   }

   .pricing-plan--complete {
   background-color: #fdf2e9;
   padding: 4.8rem;
   }

   A nice visual effect ie. a cosmetic added to the complete Plan
   Stating that the complete plan is the best value

   .pricing-plan--complete {
   background-color: #fdf2e9;
   padding: 4.8rem;

   position: relative;
   overflow: hidden;
   }

   .pricing-plan--complete::after {
   content: "Best Value";
   position: absolute;
   top: 6%;
   right: -18%;

   text-transform: uppercase;
   font-size: 1.4rem;
   font-weight: 700;
   background-color: #ffd43b;
   padding: 0.8rem 8rem;
   transform: rotate(45deg);
   }

   It kinds of create a ribbon saying "BEST VALUE"

   Adding features part
   We are going to add another grid inside the same section ie. just after pricing-plan grid we are going to add features grid. And this is more common to add more grids in a same section. And once we add the grid we can see there wont be any spacing between the grids. Of course, we can do it manually but we want the grid to do it automatically.

   The one way in which we can do that is to add margin-bottom inside the reusable grid container. But this will apply on all the grid container that we already created which creates a mess in our application. But we will say that if the grid is the last child on the section we dont want to apply the margin-bottom to it.

   .grid {
   display: grid;
   row-gap: 9.6rem;
   column-gap: 6.4rem;

   margin-bottom: 9.6rem;
   }

   .grid:last-child {
   margin-bottom: 0;
   }

   But we can do it more efficiently in a single line. That is, we can make use of pseudo-element which is called not. We can say that if the grid is not the last child element, then we need to apply margin-bottom.

   .grid:not(:last-child) {
   margin-bottom: 9.6rem;
   }

   Inside features part, we have included icons. To enclose icons into a circle

   .feature-icon {
   height: 3.2rem;
   width: 3.2rem;
   border-radius: 50%;
   color: #e67e22;
   background-color: #fdf2e9;
   padding: 1.6rem;  // Giving same padding on all sides so we can make them square
   margin-bottom: 3.2rem;
   }

   The icon from ion-icons works with the default behaviour of box-model ie. padding is added on top of height and width that we defined

   To give some spacing for additional details about plan, we had made it grid container because as we know we have applied some margin bottom for grid and to apply the same margin for this too. And it is not a issue to make it a grid because we can make a grid container even with one child element.

   <div class="container grid">
   <aside class="plan-details">
   Prices include all applicable taxes. You can cancel at any time. Both plans include the following
   </aside>
   </div>


12.Building the CTA Section
   We are not using reusable grid here because we want the content to be 2/3rd of the container and img to be 1/3.

   And we are using box-shadow so that we can make this section to really stand out. And the darker the background-color/background is, the darker the shadow should be.

   Instead of using background-color for this section, we are going to use gradient so that the entire section goes from one color to the other.
   
   More on gradient:
   We create a gradient using background-image property. By default, the gradient flows from top to the bottom.
   background-image: linear-gradient(red, blue); 
   
   But we can also change the flow. We can change it either by using degree or english language.

   /* This will flow from left to right */
   background-image: linear-gradient(90deg, red, blue);
   or
   background-image: linear-gradient(to right, red, blue);

   /* This will flow from top to bottom - which is default */
   background-image: linear-gradient(180deg, red, blue);
   or
   background-image: linear-gradient(to bottom, red, blue);

   /* Bottom to Top */
   background-image: linear-gradient(360deg, red, blue);
   or
   background-image: linear-gradient(to top, red, blue);

   And we can also basically use corners.
   background-image: linear-gradient(to right bottom, red, blue);
   Then it will start from left top corner and then flow to the right bottom corner.

   Speciying image:
   On the right side of the section, instead of specifying image, we are going to use background image, because then it will make it easy to overlay a color on top of it.
   .cta-img-box {
   background-image: url(../img/eating.jpg);
   }

   .. means that we need to go to the parent folder. So, moving one level up in the file tree.

   Since we added background image to the entire right side of the section, we ended up with the empty div on the html.
   <div class="cta-img-box"></div>
   However, the problem with this is that visually, of course, the element still contains an image, but now it is completely inaccessible to screen readers. We should however fix that.

   We can fix that using two newer attributes, role and aria-label
   <div class="cta-img-box" role="img" aria-label="Women enjoying food"></div>
   
   role - We are saying that the div element acts as if it was an image
   aria-label - And we are describing the image (similar like how we use alt in image).

   And so now screen readers will be back to understanding this as an image.

   Working with form:
   <form class="cta-form" action="#">
                <label>Full Name</label>
                <input type="text" placeholder="Bhargav Parithi" />

                <label>Email Addres</label>
                <input type="email" placeholder="parithi@example.com" />
                <button class="btn-form">Sign up now</button>
   </form>
   
   One important thing that we can do with label is when we click them, the input field that belongs to it will become active.
   <label for="full-name">Full Name</label>
                <input
                  id="full-name"
                  type="text"
                  placeholder="Bhargav Parithi"
   />

   Styling input elements:
   We can see that the input elements do not inherit the font family from body element by default. But we can force the input elements to inherit the font family by making use of new css keyword which is inherit. 

   .cta-form input {
   width: 100%;
   padding: 1.2rem;
   font-size: 1.8rem;
   font-family: inherit;
   }

   We can use this in all kinds of situations, not just for a font-family.

   To make the placeholder much lighter, we make use of pseudo element.

   .cta-form input::placeholder {
   color: #aaa;
   }

   Important Note:
   Focus State: When we click on the input elements, it gets focused with some predefined border. The same happens when we use tab on the keyboard. Thats because of the property called outline. But we dont want the default border. We can set the outline to none which causes accessibility problems for users who rely on keyboard. But then we can give other ways in which can provide accessibility.

   We can select every single element just like global reset and change the focus state there.
   *:focus {
   outline: none;
   /* outline: 8px solid rgba(230, 125, 34, 0.5); */

   /* Also other way of doing the above */
   box-shadow: 0 0 0 8px rgba(230, 125, 34, 0.5);
   }

   And we can also change the focus state on certain elements seperately like for input elements and so on.

   .cta-form input:focus {
   box-shadow: 0 0 0 8px rgba(253, 242, 233, 0.5);
   }

   But want we are going to do is for all the form elements we are going to apply the different focus state.

   .cta *:focus {
   outline: none;
   box-shadow: 0 0 0 0.8rem rgb(253, 242, 233, 0.5);
   }

   Here, we are saying inside the cta class apply the styles for all the elements for the focus state.


13.Building the Footer
   Wrapping Logo into a link
   This is something that we do all the time. So that when we click the logo, we will go back to the top. Also doing the same in the header.

    <a href="#">
        <img src="img/omnifood-logo.png" alt="Omnifood logo" class="logo" />
    </a>

   Also we will later implement some smooth scrolling functionality, which will happen when the user clicks the logo.

   Building contact information on footer:
   For address, we use special html element called address.

   For phone number and mail, we can wrap it inside special kind of link.

    <a href="tel:415-201-6370">415-201-6370</a>
    <a href="mailto:hello@omnifood.com">hello@omnifood.com</a>

   Setting href as tel:415-201-6370 will make the call to the phone Number. And
   mailto:hello@omnifood.com will open up our mail program.

   We want to change spacing in the first column of the footer ie. logo column. We want to make copyright text go all the way down. How we can do that? 
   As always, there are multiple ways of achieving this. We can manually try to add some margin bottom to the icons or margin top to the copyright text.
   But here, we are going to use flexbox trick that we used in the app layout (previous section). We push one element all the way to the end here using margin-top: auto trick.

   .logo-col {
   display: flex;
   flex-direction: column;
   }

   .copyright {
   font-size: 1.4rem;
   line-height: 1.6;
   color: #767676;
   margin-top: auto;
   }











   

   


