1. Web Design Rules #10:  Part-1 Elements and Components
   
   From Elements to Webpage
   How an actual webpage is designed from scratch?
   When we want to start a new website, and start with an empty page, and all we have is the content, we might feel very lost. But we dont have to feel lost. It doesnt have to be hard because this is where well-established patterns come into play in order to help us. 
   
   Basically we build websites always in the same way. We start with some common small elements, like paragraphs, images, buttons which will contain our actual content. We then assemble these simple elements into common components such as feature-row, or a feature-card, or a pricing table or a tabbed component. Then we take all the components that we designed and use them to build a layout using common layout patterns. Finally, we take all the smaller layouts or just one big layout and assemble a final page from them. And in the end, this is how we come up with a final design. So, we can see there is in fact a system behind all this. So, a webpage is not just a bunch of random elements joined together. Instead, elements are organized into components, which are then organized into one or more layouts, which in the end make up a final webpage.
                                            
      Elements  -----------> Components  ------------->   Layouts  ------------------->  Webpage

   So, whenever we need to start a new design from a blank page, this is how we proceed. 
     1. Use common elements and components to convey our websites information.
     2. Combine components into layouts using common layout patterns.
     3. Assemble different layout areas into a complete, final page.

   Most common elements, components, section components, layout patterns that exist in web design and web development
   ELEMENTS
   1. Text
   2. Buttons
   3. Images
   4. Input elements
   5. Tags

   COMPONENTS
   1. Breadcrumbs                          10. Carousel
   2. Pagination                           11. Customer testimonials
   3. Alert and status bars                12. Customer logos
   4. Statistics                           13. Featured-in logos
   5. Gallery                              14. Steps 
   6. Feature box                          15. Forms
   7. Preview and Profile cards            16. Tables
   8. Accordion                            17. Pricing tables
   9. Tabs                                 18. Modal windows

   SECTION COMPONENTS
   1. Navigation
   2. Hero Section
   3. Footer
   4. Call-to-action section
   5. Feature row

   LAYOUT PATTERNS
   1. Row of boxes or cards
   2. Grid of boxes or cards
   3. Z-Pattern
   4. F-Pattern
   5. Single-column
   6. Sidebar
   7. Multi-column/magazine
   8. Asymmetry/Experimental



2. Accordion Component

   FEATURE NEW IN FLEXBOX:
   To create margin/space between each li elements, we can make use of flexbox. Normally, if we want to create space between li elements we would select all of them and apply margin-bottom except for the last one. Now we can do this in an easier way using flexbox and then setting the gap property. 

   Normally, if we apply flex to some container elements, all the child elements will be aligned side by side and if we apply gap property that will be applied horizontally between each child elements. But for the above case of applying space between each li elements, we can set display to flex and set flex-direction: column. So now the elements will not be aligned side by side but in the vertical direction. Also if we apply gap property between each elements then it is applied vertically.

   .hidden-box ul {
      color: #868e96;
      margin-left: 20px;

      display: flex;
      flex-direction: column;
      gap: 12px;
   }

   SWITCHING FLEX-DIRECTION TO COLUMN: HOW IT WORKS?
   In Flexbox, by default, the main axis is basically horizontally and the elements are side by side. And if there is gap property specified, there will be some space horizontally. However, if we set the flex-direction to column, the elements are stacked one after the other because the main-axis is rotated by 90 degree. And so now the main-axis no longer goes from left to right, but from top-to-bottom. Or in other words, the main-axis is now vertically and no longer horizontally. On the other hand, the cross-axis which used to be vertically, is now horizontally. And so now everything is different.
   Everything in flexbox has now turned by 90 degrees, basically.
   So, with flex-direction set to column: 
      a. align-items aligns item horizontally, no longer vertically
      b. justify-content aligns item vertically, no longer horizontally
      c. gap acts like margin-bottom, no longer like margin-right

   How to hide content in accordion and open if needed?
   We will use a very common trick that we use in CSS all the time, especially when we create these components that will at some point, have to work together with Javascript. So basically, we will by default, set the items to the default closed state. And then, we will add a special class to the item, which will then make it so that the item is open.

   1. First we are hiding the hidden-box by default

   .hidden-box {
      grid-column: 2;
      display: none;
   }

   .number,
   .text {
        font-size: 24px;
        font-weight: 500;
   }

   .number {
        color: #ced4da;
   }

   2. Adding a special class to the item that needs to be opened
   <div class="item open">
        <p class="number">02</p>
        <p class="text">How long do I have to return my chair?</p>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="icon"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="m19.5 8.25-7.5 7.5-7.5-7.5"
          />
        </svg>
        <div class="hidden-box">
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Corporis
            autem similique illum sapiente at cupiditate, temporibus alias odio
            doloremque id ab eveniet officiis neque, ipsum magni assumenda.
            Voluptatum, esse beatae!
          </p>
          <ul>
            <li>Lorem ipsum dolor sit, amet consectetur adipisicing elit.</li>
            <li>Consequatur itaque dolorem sapiente officia eius.</li>
            <li>
              Ab incidunt officiis minus quam esse aperiam repudiandae eum.
            </li>
            <li>Voluptatum, esse beatae!</li>
          </ul>
        </div>
   </div>

   3. Adding styles to special class
   .open {
        border-top: 4px solid #087f5b;
   }

   .open .hidden-box {
        display: block;
   }

   .open .number,
   .open .text {
        color: #087f5b;
   }


