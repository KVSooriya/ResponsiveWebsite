1. Introduction to CSS Grid
   CSS Grid, right now, is the most modern way of building layouts and its also the most complete one. It is even the easiest way of building layouts, atleast if we use only the fundamentals.
   Just like in flexbox, we have flex containers and flex items. In CSS Grid, we have grid container and grid items. Its a very similar logic. In order to declare grid container, we need display and set it to grid. And thats it. Visually that changes nothing because we need to actually define our two dimensional layout. So, basically all columns and all rows. We use the property called grid-template-columns and here we can define as many width values as we want. And then, for each of these values, one column will be created.

   .container--1 {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 40px;
        margin: 40px;

        /* CSS GRID */
        display: grid;
        grid-template-columns: 250px 150px;
   }

   The above code will generate two columns, one with a width of 250px and another one with a width of 150px. So, as soon as we start creating some columns then all the elements will be displayed in columns and rows. And so, as many rows will be created as necessary to accomodate for all the content. Just like in flexbox, the elements stretch across the entire cell. If an element has more height than the others in a row, then the entire row will have that height in order to accomodate for that height. ie. all of the elements will then stretch as far as they need to basically fill that entire row.
   
   Of course, we can also size the rows to make them tall as we want. We can size the row using property grid-template-rows
   grid-template-rows: 300px 200px;
   So, the first row will get the height of 300px and second will get 200px.  

   Note: Actually all we need would be the columns. And if we then want to also define the rows, we can do that by giving them an explicit height.

   Just like in flexbox, we can also specify a gap in CSS grid. And actually this is the only way of defining space between the grid items. So, always use gap and never margin. That is simply not going to work.
   gap: 30px;   // This creates a gap between both the columns and the rows
   This property actually used to be called grid-gap but they dropped the grid prefix when they also added gap to the flexbox. grid-gap is exactly same as gap and it still works in browsers.
   We can also specify seperate values for the column and for the rows.
   column-gap: 30px;
   row-gap: 60px;

   .container--1 {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 40px;
        margin: 40px;

        /* CSS GRID */
        display: grid;
        grid-template-columns: 250px 250px 150px 150px;
        grid-template-rows: 300px 200px;

        /* gap: 30px; */
        column-gap: 30px;
        row-gap: 60px;
   }

2. A CSS Grid Overview
   CSS Grid is a set of CSS properties that web developers can use to build 2-dimensional layouts.
   The main idea behind it was that now we could divide a container element into rows and columns that we could then fill with its child elements. And a lot of stuff is possible here. So things like spanning elements across multiple rows and columns, overlap different elements and more.
   We use CSS Grid in 2-dimensional contexts where it allows us to write a lot less nested HTML and also easier-to-read CSS.
   CSS Grid completely changes the way that we envision and build 2-dimensional layouts with CSS.
   One Common misconception that many have is that CSS Grid is meant to replace Flex Box. However that is not the case. So, instead Flex Box and CSS Grid work together perfectly. We simply use them in different situations. So, when we need a 1-dimensional layout, then we can simply reach for FlexBox. But if we need a 2-dimensional layout, then we can use a CSS Grid.

   Basic CSS Grid Terminology
   The grid container is basically where everything happens and we create a grid container by setting it to display:grid. Then all the child elements of the grid container will be the grid items. Then also like FlexBox, we also have axis here. We have a row axis and a column axis. Now unlike flex box, we cannot change the direction of the row and column axis.
   More CSS Grid Terminology
   Grid lines - lines which basically divide up the grids and seperate the columns and the rows. The grid lines are numbered from 1 to number of columns + 1 and the number of rows + 1. And these numbers are actually important because we can use them to place a grid item exactly in one place in the grid where we want it to be.
   Grid cells - The intersection of all these grid lines, creates the areas in which we can place our grid items. And these areas are called the grid cells. So, grid cells are always created but they dont always needs to be filled.
   Gutters - We can actually create spaces between the grid items and these are then called gutters or gaps. For that, we can use the gap/column-gap/row-gap property. Technically, these are actually called gutters.
   Grid track - A grid track can be a row or also a column.

   Properties:
   Related to Grid container

   The first value is the default value and the other ones are the possible options that we can specify.

   1. grid-template-rows : <track size>*
      grid-template-columns : <track size>*
      To establish the grid row and column tracks. One length unit for each track. Any unit can be used, new fr fills unused space.

   2. row-gap: 0 | <length>
      column-gap: 0 | <length>
           or
      gap: 0 | <length>
      To create empty space between tracks

   3. justify-items: stretch | start | center | end
      align-items: stretch | start | center | end
      To align items inside rows/columns (horizontally/vertically)
   
   4. justify-content: start | center | end ..
      align-content: start | center | end ..
      To align entire grid inside grid container. Only applies if container is larger than the grid.

      Related to Grid items

   1. grid-column: <start line> / <end line> | span <number>
      grid-row: <start line> / <end line> | span <number>
      To place a grid item into a specific cell, based on line numbers. span keyword can be used to span an item across more cells.

   2. justify-self: stretch | start | center | end
      align=self: stretch | start | center | end
      To overwrite justify=items/align-items for single items


