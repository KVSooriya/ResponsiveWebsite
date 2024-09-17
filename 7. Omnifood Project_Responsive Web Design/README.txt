1. How Media Queries Work
   
   With max-width property:
   This is what we use in desktop first strategies. And there is also mobile-first strategy. And so there we do use media queries with min-width. 
   
   Lets say we wanted to apply a certain style for the range between 0 and 600px. Then we could write a media query like this
   @media (max-width: 600px)    -  So, basically this media query checks if the current viewport width is smaller or equal than 600px. And if it is, then all the CSS code that is in this media query will apply. And if not, then that code that is in the media query will not apply. Here, max-width is 600 and 600 is the maximum width at which the media query still works. Now, after 600px, for eg, at 700px, it stops working.

   We can create more than just one media query.
   @media (max-width: 1200px)  - This media query asks the question is the width less than or equal to 1200px? And if it is, then of course, the code that is in this media query will be applied.

   Inside these media queries, we simply override some specific parts of the global css, so the code that is outside of any media query. But all the rest of the global code will of course, still apply. So, we can think of media queries as tools for basically overriding specific parts of our css at certain viewport width.

   What happens if a certain phone has a width of 400px. From the above two, which media query will apply now in this situation. Both queries will apply because both of the conditions are actually true. And so the code in both media queries will be applied. If we have conflicting CSS declarations in these queries, which is in fact usually the case, then the one which appears last in the code is the one that will apply.

   Implementing in code

   @media (max-width: 1200px) {
   .section-hero {
    background-color: aqua;
   }
   }

   @media (max-width: 600px) {
   .section-hero {
    border: 5px solid black;
    background-color: #94d82d;  // Conflicting css property but since this is the last in the code, this one gets applied for devices below 600px.
   }
   }


2. How to select breakpoints
   
   What actually are breakpoints?
   Breakpoints are the viewport width at which we want our design to change, or in other words breakpoints are the pixel values that we want to put in all media queries.

   Strategies for selecting breakpoints
   1. BAD APPROACH
   Back in the day, we would simply use the screen width of popular Apple devices like the iPhone and iPad as breakpoints and simply call it a day. While this is certainly the easiest way of doing it, we no longer do this for two important reasons.
     i.  When we optimize for one very specific device, we ignore all the other users of the other devices and so we create a worst experience for them.
     ii. Absolutely nightmare for maintaining our code and keeping it up to date in the future. Because, if tommorrow, Apple releases a new phone with new dimensions, do we really wanna go back and change all our media queries in all the projects that we have ever built?

   2. GOOD APPROACH
   This one is based on screen width ranges. Basically what we do here is to look at the most used width for different categories of devices like phones, tablets or desktop computers and then we try to group them together in some logical way to then pick our breakpoints from that. This is already a lot better than previous strategy because we are using lot of different devices here. And even more importantly, we are not setting breakpoints at one specific device but between similar device sizes. We can assume that most phones are somewhere between 300 and 500px and that most tablets are between 600 and 900px. And so therefore, we can place a breakpoint somewhere at 600px. And the same works for other categories. So, for eg, most landscape tablets are between 900 and 1100px and desktops are usually above 1200px.

   3. PERFECT APPROACH
   This one is all about setting breakpoints at places where the design breaks down. In this strategy, we can try to completely ignore devices and device categories all together, and only look at our content and our design. And ideally it works like this. So we begin at one screen size, either desktop or mobile size, and then we start decreasing our screen width, or increasing it for mobile first. Then as soon as the design breaks, which means that the design no longer looks acceptable, we create a new breakpoint and thats it. Its actually quite hard to do this one completely without thinking about devices. So, without classifying breakpoints as a phone, or as a tablet or something like that. So, therefore basically, we're gonna use this PERFECT strategy together with the GOOD strategy.