3. Carousel Component
   
   A new feature:
   To make an image to grow big/scale up : ie. instead of defining higher width and height we just want the image basically to stay in the same place and scale up the image.
   We can simply scale up the image by using brand new property which is called transform. So, transform is for many different things. And one of them is to scale elements.
   transform: scale(1.5); // We need to specify a value by which we want to scale.
   If we write 1, ie. scale(1), then the element will stay the same size.
   If we use 2, ie. scale(2), then it will double the size. 

   img {
        height: 200px;
        border-radius: 8px;
        transform: scale(1.5);
        box-shadow: 0 12px 24px rgba(0, 0, 0, 0.25);
   }

   We are placing an icon inside the button and providing height and width to both the button and the icon. But how to center the icon inside the button.
   Since icon is only the child element inside the button, we can use nice trick.

   .btn {
        background-color: #fff;
        border: none;
        height: 40px;
        width: 40px;
        border-radius: 50%;
        position: absolute;

        /* To center the icon inside the button */
        display: flex;
        align-items: center;
        justify-content: center;
   }


   A new feature:
   We need to basically absolutely position the button to the center of the parent container ie. it needs to be vertically centered in the carousel component. For that, we can use top property. 
   What if we specify top: 50%? We think 50% is half of the parent container and specifying top as 50% will automatically center the button inside the carousel. But it is not that happens. Only the start of the element starts from top: 50% of the parent container and it is not actually vertically centered. We need middle of the button element to be in the center ie. middle of the button element should be from top: 50%.
   For that we can use a brand new technique.
   We know top: 50% moved the entire element to 50% of the top of the parent container. ie. top of the button now starts from 50% of the carousel component. But we need middle of the button to start from 50% of the top of the parent container. So, this is where the technique of vertically centering with absolute positioning is done with the transform property. In this case, we use transform not with scale, but with translate.

   Translating:
   The translate basically move the element around. Here, we can specify the x value which is basically horizontally and y value which is vertically.
   transform: translate(0,-50%);  // This will basically move the element exactly 50% of its height back to the top. This 50% is of the actual elements height not of the parent container's height.
   Specifying -50% will make the element to move up because of the minus and it will move up by exactly 50% of its actual height. After doing this, the element will be completely vertically centered.

   We can also use translate not only vertically but also horizontally ie. in our case we want half of the button to be outside of the parent container ie. the middle of the button should lie in the transition. We now need to move the button horizontally.
   Specifying transform: translate(-50%, -50%); will move the element left because of minus and it will move by half of the size of the actual elements width.

   .btn--left {
        left: 0;
        top: 50%; /* Positioning the element in relation to the parent containers height */
        transform: translate(
          -50%,
          -50%
        ); /* Positioning the element in relation to itself */
   }

   .btn--right {
        right: 0;
        top: 50%;
        transform: translate(50%, -50%);
   }



