1. Responding to Small Laptops
   Before we actually write a single media query for our page, we first need to ensure that our HTML has one very important line.
   <meta name="viewport" content="width=device-width, initial-scale=1.0" />

   This meta tag might seem quite unimportant but actually for responsive web design it is absolutely crucial. Without this, responsive web design will actually not work on physical mobile devices. So, not on phones and not on tablets. And the reason for that is that browsers on mobile devices will basically zoom the page out by default until it fits the screen. And so thats not what we want with media queries. We simply want to make our entire layout, so our entire design smaller, so less wide. And so therefore we need this line of code which will make it so that the page will actually match the screen's width. So, thats what this one does here: content="width=device-width, initial-scale=1.0" (So, the width will be equal to the device width and the scale initially should be 100%. So, what that means is that it will not zoom out of the page to fit it on the screen).

   Selecting the breakpoint:
   We start from 1500px and checking where the design looks unacceptable also taking into account common screen width ranges. 

   We are going to make the hero container width same as other container width which is 1200px and that is because header seems to have much spacing on sides compared to hero section as the screen width reaches around 1300px. Now, there is an extremely common screen size at 1366px because these are the so-called HD-ready screens. So, we can choose some value between 1300px and 1366px.

   Particularity about media queries
   We should also not use pixels in media queries. And the reason is that using pixels will not adjust to the user's font size setting in the browser and also not to the user's zoom level.

   We should now use rem instead of pixels. However, there is one very, very important particularity of these responsive units in media queries which is the fact that they do not respond to the font-size setting in the html. In other words, in media queries, one rem is not 10px as we defined up in html. Instead, one rem will always be the default font size browser setting.

   And in media queries, we use em, which is current font size instead of rem because rem apparently has some bugs in some browsers when used in media queries. So, its safer to use em and it works exactly same as rem.

   Selected breakpoint: 1350px 
   And we need to convert this to em so we need to divide it by 16. So, we get 84.375 which we can round to 84em which is again 1344px.

   Once we implement the breakpoint, and changed the width of hero container, the primary heading switched from 3 lines to 4 lines. So, we decreased the font-size. Also now the gallery does not look good. So, changing layout from 3 cols to 2 cols. But the testimonials have much spacing around it. We will fix it later at some other breakpoint.

   /********** SMALLER LAPTOPS (Below 1344px) **********/
   @media (max-width: 84em) {
   .hero {
    max-width: 120rem;
   }

   .heading-primary {
    font-size: 4.4rem;
   }

   .gallery {
    grid-template-columns: repeat(2, 1fr);
   }
   }


2. Responding to Landscape Tablets
   
   Selecting breakpoint
   As we decrease down the viewport width, around 1100px we can see the text starts to increase one line. And some single line text has started to become double lines. One of the next breakpoint that we use commonly is 1200px, because that is where we start getting into mobile device territory. As said earlier, we shouldnt just base our breakpoints on the device width but also on where the design breaks. And in the case of 1200px, its not yet really visible that the design is breaking, atleast not in terms of the layout, but still everything is quite too big here. So everything looks like huge even at 1200px. 

   Selected Breakpoint: 1200px
   Lets start fixing that overall feeling that we have, that everything is too big. So, how can we do that? We can now finally use to our advantage the fact that we used responsive units from the very start. In fact, everything that we did in media query works because we already have the other three responsive web design ingredients already in place. So, we already have a fluid grid and responsive images and responsive units. Otherwise none of this would work at all.

   And so now lets make use of ingredient which is responsive units. We have been using rem all the time in css for most of the lengths. So, all of the lengths defined using rem are dependent on one setting right in the html. So, if we change that one setting inside html, then every single length and every single font size on the page will immediately change.

   @media (max-width: 75em) {
   html {
    font-size: 56.25%;
   }
   }

   Now, the entire design becomes bit small because of the power of sizing everything in rem and then changing that one setting. So, basically changing the definition of what one rem is right there in the media query.

   After changing the entire layout into bit smaller, still we can decrease font size of secondary and tertiary heading and gaps in the grid.

   And we are making the padding in header same as that of container so it looks aligned to the container.

   Also, hero is a seperate grid we created not a resuable grid we are changing the gap in the hero section as well.


