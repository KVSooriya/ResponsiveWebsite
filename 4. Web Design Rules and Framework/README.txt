1. Overview of Web Design and Website Personalities
   
   Web Design vs Development
   Web designers are who create the overall look and feel of websites. On the other hand, web developers are the ones who then implement the design using html, css and javascript code.
   Back in the day, designers only designed using some web design program such as Sketch, Figma or Photoshop. The developer would then take that design and implement it in code using some software such as VS code, so that in the end, the website could be displayed for the user in a browser.
   Using design rules and framework we can develop and design websites only using code.

   Web Design Ingredients
   1. Typography - all about formatting and designing text
   2. Colors - another crucial part
   3. Images/Illustrations - fundamental aspect that any website cannot miss
   4. Icons
   5. Shadows
   6. Border-radius - which is basically the general roundness of the elements on the page, might seem a little bit insignificant but actually its not. So different border-radius actually give a website completely different look and feel.
   7. Whitespace
   8. Visual Hierarchy
   9. User Experience
   10. Components/Layouts - how we can use different components and types of layouts to represent different kinds of information

   We will take the design decisions for each of these ingredients based on the website personality.

   Overview of Website Personalities
   1. Serious/Elegant - to convey luxury and elegance, based on thin serif typefaces, golden or pastel colors, and big high-quality images
   2. Minimalist/Simple - focusses on the essential text content, using small or medium-sized sans-serif black text, lines, and few images and icons
   3. Plain/Neutral - Design that gets out of the way by using neutral and small typefaces, and a very structured layout. Common in big corporations.
   4. Bold/Confident - Makes an impact, by featuring big and bold typography, paired with confident use of big and bright colored blocks
   5. Calm/Peaceful - This one is used many times for products and services that try to convey the idea that they care about the consumer. And they do this by using calming pastel colors, soft serif headings, and matching images/illustrations
   6. Startup/Upbeat - Widely used in startups, featuring medium-sized sans-serif typefaces, light-gray text and backgrounds, and rounded elements
   7. Playful/Fun - Colorful and round designs, fueled by creative elements like hand-drawn icons or illustrations, animations and fun language



2. Web Design Rules #1: Typography
   Typography is all about making text beautiful and easy to read.
   Serif and Sans-Serif typefaces
   Serif - It has small details, like the tails at the end of the lines which we call seriffs. Serif typefaces are the more traditional typefaces. And therefore we can use them to create more traditional or classic looking interfaces. They also make design convey trustworthiness for the user. And finally, its also good for long text, for eg in an article or an online magazine.
   Sans-Serif - typefaces which do not have decorative lines, ie. serifs that Serif typefaces have. And Sans-Serif typefaces usually look very clean and simple. By using them, we can give any interface a very modern look and feel.

   Rules:
   USE GOOD TYPEFACES
   1. Use only good and popular typefaces and play it safe (ie. do not choose any crazy or weird looking typefaces)
   
   ToolBox:
   Google Fonts
   Font Squirrel
   
   Examples for Sans-Serif typefaces (Available for free)
   Inter
   Open Sans
   Roboto
   Montserrat
   Work Sans
   Lato

   Examples for Serif typefaces
   Merriweather
   Aleo
   Playfair Display
   Cormorant
   Cardo
   Lora

   2. Its okay to use just one typeface per page! If we want more, limit to 2 typefaces
   3. Choose the right typeface according to our website personality

   USE GOOD FONT SIZES AND WEIGHTS
   4. When choosing font-sizes, limit choices! Use a "type scale" tool or other pre-defined range
   FONT SIZE SYSTEM (px)
      10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
   5. Use a font size between 16px and 32px for "normal" text
   6. For long text (like a blog post), try a size of 20px or even bigger
   7. For headlines, we can go really big (50px+) and bold (600+), depending on personality
   8. For any text, dont use a font weight under 400 (regular)

   CREATE A GOOD READING EXPERIENCE
   9. Use less than 75 characters per line
   10. For normal-sized text, use a line height between 1.5 and 2. For big text (like headlines), go below 1.5 something like 1.1 or 1.2
   11. Decrease letter spacing in headlines, if it looks unnatural (it will come from experience)
   12. Experiment will all caps for short titles. If we do this, then make them small and bold and increase letter spacing
   13. Usually, dont justify text
   14. Dont center long text blocks. Small blocks are fine