4. Table Component
   Tables are actually not used a lot anymore in web development. Back in the day, tables actually used to be the first way in which developers built layouts. Now, with flexbox and CSS Grid, we have better ways of doing that. However, tables do still have a place in HTML, especially if we are really trying to represent some dataset that can be displayed using a table. And so, then the table is the most semantic way of doing that.
   
   <table> - element to markup a table
   <tr> - element to create a new row
   <td> - element to create a new data (ie. new data for each column in a row)

   We can mark first row as being special, ie. telling html that first row is the head of the table. And the rest of the content is the table body. So to do that, we can wrap the first row into the <thead> element. And wrap other remaining rows inside the <tbody> element.
   <thead>
        <tr>
          <td>Chair</td>
          <td>The Laid Back</td>
          <td>The Worker Bee</td>
          <td>The Chair 4/2</td>
        </tr>
   </thead> 

   <tbody>
        <tr>
          <td>Width</td>
          <td>80 cm</td>
          <td>60 cm</td>
          <td>220 cm</td>
        </tr>
        <tr>
          <td>Height</td>
          <td>100 cm</td>
          <td>110 cm</td>
          <td>90 cm</td>
        </tr>
        ...
   </tbody>

   Visually it still looks same as before. But semantically the table makes a lot more sense because its nicely divided into more logical sections.

   If we actually want the cell to look different, ie. if we want to mark it as an actual table head, we need to use a different element. Instead of using td, we use th, which is basically a table head cell. 

   <thead>
        <tr>
          <th>Chair</th>
          <th>The Laid Back</th>
          <th>The Worker Bee</th>
          <th>The Chair 4/2</th>
        </tr>
   </thead>

   <tbody>
        <tr>
          <th>Width</th>
          <td>80 cm</td>
          <td>60 cm</td>
          <td>220 cm</td>
        </tr>
        <tr>
          <th>Height</th>
          <td>100 cm</td>
          <td>110 cm</td>
          <td>90 cm</td>
        </tr>
        ...
   </tbody>

   
   Typical table formatting of adding zebra stripes - having alternating background colors which makes the table really easy to read and to scan
   
   tbody tr:nth-child(odd) {
        background-color: #f8f9fa;
   }

   tbody tr:nth-child(even) {
        background-color: #e9ecef;
   }


