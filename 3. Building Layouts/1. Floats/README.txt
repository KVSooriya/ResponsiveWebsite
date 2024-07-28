1. Using Floats
   .author-img {
   float: left;
   }

   With this, the image is basically going to be taken out of the document flow just like an absolutely positioned element. The difference here with floats is that then all the other elements will basically float around it.

   If we now set,
   .author {
   padding-left: 10px;
   }

   Nothing actually happens, this is because the element itself actually does not start right where the text is but it does, in fact, right behind the image. If we add a lot more padding, then only atleast the changes are visible because only then it is started moving out behind that image.

   How we can actually fix the fact that p element which is the one with the class="author" basically starts right at the beginning of the container. So, behind the image. So, what we can do is to make the element float as well.
   .author {
   padding-left: 60px;
   float: left;
   }

   And then the element starts right after the floated image. This all may seem and sounds weird but this is all how floats work.

   Next, we want heading to be floated on left side and nav links on the right side.
   h1 {
   float: left;
   }

   nav {
   float: right;
   }

   This will create an interesting phenomena. The interesting thing that happens with this is, if we notice the gray background it gets changed. If we inspect, the main header element is kind of lost its height. Also, in fact the only reason why gray background is still visible is because we have some padding. So, if we remove the padding, then the element would disappear completely (well atleast the background color behind it). Why is this happening? Well, the reason is that all of its child elements (of the main-header), which are in this case only two (h1 and nav), are floated. This means that its as if these elements would not even be on the page. So as if they had been removed. And so now the element basically has no content anymore. And that way it makes sense that its height is actually zero. This phenomena is what we call the collapsing element and when this happens, we say that the element's height has collapsed. And again, this happened because both of its children are now floated. We can actually fix that (next).

   Absolute Positioning vs. floats
   When an element is floated, it is removed out of the normal flow. And so in this regard, it is exactly the same as with absolute positioning. What different about floats is that floated elements do still have an impact on surrounding elements. So, text and inline elements will actually wrap around the floated element. One important characteristics of float is that the container element will simply not adjust its height to the floated element.

2. Clearing Floats
   How to fix the collapsing element? We can do it in two ways.
   1. We can create an empty div as another child element of main-header element where the height is collapsed and clear the float in the empty div using property clear:both;

   index.html
   <header class="main-header clearfix">
        <h1>📘 The Code Magazine</h1>
        <nav>
          <a href="blog.html">Blog</a>
          <a href="#">Challenges</a>
          <a href="#">Flexbox</a>
          <a href="#">CSS Grid</a>
        </nav>
        <div class="clear"></div>
   </header>

   styles.css
   .clear {
   clear: both;
   }

   The problem with this approach: Earlier, float was used for building layouts and this issue is very common so we have empty divs all over the html page just to fix this collapsing height

   2. Then an popular approach came which is clearfix hack and then it is used widespread. The idea is to create psuedoelement instead of creating empty div in html.

   .clearfix::after {
   content: "";
   clear: both;
   display: block;
   }

   Instead of creating empty divs in html, we can create a psuedoelement which creates an element similar like as we have an element inside the main-header and apply property of clear:both on that element. after is the pseudoelement which essentially creates the very last child element for the specified element. Also, clear works only on block elements and since psuedoelements are by default inline elements we explicitly need to set the display to block.

3. Building a simple Float layout
   Then placing article and aside side by side.
   Total width of the container: 1200px;

   article {
   float: left;
   width: 825px;
   }

   aside {
   float: right;
   width: 300px;
   }

   Also some padding is created inside aside. 
   aside {
    padding: 50px 40px;
   }

   Now, because of the default behaviour of box model, the total width is calculated as 
   width = border left + padding left + actual width + padding right + border right. This causes the aside to have actual width of 300 plus 40 and 40 px right and left padding added on top of that. But we can change this default behaviour of box model which does not make sense.


4. box-sizing: border-box; 
   By specifying this on universal selector, this property is applied to every single element. This changes the default behaviour of box model so now the width of the entire element is only the actual width we specify in css. Paddings are not added on top of that. Of course, the width of inner content is adjusted based on paddings. But it of course not a problem. 

   * {
   margin: 0;
   padding: 0;
   box-sizing: border-box;  // This will apply then to every single element on the page
   }

   Something like this is what most developers actually add to their CSS. So, a simple global reset and then basically enabling this better behaviour of the box model on every single element. 