3. Implementing Typography
   1. Select suitable typeface from google font and select embed code from there and place inside head in html
   2. Apply typeface in css property
   body {
   font-family: "Inter", sans-serif;  // If for some reason, inter does not works then sans-serif is applied
   }



4. Web Design Rules #2: Colors

   Rules
   CHOOSE THE RIGHT COLOR
   1. Make the main color match our website's personality: colors convey meaning
      Red draws a lot of attention, and symbolizes power, passion and excitement
      Orange is less aggressive and conveys happiness, cheerfullness and creativity
      Yellow means joy, brightness and intelligence
      Green represent harmony, nature, growth and health
      Blue (most used in web design) is associated with peace, trustworthiness and professionalism
      Purple conveys wealth, wisdom and magic
      Pink represents romance, care and affection
      Brown is associated with nature, durability and comfort
      Black symbolizes power, elegance and minimalism but also grief and sorrow

   2. Use a good color tone! Dont choose a random tone or CSS named colors

   ToolBox:
   Open color
   TailWind CSS
   FLAT UI COLORS

   ESTABLISH A COLOR SYSTEM
   3. We need at least two types of colors in our color palette: a main color and a grey color
   4. With more experience, we can add more colors: accent (secondary) colors (use a tool)

   ToolBox:
   Paletton
   Coolors

   5. When we design real world interfaces, we'll always need some lighter and some darker versions of the above three colors (tints and shades). And this is specially important for grey colors as we will usually need many different gray tones for text in different places or different states, for eg, different button states.
   
   ToolBox:
   Tint and Shade Generator

   WHEN AND HOW TO USE COLORS
   6. Use our main color to draw attention to the most important elements on the page eg., to draw attention to the button, logo
   7. Use colors to add interesting accents or make entire components or sections stand out
   8. We can try to use color strategically in images and illustrations

   COLORS AND TYPOGRAPHY
   9. On dark colored backgrounds, try to use a tint of the background ("lighter version") for text
   10. Text should usually not be completely black. Lighten it if it looks heavy and uninviting
   11. Dont make text too light! Use a tool to check contrast between text and background colors

   ToolBox:
   Coolors - tool like this will give us something called a contrast ratio, which needs to be atleast 4.5:1 for normal text and 3:1 for large text


5. Web Design Rules #3: Images and Illustrations

   Rules
   USE GOOD IMAGES
   1. Four different types of images: product photos, storytelling photos, illustrations, patterns
   2. Use images to support our websites message and story. So only use relevant images!.
   3. Prefer original images. So, basically images that we take ourselves or that some professional photographer takes for us. If not possible, use original-looking stock images (not generic ones!)

   ToolBox:
   Unsplash
   Pexels
   DrawKit
   unDraw

   USE IMAGES WELL
   4. Try to show real people to trigger users emotions
   5. If necessary, crop images to fit our message
   6. Experiment combining photos, illustrations and patterns

   HANDLING TEXT ON IMAGES
   7. Method #1: Darker or brighten image (completely or partially, using a gradient)
   8. Method #2: Position text into neutral image area. We just need to be mindful about what happens when these images get smaller on a mobile screen because then somehow the text might get overlaid with the rest of the image. ie. with the part of the image where we dont want it to be.
   9. Method #3: Put text in a box. Very simple to do and quite effective, especially if we add some opacity to the box.

   SOME TECHNICAL DETAILS
   10. To account for high-res screens, make image dimensions 2x as big as their displayed size. Eg: If we want to display a image as 300 * 300 px, then we actually need the image file to be 600 * 600 px. And we call this 2x or two times a scale factor.
   11. The above can create a problem of very large image files. So, always compress images for a lower file size and to achieve better load performance for our website.

   ToolBox:
   Squoosh

   12. When using multiple images side by side, make sure they have the exact same dimensions. Before placing images on the website, make sure they have the same dimensions or atleast the same aspect ratio.