5. Pagination Component
   Note: Basically there is a circle around each of the links which then becomes green as we hover over it. What that means is that this circle actually needs to kind of exist already in the predefined link ie. in the state before the hover.

   .page-link:link,
   .page-link:visited {
        font-size: 18px;
        color: #343a40;
        text-decoration: none;
        /* To make it as a circle around the link */
        height: 36px;
        width: 36px;
        border-radius: 50%;
        /* display: inline-block;    Height and width wont work in inline element so set the display to inline-block. And since we are going to make use of flex to 
        basically align text inside the link center, we dont want to set this */

        /* To center the text inside the link we use the flexbox trick. At this point, the links get stacked one below the other and thats because basically by default a flex container is also something like a block element. Since, each of the page links is a flex container it takes its own line 
        */
        display: flex;
        align-items: center;
        justify-content: center;
   }

   .page-link:hover,
   .page-link:active {
        background-color: #087f5b;
        color: #fff;
   }


   When we hover over the button it needs to change its background to green and icon to white. How do we do that?
   .btn:hover {
        background-color: #087f5b;
   }

    /* We are telling here the icon should become white when we hover over the button */
   .btn:hover .btn-icon {
        stroke: #fff;
   }    /* right way of doing */

   .btn-icon:hover {
        stroke: #fff;
    }  /* We should not do this. This will make icon white only when we hover over the icon not over the button */


   We can use flexbox trick to center a component instead of using margin auto trick because margin trick works only when we provide defined width. But in some cases, the component does not have predefined width and in that case the margin auto trick wont works. So, in the body which is the parent container of all we can use the flexbox technique to center the component.
    
   body {
        font-family: "Inter", sans-serif;
        color: #343a40;
        line-height: 1;

        /* To make the pagination component to be at the center of the page - instead of using margin auto this is also one of the trick to center a component */
        display: flex;
        justify-content: center;
   }

   NEW AND IMPORTANT: NOTION OF SPECIFICITY
   Lastly we want to apply special style to a page-link to indicate that this is the active page selected.
    <a href="#" class="page-link">1</a>
    <a href="#" class="page-link">2</a>
    <a href="#" class="page-link page-link--current">3</a>
    <a href="#" class="page-link">4</a>
    <a href="#" class="page-link">5</a>
    <a href="#" class="page-link">6</a> 

    .page-link:link,
    .page-link:visited       /* Selector Specificity: (0, 2, 0) */ 
    {
        font-size: 18px;
        color: #343a40;
        text-decoration: none;
        /* To make it as a circle around the link */
        height: 36px;
        width: 36px;
        border-radius: 50%;
        /* display: inline-block;    Height and width wont work in inline element so set the display to inline-block. And since we are going to make use of flex to 
        basically align text inside the link center, we dont want to set this */

        /* To center the text inside the link we use the flexbox trick. At this point, the links get stacked one below the other and thats because basically by default 
        a flex container is also something like a block element. Since, each of the page links is a flex container it takes its own line 
        */
        display: flex;
        align-items: center;
        justify-content: center;
     }

     .page-link:hover,
     .page-link:active,
     .page-link--current      /* Selector Specificity: (0, 1, 0) */ 
     {
        background-color: #087f5b;
        color: #fff;
     }

   As a special styling for the active page, we want background color green and color white to be applied on the link. But if we code as above, only background color gets applied but color is not applied since that is being applied from the previous selector. This is because of the notion of specificity. 
   Specificity: Selector with the highest value of specificity gets highest priority. 

   Why .page-link:link and .page-link:visited has specificity of (0,2,0) ? because it has two classes, one the original class and the other pseudo class
   Why .page-link--current has specificity of (0,1,0) ? Because it is only single class

   To solve the above issue we can make use of and selector
   Instead of simply using .page-link--current to select the element, we can make use of and selector ie. .page-link.page-link--current. Two classes put together without any spaces to create higher specificity. This is different from descendant selector in which we leave spaces between two classes. Here no space is left since this is and selector. And selector works if an element contains both the classes.

     .page-link:hover,
     .page-link:active,
     .page-link.page-link--current    /* Selector Specificity: (0, 2, 0) */
     {
        background-color: #087f5b;
        color: #fff;
     }
     
   Now both have the same specificity but the above gets applied since this is the last on the code.