3. Responding to Tablets
   
   Selecting breakpoint
   We introduced a breakpoint at 1200px for Landscape tablets (And so we fixed our design basically at that screen width). Of course a media query should not work at just one specific point. So, instead as a rule of thumb, it should work over a range of atleast 200 or 300px.

   On analyzing at around 900px, its time to move some of the sections into just one column.

   Selected breakpoint: 992px

   We will move the hero section just to one column and then it becomes essentially one of these other types of hero section where the content is on top and centered and then below that there is some image.

   We can basically set text-align to center even for the image content because an image is an inline element and so it is also affected by text align center.

   .hero-text-box,
   .hero-img-box {
    text-align: center;
   }

   We are going towards more narrow and less spacey layout. So, inside of the sample meals on adjusting viewport width the text becomes as double line. So, we need to remove lot of padding there.

   .meal-content {
    padding: 2.4rem 3.2rem 3.2rem 3.2rem;
   }


4. Building the Mobile Navigation
   Instead of showing the entire nav, now at this breakpoint we want simply to show the menu button and only once the user clicks the menu icon, we want to show the navigation to the user.
   
   Step 1:
   We want the menu button from the very beginning of the project. So, we want to place the menu icon in the html. And style the button and icon.

   <header class="header">
      <a href="#">
        <img src="img/omnifood-logo.png" alt="Omnifood logo" class="logo" />
      </a>
      <nav class="main-nav">
        <ul class="main-nav-list">
          <li><a class="main-nav-link" href="#">How it works</a></li>
          <li><a class="main-nav-link" href="#">Meals</a></li>
          <li><a class="main-nav-link" href="#">Testimonials</a></li>
          <li><a class="main-nav-link" href="#">Pricing</a></li>
          <li><a class="main-nav-link nav-cta" href="#">Try for free</a></li>
        </ul>
      </nav>

      <!-- Button added for mobile navigation -->
      <button class="btn-mobile-nav">
        <ion-icon class="icon-mobile-nav" name="menu-outline"></ion-icon>
        <ion-icon class="icon-mobile-nav" name="close-outline"></ion-icon>
      </button>
   </header>

   /* Mobile Navigation */
   .btn-mobile-nav {
   border: none;
   background: none;
   cursor: pointer;
   }

   .icon-mobile-nav {
   height: 4.8rem;
   width: 4.8rem;
   color: #333;
   }

   
   Step 2:
   We have placed menu and close icon inside the button. But by default, we only want the menu icon to appear and close icon to be hidden. Later, when the user clicks on the menu icon, we need to show the navigation and the icon needs to be switched from menu to close. We can simply do this by applying styles by giving seperate class names to both icons. But we are going to use new kind of selector here. Here both icons has the same classname, but the distinguishing feature of the icons are the name of the icon. So, in css we can select the elements based on attributes.

   .icon-mobile-nav[name="close-outline"] {
   display: none;
   }

   Note: What is the difference between display: none, visibility: hidden and opacity: 0 ?
   i.   display:none turns off the layout of the elements, so they are not rendered. 
   ii.  visibility:hidden hides the elements without changing their layouts. 
   iii. opacity:0 causes the elements to be very transparent but users can still interact with them.

   Step 3:
   Also, by default we dont want to show the menu icon. Because we show the entire nav and only at certain breakpoint the menu icon needs to be shown. So, we are going to make it hidden by default. And at certain breakpoint, we are going to make it visible.

   .btn-mobile-nav {
   border: none;
   background: none;
   cursor: pointer;

   display: none;
   }

   @media (max-width: 62em) {
   /* MOBILE NAVIGATION */
   .btn-mobile-nav {
    display: block;
   }
   }

   Step 4: Styling and creating a mobile navigation
   The mobile navigation will need to work for provided breakpoint and for all the other width that will come before. For eg, even on a small phone. So, what we are going to do is to basically overlay the navigation over the entire screen. So, creating like an overlay and then having the menu items displayed one after another vertically. ie. having all of the menu items on top basically of the page. And the way we are going to do that is to basically remove the entire nav element using CSS with absolute positioning.

   .main-nav {
    background-color: rgba(255, 255, 255, 0.97);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;

    display: flex;
    align-items: center;
    justify-content: center;
   }

   .main-nav-list {
    flex-direction: column;
    gap: 4.8rem;
   }

   .main-nav-link:link,
   .main-nav-link:visited {
    font-size: 3rem;
   }

   Step 5:
   We need to actually hide the mobile navigation that we positioned absolutely in a correct way. And also come up with basically a mechanism that we can use later in javascript to create the effect of showing and displaying the navigation. We will not be able to do that functionality with CSS alone. But what we can do is to already prepare everything and basically do that manually.

   First, we need to hide the mobile navigation by default. Can we do this using display: none? Yes, but the problem with this is when this is used on an element, we can do no animations. So, transitions will not work when we have display set to none. And so we will need to find a way around this. We can set opacity to 0 but this does not hide exactly. So, this is not just enough.

   .main-nav {
    background-color: rgba(255, 255, 255, 0.97);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;

    display: flex;
    align-items: center;
    justify-content: center;

    /* To hide navigation by default */
    /* Allows no animations at all */
    /* display: none; */

    opacity: 0;
   }

   Mechanism of hiding and displaying the navigation
   We want to add a class to the element that we wanted to be open. We will add a class to the header whenever the navigation is open.

   <header class="header nav-open">
   ....
   </header>

   nav-open  - So, this is the class that will be added and removed using javascript. And so whenever the navigation is open, nav-open will be present here on the header element. So this is a very very common technique when we build components like this, which need to change their state a little bit based on javascript later. So, later we will add simple javascript to add and remove the class depending on whether the user has clicked the navigation button or not.

   /* If the nav-open is present on the header, apply the style */
   .nav-open .main-nav {
    opacity: 1;
   }

   To hide the navigation properly without using display: none, opacity set to 0 is not enough. We need to do a couple of steps.

   /* 1. Hide the element visually */
    opacity: 0;

   /* 2. Make inaccessible to mouse and keyboard */
    pointer-events: none;

   /* 3. Hide it from screen readers */
    visibility: hidden;

   This is the correct way of hiding an element without using display: none.

   But then of course when we want to open the navigation, we need to set all of that back to normal.

   .main-nav {
    background-color: rgba(255, 255, 255, 0.97);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;

    display: flex;
    align-items: center;
    justify-content: center;

    transition: all 0.5s;

    opacity: 0;
    pointer-events: none;
    visibility: hidden;
   }

   .nav-open .main-nav {
    opacity: 1;
    pointer-events: auto;
    visibility: visible;
   }

   Step 6:
   What we want to do now is to actually change the menu icon to the close icon when the navigation is open.

   .nav-open .icon-mobile-nav[name="close-outline"] {
    display: block;
   }

   .nav-open .icon-mobile-nav[name="menu-outline"] {
    display: none;
   }

   Step 7:
   We could call it a day here and actually say that we are ready because this is already working quite nice. But we are going to add another really, really cool effect, which is to basically have the whole navigation come sliding in from the right side.

   How we could do that? We could move the entire nav completely out of the page, so basically to the right side of the screen. And then once the navigation becomes visible, then we slide that back in here. So, move in basically with some animation. And the way we can do that is by using transform property.

   .main-nav {
    background-color: rgba(255, 255, 255, 0.97);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;

    /* We want to move the navigation out of the screen completely at horizontal axis
    by its own width ie. 100% */
    transform: translateX(100%);

    display: flex;
    align-items: center;
    justify-content: center;

    transition: all 0.5s;

    opacity: 0;
    pointer-events: none;
    visibility: hidden;
   } 

   But now the problem is that we can now see it by scrolling to the right. But that is not what we want. The navigation should be really hidden on the right side and then simply move in.

   For that, we need to use yet another new property. And this is something that we always do actually when we build a page like this. That is, on body and on html, we will set the overflow-x to hidden. 

   html {
   /* font-size: 10px; */
   /* Percentage of browsers font-size setting */
   font-size: 62.5%; /* This is similar to setting 10px, because default font-size of browser: 16px and 10/16 = 0.625 which is same as 62.5%. And
   if the user changes the font size in browser it adapts automatically since we are using % */

   overflow-x: hidden;
   }

   body {
   font-family: "Rubik", sans-serif;
   line-height: 1;
   font-weight: 400;
   color: #333;

   /* This only works if there is nothing absolutely positioned in relation to body */
   overflow-x: hidden;
   }

   So, what this means is that all the elements that overflow the view port in the x-axis, so horizontally will be hidden.

   We moved the whole navigation to the right side using transform property, and we need to set it back basically to the initial state once the navigation is open.

   .nav-open .main-nav {
    opacity: 1;
    pointer-events: auto;
    visibility: visible;
    transform: translateX(0);
   }

   Its actually very important that we use transform property to do this animation because this is way more performant than, for eg, doing the same thing using the left property. So, we could also have used the left property to create this animation, but then the animation would not be as smooth as it should be. So, transform is a very, very common property that should be used for transitions because well, these kind of animations, they have been optimized by CSS for this property and a couple of others such as opacity.

   Note: We can specify third value in transition. ie. type of the animation. If we dont specify anything, then by default the transition is linear. But we can also specify like a transition curve which is how we call it. For eg, we can choose ease, ease-in or ease-out.
   ease-out  - animation will be little bit faster in the beginning and then slows down significantly.
   ease-in   - animation will be bit slower in the beginning and in the end it speeds up.
   ease-in-out - This makes animation fast in the beginning and in the end, and slows down a little bit in the middle.

   transition: all 0.5s ease-in;