3. Sizing Grid columns and rows
   grid-template-columns: 250px 250px 150px 150px;
   grid-template-rows: 300px 200px;

   Using fr unit (a very new unit) here instead of px will allow us to very easily create flexible columns and flexible rows. Using px allows us to only give these tracks very rigid dimensions. So, if we resize the window, the size always stays the same here. At some point, it even overflows the container. Many times this is not what we need. And instead we want flexible columns and rows. For that we can use the new fr unit.

   What if we want the third column to fill up the remaining space?
   grid-template-columns: 250px 250px 1fr 150px;
   Its a little bit like setting flex: 1 in the flexbox. 

   What if we set 1fr to two columns?
   grid-template-columns: 250px 250px 1fr 1fr;
   Then they have the exact same size because they have the exact same value here for the fr unit. If we resize the window, they fill the remaining empty space basically in the same proportion.

   How to create a grid where all the columns are the same width?
   grid-template-columns: 1fr 1fr 1fr 1fr;
   
   This is very powerful and very useful and we do this kind of thing all the time.
   
   What happens behind the scenes?
   In the grid container, there is basically initially all of the empty space all the way from side to side. And then as we use the fr unit, then all of the empty space will get divided up equally between the four columns. And that is because each of them has the same value/proportion. 

   What happens if one of them gets 2?
   grid-template-columns: 2fr 1fr 1fr 1fr;
   Then that gets double the space than the other columns. ie. here the space is basically divided into 5 fraction. And so out of these 5 fractions, the first column gets 2 of them and the remaining ones get each of them each.
   grid-template-columns: 3fr 1fr 1fr 1fr; 
   Same as above. The space is basically divided into 6 fractions and the 1st column gets 3 of them which is half of the space.

   This is very important stuff and just like in flexbox this allows us to not having to specify width manually.

   What if we set auto to one of the columns instead of fr?
   grid-template-columns: 1fr 1fr 1fr auto;  (Also important)
   Then that column will only take exactly the size that is necessary to fill its content. And many times in practice, this is actually exactly what we need for one of the columns.

   There is an easier way to write 4 fr and CSS Grid introduced a function repeat for that.
   grid-template-columns: repeat(4, 1fr); // repeat(how many columns, how large they should be)

   The fr unit is also available on rows.
   
   How fr works in rows?
   grid-template-rows: 1fr 1fr;
   We didnt explicitly specified height for the container but still the above works and the height gets distributed evenly? How that works? In our code, we have one element with a height of 150px. And therefore, the entire row will then get 150 px height. And so therefore that is then 1fr.
   If we explicitly specify height for the container, then that height is actually evenly divided between rows.
   We can also use auto on specifying height for rows.

   Usually the fr unit is actually more helpful on columns. In many situations, its actually enough to define only columns and let the rows filled automatically.