6. Building a Hero Section
   If we wanted to center a content inside header or section, instead of centering the whole header or section using margin auto trick, we can center only the nav or div or whatever holds content. By doing this, we are preventing the entire section to be centered because we only want content to be centered but if we have some background image or background color, that needs to go from side to side entirely in the view port.

   /* Utility class for centering the content */
      .container {
        width: 1200px;
        margin: 0 auto;
      }

      <header>
      <nav class="container">
        <div>LOGO</div>
        <div>NAVIGATION</div>
      </nav>
      <div class="container">
        <h1>A healthy meal delivered to your door, every single day</h1>
        <p>
          The smart 365-days-per-year food subscription that will make you eat
          healthy. Tailored to your personal tastes and nutritional needs
        </p>
        <a href="#" class="btn">Start eating well</a>
      </div>
      </header>

      <section>
      <div class="container">
        <h2>Some random heading</h2>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Obcaecati
          porro nobis natus sint ipsa incidunt maiores veniam iure suscipit
          corporis consequatur laboriosam, placeat pariatur facere adipisci
          eligendi illum a tempora! Lorem ipsum dolor sit amet consectetur
          adipisicing elit. Sit soluta accusantium vel adipisci labore.
          Cupiditate similique labore rerum odit perspiciatis sint soluta vero,
          culpa minus assumenda, vitae eos veniam suscipit.
        </p>
      </div>
      </section>
   
   IMPORTANT AND NEW FEATURE
   To make the header the entire height of the view port? Currently, the header only occupies the space that it requires for its content. So, what we need to do is to use a new unit which is called view port height.

   header {
        background-color: aquamarine;
        height: 100vh; /* vh - new unit which is view port height. 100vh means 100% of the available view port*/
   }

   This is a trick that we will use all the time.
   What if height: 50vh ? Then it would be exactly half of the view port.
   If height: 150vh ? Then it would be one and a half of the view port.

   There's also another similar unit, which is vw which stands for view port width. However, we dont need to use that and in fact we very rarely use that one because since all these are block elements, they will already occupy 100% of the available space by default.


   What if we want to vertically center the content inside the header but at the same time keeping the navigation bar at the very top ?
   Probably the first thing that comes to our mind is the flexbox. But that would not be the good fit in this case. Because declaring header as a flex and aligning items vertically will put the nav and the content side by side eventhough the content is centered. But we want nav to stay on the top of the page.

   There are multiple ways of achieving that layout. The one that we are going to use to vertically center the content is, using absolute positioning and then using the transform with translate function.
   Now we want to give it a different class name.

   <header>
      <nav class="container">
        <div>LOGO</div>
        <div>NAVIGATION</div>
      </nav>

      <div class="header-container">
        <h1>A healthy meal delivered to your door, every single day</h1>
        <p>
          The smart 365-days-per-year food subscription that will make you eat
          healthy. Tailored to your personal tastes and nutritional needs
        </p>
        <a href="#" class="btn">Start eating well</a>
      </div>
   </header>

   header {
        background-color: aquamarine;
        height: 100vh; /* vh - new unit which is view port height. 100vh means 100% of the available view port*/

        position: relative;
   }

   .header-container {
        width: 1200px;
        /* We want this to absolutely position in relation to header element, so header set to position: relative */
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
   }


   Next we want content which is centered only to occupy 50% of the space. So, we want to create another container to hold the content and make that container to be half of the width of the parent container which is being centered.
   
   <header>
      <nav class="container">
        <div>LOGO</div>
        <div>NAVIGATION</div>
      </nav>

      <div class="header-container">
        <div class="header-container-inner">
          <h1>A healthy meal delivered to your door, every single day</h1>
          <p>
            The smart 365-days-per-year food subscription that will make you eat
            healthy. Tailored to your personal tastes and nutritional needs
          </p>
          <a href="#" class="btn">Start eating well</a>
        </div>
      </div>
   </header>

   .header-container {
        width: 1200px;
        /* We want this to absolutely position in relation to header element, so header set to position: relative */
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
      }

      .header-container-inner {
        width: 50%;  // This width will be in relation to parent container
   }


   How to set a background image?
   background-image: url(hero.jpg); // Inside url, we need to specify the path in relation to the current file
   Since the image is huge, we only can see a part of it covering the header. What if we want to shrink the image so that the entire image is visible over the header? Fortunately for us, there is a nice and handy property which is called the background-size and set it to cover.
   background-size: cover;  // cover will figure out automatically the exact size the image needs to be to cover the entire element 

   header {
        height: 100vh; /* vh - new unit which is view port height. 100vh means 100% of the available view port*/
        position: relative;

        background-image: url(hero.jpg);
        background-size: cover; /* cover will figure out automatically the exact size the image needs to be to cover the entire element */
   }
 

   NEW AND IMPORTANT FEATURE
   How to make a background image darker so that the text can be readable?
   Doing this is bit harder. What we need to do is to basically create a stack of background images where the first background image is a gradient that is transparent.
   
   How it works?
   To create a gradient anywhere, we still use the background-image.
   background-image: linear-gradient(red, blue); // The gradient will go from red to blue. By default, it goes from top to bottom
   We can also change the direction
   background-image: linear-gradient(to right, red, blue);

   And so we need a linear gradient to make a background image darker.
   background-image: linear-gradient(rgba(36, 36, 36, 0.6), rgba(36, 36, 36, 0.6)), url(hero.jpg);
   This is kind of a stack where the gradient is on top of the background image.


