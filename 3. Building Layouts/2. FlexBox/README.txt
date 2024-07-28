1. Introduction to Flexbox
   All we have to do in order to get started with Flexbox is to use the display property and set it to flex on some container element. And with container element, it mean any element that has a couple of child elements. Then all the elements will be side by side without having to use any floats or anything like that. And the child elements, we call them the flex items because they are the child elements of the flex container. Then each of the child element occupies exactly the space that it needs for its content.

   .container {
    display: flex;
   }  

   Horizontally, each of the element takes up exactly the space that is necessary for its text content. However, vertically things are a bit different. So, vertically by default, all the flex items are as tall as the tallest element.

   In order to demonstrate how powerful Flexbox can be, we can see by one of its most useful applications which is vertical centering. So, to basically center all these items vertically, say align-items: center. And indeed, they are vertically aligned just as expected. The flex container still takes the height of the highest element but all the other ones simply take the space that they need for the content and then they get vertically aligned in the center. To put them at the very start we can use align-items: flex-start, and to put them at the bottom we use align-items: flex-end. And by default, the value of align-items is stretch. So stretch essentially means that all the elements will automatically stretch as tall as the tallest element. The most important applications of Flexbox is however, vertical centering ie. align-items: center. But how hard it would be to do this without Flexbox. So we would have to manually select each of the elements and then try to guess some margin at the top so that they then looked align in the center. But here it all happens automatically. 

   And we can also center them horizontally. So basically center all of the items inside of the flex container. So, we do that with justify-content: center. It also gives a couple of other really helpful and nice options. eg: justify-content: space-between. Now the remaining space is now distributed evenly between all of the other elements. Basically they will have the space which is the same between all of them.


2. A Flexbox Overview
   Flexbox is a set of related CSS properties that we can use to build one-dimensional layouts.
   The main idea behind it, was to basically allow browsers to automatically divide empty space inside some container element, by its child elements. And by doing that, the browser take away a lot of work that previously the web developers had to do like manually defining width, margin and stuff like that.
   Also Flexbox makes it extremely easy to automatically align items to one another inside a certain parent container. And that is true both horizontally and vertically.
   Flexbox solves a couple of very common problems in CSS development such as vertical centering and also creating equal height columns. So, these used to be hard problems before Flexbox came along. But now with modern CSS, these are very, very simple to solve.
   Flexbox is perfect for replacing the old school float, and by that it allows us to write fewer and also cleaner HTML and CSS codes which of course is very easy to maintain websites over the long run and to write less bugs.

   Flexbox Terminology
   The element on which we want to use Flexbox is called the flex container. In order to create a flex container, set its display property to flex, and thats it. Thats how we get started with flexbox. If we do this, then all the direct children of that flex container will become the so-called flex items. We will use different properties on the flex container and on the flex items. 
   The direction in which these flex items are laid out is called the main axis. Then the other perpendicular axis is simply called the cross axis. And we can actually change the direction of the main axis, and so therefore also of the cross axis.


   Properties:
   Related to Flex container

   The first value is the default value and the other ones are the possible options that we can specify

   i.   gap: 0 | <length>
        To create space between items, wihout using margin
   ii.  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly
        To align items along main-axis (horizontally, by default)
   iii. align-items: stretch | flex-start | flex-end | center | baseline
        To align items along cross-axis (vertically by default)
   iv.  flex-direction: row | row-reverse | column | column-reverse
        To define which is the main axis
   v.   flex-wrap: nowrap | wrap | wrap-reverse
        To allow items to wrap into a new line if they are too large
   vi.  align-content: stretch | flex-start | flex-end | center | space-between | space-around
        Only applies when there are multiple lines (flex-wrap: wrap)

   Related to Flex items

   i.   align-self: auto | stretch | flex-start | flex-end | center | baseline
        To overwrite align-items for individual flex items
   ii.  flex-grow: 0 | <integer>
        To allow an element to grow (0 means no, 1+ means yes)
   iii. flex-shrink: 1 | <integer>
        To allow an element to shrink (0 means no, 1+ means yes)
   iv.  flex-basis: auto | <length>
        To define an items width, instead of the width property
   v.   flex: 0 1 auto | <int> <int> <len>
        Recommended shorthand for flex-grow, -shrink, -basis
   vi.  order: 0 | <integer>
        Controls order of items, -1 makes item first, 1 makes it last ..