4. Placing and Spanning grid items
   Until now, we have basically let CSS grid decide where to place our items in a completely automatic way simply following the HTML source code. However, sometimes its important to manually place elements in a grid cell other than the predefined one.

   How to place a certain grid item into another grid cell ie. into a grid cell that was not its default one
   Turn on grid visualization in dev tools to help getting started. We can see numbered grid lines that allow us to place any grid item wherever we want.

   We can make use of numbered grid lines to specify where to exactly place the grid item .. ie. in which column and which row
   .el--8 {
        grid-column: 2 / 3;
        grid-row: 1 / 2;
   }
   The above code places the grid item in second column and first row.
   .el--2 {
        grid-column: 1 / 2;
        grid-row: 2 / 3;
   }
   Again, the above code places the grid item in first column and the second row.

   And actually, if the second value is just one more than the first, we can omit it.
   .el--2 {
        grid-column: 1;
        grid-row: 2;
   }

   What will happen when we specify a second value that is actually not just plus one?
   .el--2 {
        grid-column: 1 / 3;
        grid-row: 2;
   }
   Then the above grid item will span across two columns.

   Also instead of this, we can also say span 2 ie. instead of specifying the final value of the grid line, we can say span across 2 cells or whatever no of cells we want to span.

   .el--2 {
        /* grid-column: 1 / 3; */
        grid-column: 1 / span 3;
        grid-row: 2;
   }
   `  
   What if we want one grid item to span all the way to the end of the container?
   So in some situations, we might not even know how many columns there are in a grid or we might simply not want to think about how many cells we need to span. And so in those situations, there is a very nice trick that we can use instead of manually spanning. 
   ie. we can use 
   grid-column: 1 / -1;
   Why this trick works?
   Each of the grid lines actually has two numbers (which we can see in devtool visualization). ie. the last grid line is not only 5 but it is also -1. And so this is why the trick works.

   And so the same thing ie. spanning also work for rows
   .el--6 {
        grid-row: 3 / span 2;
        grid-column: 2;
   }

5. Aligning grid items and tracks
   Just like in flexbox, in css grid we also have the ability of aligning grid items.

   Aligning grid items is a little bit different than it is in flexbox, because we can align both the tracks inside the container and we can also align the grid items inside of the tracks. And thats because sometimes the grid items are smaller than the cells that they are in.

   i. Aligning the grid tracks inside of the grid container (basically the columns and the rows inside of the grid container)
      Thats only possible in the case if the grid itself is smaller than the container.
      The two properties are: justify-content and align-content

       .container--2 {
        /* STARTER */
        font-family: sans-serif;
        background-color: black;
        font-size: 40px;
        margin: 40px;

        width: 700px;
        height: 600px;

        /* CSS GRID */
        display: grid;
        grid-template-columns: 125px 200px 125px;
        grid-template-rows: 250px 100px;

        /* Aligning grid tracks inside the container */
        justify-content: center;
        align-content: center;
       }

    ii. Aligning grid items inside the cell
        The two properties are: align-items and justify-items

        .container--2 {
        /* STARTER */
        font-family: sans-serif;
        background-color: black;
        font-size: 40px;
        margin: 40px;

        width: 700px;
        height: 600px;

        /* CSS GRID */
        display: grid;
        grid-template-columns: 125px 200px 125px;
        grid-template-rows: 250px 100px;

        /* Aligning grid tracks inside the container */
        justify-content: center;
        align-content: center;

        /* Aligning grid items inside of the cell */
        justify-items: center;
        align-items: center;
        }

    iii.Overriding align items individually
        As in flexbox, we can also align items individually. The two properties are align-self and justify-self
        .el--1 {
        align-self: start;
        justify-self: start;
        }