6. Web Design Rules #4: Icons
   
   Rules
   USE GOOD ICONS
   1. Use a good icon pack. There are tons of free and paid icons pack.

   ToolBox:
   Phosphor icons
   ionicons
   ICONS8
   and many, many more 

   2. Use only one icon pack. Dont mix icon from different icon packs.
   3. Use SVG icons or icon fonts. Dont use bitmap image formats (.jpg and .png)! And thats important because svg type of icons are so called vector based which means that we can scale them indefinitely without they getting pixelated. So they will not get unsharp no matter how big we make the icons.
   4. Adjust to website personality! Roundness, weight and filled/outlined depend on typography. Some website personalities might actually not need icons at all such as the minimalist or bold personality

   WHEN TO USE ICONS
   5. Use icons to provide visual assistance to text
   6. Use icons for product feature blocks
   7. Use icons associated with actions (for eg, on buttons or on menus) and label them (unless no space or icon is 100% clear)
   8. Use icons as bullet points (like small check marks and they are included by default in all icon packs)

   USE ICONS WELL
   9. To keep icons neutral, use same color as text. To draw more attention, use different color
   10. Dont confuse users: icons need to make sense and fit the text or action!
   11. Dont make icons larger than what they were designed for. If needed, enclose them in a shape


7. Web Design Rules #5: Shadows
   Shadow creates depth (3D): the more shadow we add to a certain element, the further away from the screen or from the user interface that element will seem
   Shadow can be used on boxes and text

   Rules
   USE SHADOWS WELL
   1. We dont have to use shadows! Only use them if it makes sense for the website personality
   2. Use shadows in small doses: dont add shadows to every element
   3. Go light on shadows, dont make them too dark!

   USE SHADOWS IN THE RIGHT SITUATIONS
   4. Use small shadows for smaller elements that should stand out (to draw attention) eg: action buttons or small form which have an input for email address.
   5. Use medium-sized shadows for larger areas that should stand out a bit more than these smaller elements. It is used to make entire sections completely float above the page. Also another application is to make cards stand out from the rest of the interface
   6. Use large shadows for elements that should really float above the interface. Eg: navigation and popup windows
   7. Experiment with changing shadows on mouse interaction (click and hover). Eg: Consider a button with normal state doesnt having any shadow at all. Then as we hover over the button, we can add a medium size shadow, which will kind of create the effect of the button being pulled closer to the user, so towards the user as they hover with the mouse over the button. Then once they actually click the button, we can reduce that shadow, which will then create the interface of pushing that element back down into the interface. And so a very small and subtle effect like this can actually help creating a very natural feeling interface.   
   8. Bonus: Experiment with glows (colored shadows)


8. Implementing Shadows
   Property used to add shadow to a box: box-shadow
   This property actually requires multiple values. We can specify four or five values
   1. First value - the horizontal offset of the shadow ie. we need to specify a length which will then be the horizontal offset between the box and the shadow
   2. Second value - the vertical offset of the shadow ie. the offset of the shadow from the box in vertical direction
   3. Third value - blur of the shadow. So, if we use a small value here, it will be almost not blurred. And if we use a very large one, then of course, the blur will be huge.
   4. Fourth value - (Optional) It allows us to basically scale the shadow up
   5. Fifth value - Color of the shadow 

   .chair {
   box-shadow: 0 20px 30px 0 rgba(0, 0, 0, 0.07);
   }

   Property used to add shadow to a text: text-shadow
   And this property doesnt have the fourth value of spread as above

   h1 {
   /*  Font-Size System : 44 / 52 / 62 */
   margin-bottom: 24px;
   font-size: 44px;
   line-height: 1.1;
   letter-spacing: -1px;

   text-shadow: 0 5px 5px rgba(0, 0, 0, 0.2);
   }

   Text shadow is quite useful for situations where we have text on top of an image


9. Web Design Rules #6: Border-Radius

   Rules
   USE BORDER-RADIUS WELL
   1. Use border-radius to increase the playfulness and fun of the design, to make it less serious
   2. Typefaces have a certain roundness: make sure that border-radius matches that roundness
   3. Use border-radius on buttons, images, around icons, standout sections and other elements


10.Web Design Rules #7: Whitespace
   The right amount of whitespace makes designs look clean, modern and polished
   Whitespace communicates how different pieces of information are related to one another
   Whitespace implies invisible relationships between the elements of a layout

   Rules
   WHERE TO USE WHITESPACE
   1. Use tons of whitespace between sections
   2. Use a lot of whitespace between group of elements, but not as much whitespace as between sections
   3. Use whitespace between elements
   4. Inside group of elements, try to use whitespace instead of lines

   HOW MUCH WHITESPACE
   5. The more some elements (or groups of elements) belong together, the closer they should be! It is known as law of proximity
   6. Start with a lot of whitespace, maybe even too much! Then remove whitespace from there. Also remember, too much whitespace looks detached, too little looks too crammed
   7. Match other design choices, If we have big text or big icons, we need more whitespace
   8. Try a hard rule, such as using multiples of 16px for all spacing ie. for all the margins and the paddings

   SPACING SYSTEM (px)
   2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128