3. Spacing and aligning flex items
   Basically using align-items on the flex container will make it so that all the flex items will have the same alignment. However, in many situations, we want to override that for one single element. So, for that we use the align-self property. So, this is one of the most important properties that we can use on flex items.
   .el--1 {
        align-self: flex-start;
    }

    .el--5 {
        align-self: stretch;
    }

    Changing the order in which flex items are displayed on the page can be very helpful when we are adapting a bigger layout to a small layout for mobile screens. Now, the default value for all elements is always 0. And if we want to move an element to the very first position, all we need is to specify a number that is lower than that. If we want to move an element to the back, we need to specify a value that is larger than 0. And if we want another element to be even last then we simply need yet another number that is even larger.

    .el--1 {
        align-self: flex-start;
        order: 2;
    }

    .el--5 {
        align-self: stretch;
        order: 1;
    }

    .el--6 {
        order: -1;
    }

    Many times we are interested in manually defining space between our flex elements. And so there are two ways currently of doing that.
    i. Original one was simply to add margin to the flex items. However, in order to get this right, we would then have to go in and remove the margin right from the last element, which can be a bit of a pain.
    .el {
        margin-right: 40px;
    }
    ii. Its way nicer to have the definition of a gap between these elements right in the container. So then we have basically all the definitions of how the flex items look like right there in the container element. And so, therefore a new property was added to Flexbox, which is called gap.
    .container {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 40px;
        margin: 40px;

        /* FLEXBOX */
        display: flex;
        align-items: center;
        justify-content: flex-start;
        gap: 40px;
    } 


4. The flex property
   Flex property is the property that we use in order to actually size flex items.
   Defaults:
    flex-grow: 0;
    flex-shrink: 1;
    flex-basis: auto;

   Use of flex-basis
   When we want to size flex items and in particular with a width, then we usually do not use the width property but instead we use flex-basis. Let's say we want the elements to have a width of 100px. ie. flex-basis:100px; Some elements may fit into 100 px but when the content is larger than 100px, then the element actually extends to fit that content. ie. beyond 100px. So what that means is that flex basis is not really rigid. So its more like a recommendation that we make to the browser, but the browser will then based on the content, figure out the optimal length.

   Use of flex-shrink
   And what if we make the flex-basis really big? ie. flex-basis: 200px; There is chance that flex items may not fit into the entire container. To avoid this, by default flex box is allowed to shrink elements so that they fit the container. And so thats what the flex-shrink set to 1 by default. So again, if there is not enough space in a container to fit the items with the size that we describe using flex-basis then flex box is allowed to shrink these items by default because flex-shrink is set to 1. However, if we want to change that, which sometimes we might want then we can simply set it to 0 ie. flex-shrink:0; But then of course the content might no longer fit the container. So setting flex-shrink:0 is not always advisable, but in some situations its necessary (we will come across in omni-food project). 

   Use of flex-grow
   flex-grow determines whether the elements are allowed to grow as large as they can or not. And in this case, it actually doesnt make sense to have the flex-basis. When this is set to 1, ie. flex-grow: 1, then all of the element would grow to fill up the entire container.
   .el {
        /* margin-right: 40px; */
        flex-grow: 1;
    }
    
   If we set it back to 0, ie. flex-grow: 0, then each of the element would simply be back to occupying the width that they need to fit the content. But again, if it is set to 1, then all the remaining space in the container is basically evenly divided by all of the remaining elements. It wouldnt even have to be 1, what matters is that they are the same number applied on all elements. ie. flex-grow: 5;
   How flex-grow works?
   i. What happens if actually only one of the element's flex-grow is set to 1?
   Well then that element only be allowed to fill up all the remaining space. And the remaining elements will stay with the size of the content.
   ii. What if all the elements are set flex-grow to 1 and one of them is set to 2?
   Then that element would get double of the remaining space than the other one. Note: It doesnt mean it'll get double the size, it gets double of the available empty space than the other ones. And even if we set it to something bigger, then it would get an even bigger portion of the remaining space.
   But usually we simply set flex-grow to 1 on all of the flex items because that is something very usual that we want. So, basically having all of the elements expanding in order to fill the empty space. 

   flex property:
   We can use flex which is a shorthand for above three. The flex property is actually pretty smart.
   Eg: We can simply set it to 1 ie. flex: 1 and then it'll automatically figure out that this means that flex-grow should be 1. Usually we dont use flex-grow but simply use flex property which is the preferred way. So, as a best practice we should never use one of the three above individually but always use the flex property. 