7. Building a Web Application Layout
   We have used new HTML element which is called <menu>, for menu bar.
   So, whats the difference between nav and menu? The nav element is for a typical navigation of a site. So a navigation which contains a bunch of links which then points to other places in the application. menu, on the other hand, is actually for menu buttons in an actual web application. So, we use nav all the time. menu is only used when we build a web application.
   <main> - Used to display the main piece of content of the document 

   Creating a CSS grid container
   body {
        font-family: sans-serif;
        color: #343a40;
        font-size: 24px;

        display: grid;
        grid-template-columns: 80px 400px 1fr 250px;
        grid-template-rows: 80px 1fr;
  }

  As per our layout, we want our main email view to occupy all of the available space and others occupy the fixed width. Thats why we gave 1fr in one of the columns for the email view.
  Also, regarding grid rows, we sometimes do not actually define. But in this case, since we want to fill the entire screen we will basically do it here automatically in the rows. ie. we wanted the second row to go all the way to the end. However, the above alone will not work as expected. ie. the second row will not go all the way to the end. That is because, just like any other element, the body element does not magically occupy the entire space. It only occupies the place that it needs for its content. So how to fix this? We need the body to be as high as the view port. The solution is to set the height to 100vh.

  body {
        font-family: sans-serif;
        color: #343a40;
        font-size: 24px;
        height: 100vh;

        display: grid;
        grid-template-columns: 80px 400px 1fr 250px;
        grid-template-rows: 80px 1fr;
  }

  We wanted our nav to start from 1st row and go till the last row. And we want our menu to span from 2nd column until the last one.
  nav {
        background-color: #343a40;
        grid-row: 1 / -1;  // This starts from 1st row and ends at last one
  }

  menu {
        background-color: #7048e8;
        color: #fff;
        grid-column: 2 / -1;  // This spans from second column till last one
  }

  And the others will be aligned automatically.


  We have placed our buttons. The trash button should be moved all the way to the right side. How can we do that?
  We can use the technique of setting margin-left to auto.
  button:last-child {
        background-color: #d6336c;
        margin-left: auto;
  }

  We wanted our email section to use scroll if the content grows larger inside the section. So, for that we have a handy property
  overflow: scroll;

  section {
        background-color: #e9ecef;
        padding: 40px;

        overflow: scroll;

        /* To apply space between each of the email box */
        display: flex;
        flex-direction: column;
        gap: 40px;
  }

  But this does not work as expected because since flexbox is applied on each email box, flexbox allows to shrink elements if needed by default. So, each of the height of the email box is adjusted to avoid overflow since by default flex-shrink: 1 on flex-box. But we can disable this by setting it to 0.

  .email {
        background-color: #adb5bd;
        height: 96px;
        flex-shrink: 0;

        /* To center the text inside the email box, using flexbox technique */
        display: flex;
        align-items: center;
        justify-content: center;
      }

   This is only necessary since we have used flexbox otherwise scroll will be applied appropriately.