5. Responding to Smaller Tablets
   Selecting the breakpoint
   Around 772px, the lines starts to increase in the design.

   Selected breakpoint: 773px
   We are going to make three column and four column grid into just 2 columns.

   .grid--3-cols,
   .grid--4-cols {
    grid-template-columns: repeat(2, 1fr);
   }

   Also, after changing grid into 2 columns the sample meals section that has the diet now looks aligned to the left. We need to center it.

   .diets {
    grid-column: 1 / -1;
    justify-self: center;
   }

   The spacing after the h2 starts to look huge and needs to reduce that.
   .heading-secondary {
    margin-bottom: 4.8rem;
   }

   We gave 75% of width to the pricing plan for the larger screen. And now we are giving 100% back so that it has more space for the content.

   .pricing-plan {
    width: 100%;
   }

   Change in footer
   We now want to change the footer grid such that nav columns are in the first row and logo and address column on the second row. Also, we want the nav col to have the same spacing and logo and address col to have the same spacing.

   First, trying to make it into 3-column grid. The problem with this is the nav-col can go into the first row and occupy the same space. But the logo and address col which goes into the second row occupies the space which makes it so that one cell is left behind. But we cant divide the remaining cell between the address col and logo col to have it the same size.

   So, the solution is we can now change the grid into 6-col grid and make it so that all nav-col span across 2 cells and logo and address col span across 3 cells so that it gets same size. Thats a trick that we actually have to do all the time when we build kind of an asymmetric grid.

   .grid--footer {
    grid-template-columns: repeat(6, 1fr);
   }

   .nav-col {
    grid-row: 1;
    grid-column: span 2;
    margin-bottom: 3.2rem;
   }

   .logo-col,
   .address-col {
    grid-column: span 3;
   }