11.Web Design Rules #8: Visual Hierarchy
   Visual hierarchy is about establishing which elements of a design are the most important ones
   It is about drawing attention to these most important elements
   It is also about defining a "path" for users, to guide them through the page
   We use a combination of position, size, colors, spacing, borders and shadows to establish a meaningful visual hierarchy between elements/components

   Rules
   VISUAL HIERARCHY FUNDAMENTALS
   1. Position important elements closer to the top of the page, where they get more attention
   2. Use images mindfully, as they draw a lot of attention (larger images get more attention)
   3. Whitespace creates seperation, so use whitespace strategically to emphasize elements

   VISUAL HIERARCHY FOR TEXT ELEMENTS
   4. For text elements, use font size, font weight, color and whitespace to convey importance
   5. What text elements to emphasize? Titles, sub-titles, links, buttons, data points, icons. We can also de-emphasize less important text, like labels or secondary/additional information

   VISUAL HIERARCHY BETWEEN COMPONENTS
   6. Emphasize an important component using background color, shadow or border (multiple)
   7. Try emphasizing some component A over component B by de-emphasizing component B
   8. What components to emphasize? Testimonials, call-to-action sections, highlight sections, preview cards, forms, pricing tables, important rows/columns in tables etc.


12.Web Design Rules #9: User Experience (UX)
   A popular quote by Steve Jobs: Design is not just what it looks like and feels like. Design is how it works

   User interface (UI) is the visual presentation of a product. Its how the graphical interface looks and feels like. Its all about the layout of the design as well as the typography, colors, icons and other design elements that we use. And in the end, its also about the overall personality. So kind of a feel and vibe that we give to our design.

   User Experience (UX) is the overall experience the user has while interacting with the product. We need to ask questions ourselves
      i. Does the app feel logical and well thought out?
      ii. Does the navigation work intuitively?
      iii. Are users reaching their goals?

   UI and UX Design
   UI is graphical interface 👉 UI Design is what makes an interface beautiful
   UX is experience with interface 👉 UX Design is what makes an interface useful and functional

   UX Design Guiding Principle: GOALS
   A website or application exists for a reason: a user has a goal for visiting it, and a business has a goal for creating it. So, good UX design aligns the users goal with the business goals. ie. a goal of UX design is to fulfill both the goals of the user and the business.

   UX Example:
   1. Highlighting an option in the product pricing table     (Good UX design)
      Helps the user decide faster what is the best option
      Helps the business maximize revenue

   Here the user goals are aligned with business goals

   2. Many companies use to maximize revenue is to use a popup form in order to capture users email addresses. Now, this does help the business goal but in many cases it actually makes for a really bad and annoying user experience. And in many times also it doesnt help the user reach his goal.       (Bad UX design)

   Here the goals are very clearly not aligned.

   Rules
   UX RULES FOR USABILITY
   1. Dont design complicated layouts. Dont reinvent the wheel. Use patterns that users know.
   2. Make our call-to-action, which is usually a button, the most prominent element, and make the text descriptive
   3. Use blue text and underlined text only for links!
   4. Animations should have a purpose and be fast: between 200 and 500 ms. 
   5. In forms, align labels and fields in a single vertical line, to make the form easier to scan.
   6. Offer users good feedback for all actions: form errors, form success etc., [web apps]
   7. Place action buttons where they will create an effect(law of locality)  [web apps] 

   UX RULES FOR WEBSITE CONTENT
   8. Use a descriptive, keyword-focused headline on our main page. Dont be vague or fancy!
      Eg: 
      The AI assistant that grows your money
      Automate banner production in minutes
      Greenlight makes it easy to leave feedback on any website
      The All-In-One toolkit for working remotely

      Bad UX design
      Join the solar energy revolution
      The way you work is evolving. Is your hiring software?
      Meaningful insights without the click of a button
      Is design growing your product?

      So, the main headline of the website should really convey what the business does or what the website is all about!

   9. Only include relevant information, efficiently! Cut out fluff and make the content 100% clear
   10. Use simple words! Avoid technical jargon and smart-sounding words
   11. Break up long text with sub-headings, images, block quotes, bullet points etc.,


13.Design inspiration ideas

   ToolBox:
   LandBook
   OnePageLove
   awwwards
   ScreenLane