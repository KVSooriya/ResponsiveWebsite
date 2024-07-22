1. Some common properties for text: 
     font-size: 26px;
     font-family: sans-serif;
     text-transform: uppercase;
     font-style: italic;
     text-align: center;
     line-height: 1.5;

2. Combining selectors
    i. list selector - We can combine multiple selectors if we want to apply the same property or style to multiple elements
    ie. h1, h2, h3, h4, p, li { font-family: sans-serif; }

    ii. descendant selector - We can specify the element to which the style should be applied by specifying descendant
    ie. footer p { font-size: 16px; } - apply style to paragraph which is inside the footer
        article header p { font-style: italic } - apply style only to paragraph inside the header which is inside the article element

3. Comparing whether to use id and class? Which one is preferred?
    Assume we want to remove the bullets for a particular unordered list. If we then use id to name that ul, and used id selector to apply 
    style for that, in case if we wanted to do the same for another unordered list, we either need to create another id for that since id should not be repetitive in html, or we then need to change the existing unordered list to now use class instead of id. So, to prepare for the future we can use class to name elements instead of id. 

4. Colors in css 
   We can use rgb function to specify colors or hexadecimal notation. Most commonly used hexadecimal and when we need tranparancy, we can use
   rgb function. 
   Special note on gray color: When colors in all 3 channels are the same, we get a shade of gray color. Eg: rgb(69,69,69) / #444444 / #444
   and rgb(183,183,183) or #b7b7b7. #444 is the shorthand notation for #444444. 
    CSS properties that require color: color, background-color, border

5. Pseudo class
   A pseudo class starts with selector:pseudo class.
   Eg: li:first-child {font-weight:bold} - This will apply styles to first li child of the parent container. 
   li:nth-child(even) - This will apply styles to even li child of parent container. This technique is quite useful, for eg to style tables, 
   which oftentimes have like alternating background colors.

   Common misconceptions we have around pseudo classes - Let's say we want to select first paragraph element that's inside of the article
   article p:first-child {
   color: red;
   }
   By writing like above, the common misconception is to select the first p child under the article. But it will select the p element
   only if it is the first-child of the article element itself. In our case, the first-child of article is header element. 
   Note : If we mix multiple elements inside of a parent element, then these pseudo classes dont work really well. These pseudo classes
   like first-child last-child nth-child() are however perfect for situations like ol or ul where all the child elements are same ie. li

   This works because it selects the paragraph element if it is the last child of the article and it is, in our code.
   article p:last-child {
   color: red;
   }

6. Pseudo class for the hyperlink - a:link, a:visited, a:hover, a:active - These four states are always defined in this order (LVHA)

7. Devtools 
   When we inspect an element in chrome devtool, we can notice something called user agent stylesheet which is the predefined css styles applied to html elements.
   A user agent stylesheet is a pre-defined set of CSS rules that are built into a web browser and applied to web pages automatically. The purpose of the user agent stylesheet is to provide a consistent and standardized visual rendering of HTML elements across different web pages and websites.

8. CSS Theory#1: Conflicting between selectors
   Highest priority to lowest priority
   1. Declarations marked !important - not recommended
   2. Inline style (style attribute in html) - not recommended
   3. ID (#) selector
   4. Class(.) or Pseudo class(:) selector 
   5. Element selector
   6. Universal selector (*)

   If there are multiple rules under the same category, then the last rule in code applies.

   Eg: 
   <footer>
      <p id="copyright" class="copyright text">
        Copyright &copy; 2027 by The Code Magazine.
      </p>
    </footer>

    /* Resolving conflicts */
    #copyright {      This has the hightest priority since the id selector
    color: red;
    }

    .copyright {
    color: blue;
    }

    .text {           Both copyright and text are under the same category, class selector but the last one in code applies which is yellow
    color: yellow;
    }

    footer p {       This has the lowest priority compared to others since element selector
    color: green;
    }