6. Responding to Phones
   Many times for mobile we use media query at about 600px.
   From now on, we will have all the grids in just one column. Because we dont have enough space for multiple columns.
   Also, we need to dramatically reduce the gap vertically in the grid because we only have row gap now.

   .grid--2-cols,
   .grid--3-cols,
   .grid--4-cols {
    grid-template-columns: 1fr;
   }

   .grid {
    row-gap: 4.8rem;
   }

   Now, we need to remove lot of padding that we added in hero section for larger screen to look good because at smaller screen we want space for the content.
   .hero {
    padding: 0 3.2rem;
   }

   Regarding buttons, on mobile phones we need to make sure the buttons are big enough so that we can tap it easily on phone.
   .btn:link,
   .btn:visited {
    padding: 2.4rem 1.6rem;
   }

   For buttons, on top and bottom we have increased the padding compared to original and on right and left we have reduced.

   We are changing the image to be on top for how it works section for each of the steps.
   Instead of giving seperate classname for each image, making use of nth-child pseudo class.

   .step-img-box:nth-child(2)  /* Here, the order refers to the order of the child element in the parent container and it has nothing to do with classname. It doesnt mean it is referring to 2nd child which has the classname of step-img-box. It simply selects the 2nd child in the parent container which has the class name of step-img-box 
   */ 
   {
    grid-row: 1;
   }

   Now the space between the images and the step are ambigous. It has same spacing between the text and the images. So, we need to make the images has less spacing between its own step. We cant change the gap selectively because gap applies for the entire grid. What we can do here. We can select the image box and do the transform with tranlate here because it helps to move the elements around without affecting the other elements.

   .step-img-box {
    transform: translateY(2.4rem);
   }

   Now, we make the cta also a grid of 1 column. But then the background image disappears. Because its just a background image which doesnt have any content in html and so CSS does not give it a height. Before, the only reason why it was visible was because it was side by side with the cta form which had a lot of content. And so thats why it got the same height from there. So, if we want to make the image visible we need to provide height manually.

   .cta-img-box {
    height: 32rem;
    grid-row: 1;
   }
   

   