9.  CSS Theory#2: Inheritance and the Universal selector
    Inheritance is the mechanism by which some styles, some properties get their values inherited from parent elements to child elements. The inherited styles are easily overwritten whenever there is any rule that applies for the same property. In a sense, we can say that inherited values are the ones who have the lowest priority.
    Imp Note on inheritance: 
    1. Inheritance is really elements inheriting values for certain properties from one another. So, this is not conflicting selectors, or in other words, for eg: in our code the body selector is not selecting all of the elements. ie. it does not apply to all the elements. Instead, the properties simply get passed down to all the child elements that are contained within the body.
    2. Many styles do actually not get inherited because that would be very impractical for most of the properties. Eg: border property inside
    the body selector

    Universal selector (*)
    Universal selector simply selects every single element on the page. And so this is useful if we actually want a certain property applied to all elements. Eg: If we wanted border on all the elements, we can specify using universal selector. The universal selector is actually quite important.
    * {
        border-top: 10px solid #1098ad;
    }

10. CSS Theory#3: The CSS Box Model
    What exactly is the box model? Well, the box model defines how elements are displayed on a webpage and how they are sized. In this box model, each and every element on a webpage can be seen as a rectangular box and each of these boxes can have content, a border, and space inside and outside of it.
      Content: Text, images, table, vedio etc ..
      Using css property, both the height and the width of the content area can be specified. 
      Next we can define a border, that goes all around the element. This border is technically still inside of the element.
      Padding is basically invisible white space that we can create around the elements content. ie. between the content and the border. Just like the border, padding is also still inside of the element. Padding is the empty space that we can create inside of the elements.
      Margin creates empty space around the elements.
      Fill Area: Area that gets filled with background color or background image (unlike content like text, images, table ..) which also includes the padding and the border.
    

11. Phenomena of Collapsing margin : 
    Let's say we have two elements one after the other. The top element has the margin bottom of 15px and the second element has margin top of 40px. What do we think of space/margin between these two elements. Will it get added? 15+40 = 55. No, instead it shares the space and takes the margin with the highest value ie. 40px and this phenomena is called Collapsing margins. ie. When we have two margins that occupy the same space, only one of them is actually visible on the page. And that is usually the larger of the two.
    Recap on margins and paddings: Whenever we need some space inside of an element, which is very useful mostly when there is a background 
    color or a border on the element, then we always use padding. In order to create space outside of an element, or also to create space 
    between multiple elements, always use margin.

12. Specifying dimensions (height and width)
    Consider the main-header. If we specify height as 80px, the complete final size of the element is actually not the 80px. But it is 
    80px (content), 20px and 20px (for top and bottom padding), which is 120px.This is the default behaviour of the box model. Also, the content inside the header doesnt get vertically centered inside of this header element. Before it was vertically centered as we had added same padding at the bottom and top. And after changing height, it is not vertically centered. The space in bottom is not same as space in top. We can change this.

    Specifying dimensions for images:
    It is common to specify height and width in CSS than to specify in HTML. The width and height in CSS overrides the properties in html. 
    Also, if we just specify the width and didn't specify height in css, then the height in html property is considered. So, to avoid this 
    and to adjust it to the aspect ratio, we mention height as auto in CSS.
    Note: Specifying the height and setting it to auto is only necessary if that height is already specified before in html.In case we dont
    specify any dimensions in HTML, then if we set the height or width using CSS, the other one will automatically adapt in order to account for the original aspect ratio of the image.

    Using % moving from px:
    Let's say width: 100%. Usually for a width measurement like this, the percentage is usually the percentage of the width of the parent container. What's special about this? As we change the size of the window, then the size of the image will always stay at 100%. It is because as we change the size of the parent container, then the size of the image would also adapt. It will be important when we start building responsive websites (websites that adapt to the screen width).

13. Centering our page
    What if we wanted to center our page to the browser. We can enclose all the element inside a parent container .. let's say div, and style it with css such that all the elements are aligned to the center of the browser.
    <body>
    <div class="container">
      .....
    </div>
    </body>

    .container {
        width: 700px;  /* At this point, since container is the parent container for all other elements, now all child elements will be 700px. 
        This is not something related to inheritance. The thing is child element cant be wider than the parent container. */
        margin-left:auto;
        margin-right:auto; /* What the two lines of code mean? Margin on the left needs to be the same as margin on the right side and they both should be calculated automatically by the browser. Therefore, this will mean that there will be a margin on the left and on the right side which will be exactly the same size, and therefore as a result the container will look centered inside of the body.So, basically inside of the browser. */
    }

14. CSS Theory#4: Types of boxes
    i.   Block-level elements
    ii.  Inline elements
    iii. Inline-block elements

    Block level elements 
        Elements are formatted visually as blocks
        Elements occupy 100% of parent element's width, no matter the content
        Elements are stacked vertically by default, one after another
        The box model applies as showed earlier.
        Eg: body, main, header, footer, section, nav, aside, div, h1-h6, p, ul, ol, li etc ..

        CSS property: display: block;

    Inline elements
        Occupies only the space necessary for its content
        Causes no line-breaks after or before the element
        Box model applies in a different way: heights and widths do not apply 
        Paddings and margins are applied only horizontally (left and right)
        Eg: a, strong, em, button etc ..

        CSS Property: display: inline;

    Inline-block elements
        Looks like inline from the outside, behaves like block-level on the inside
        Occupies only content's space
        Causes no line breaks
        Box-model applied as shown
        Eg: img

        CSS Property: inline-block

15. CSS Theory#5: Absolute Positioning
    Normal flow vs Absolute Positioning

    Normal flow:
    Default positioning of elements on our page
    Element is in flow
    Elements are simply laid out according to their order in the HTML code

    CSS Property: position: relative;

    Absolute positioning:
    Basically allows us to absolutely position elements anywhere on the page
    In this case, element is removed from the normal flow: "out of flow"
    The element completely loses any impact on surrounding elements and in fact it might even overlap them
    To actually position the element that is absolutely positioned, we can use the top, bottom, left or right properties in order to position that element and that positioning is going to happen in relation to a relatively positioned container.
    
    CSS Property: position: absolute;

    By default, the absolute positioned element is positioned based on view port (ie. visible part of the page). But that is usually not what we want. Usually we want to absolutely position the element in relation to some other parent element. To do that, we need to specifically set the position of that parent element to relative.

    Eg: To absolutely position based on parent element body 

    body {
       color: #444;
       font-family: sans-serif;
       border-top: 10px solid #1098ad;
       position: relative;
    }

    button {
        font-size: 22px;
        padding: 20px;
        cursor: pointer;

        /* Absolute positioning */
        position: absolute;
        /* top: 50px;
        left: 50px; */
        bottom: 50px;
        right: 50px;
}

    Note: We can also position the button inside of any other parent element, which is not the body. If there are multiple elements set to relative then button is absolutely positioned in relative to the first/enclosing/nearest parent element that has position set to relative.

16. Pseudo elements
    Nice little CSS feature
    Pseudo elements are essentially, elements that dont exist in the HTML but that we can still select and style in CSS.
    Eg: first letter of paragraph/heading or first line of paragraph or some other text

    The pseudo element is written using two colons ::

    /* Pseudo elements */
    h1::first-letter {
    font-style: normal;
    margin-right: 5px;
    }

    /*selects first letter of h2 and applies style
    h2::first-letter {
    font-size: 80px;
    }

    /* selects first-line of all paragraph and applies the style
    p::first-line {
    color: red;
    } */

    Adjacent element selector/Adjacent sibling selector
    So, a sibling element is basically an element that is part of the same parent. Adjacent sibling is a sibling that is actually the very next element.

    /* This + selector is an adjacent sibling selector. So, this basically selects the p element which is next to h3 and applies style to the first-line of the paragraph */
    h3 + p::first-line {
    color: red;
    }

    Most used and most important pseudo element - before and after
    after pseudo element creates a pseudo element that will automatically be the very last child of the selected element. This can be very useful for some small cosmetic style for which we dont want to necessarily add a new element to the HTML.
    Eg: In our code, the yellow highlighted TOP is the pseudo element for h2 and it is absolutely positioned relative to h2

    h2 {
    position: relative; /* We are setting h2 element to be relative so that we can position h2::after (pseudo element absolute to h2) */
    }
    /* Most used and most important pseudo element - before and after */
    h2::after {
    content: "TOP"; /* Even if we dont want any text in our pseudo element, we still have to define the content property with "" */
    background-color: #ffe70e;
    color: #444;
    font-size: 16px;
    font-weight: bold;
    display: inline-block; /* By default, any pseudo element is an inline element. So, to give padding we need to set display to inline-block */
    padding: 5px 10px;
    position: absolute;
    top: -10px; // Use case of negative length
    right: -25px;
    }

    Difference between after and before pseudo element: after will basically become the very last child element of the one we are selecting while before will become the very first child element.