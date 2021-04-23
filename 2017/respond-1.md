## Respond 2017 - Day One

### New Adventures in Responsive Web Design - Vitaly Friedman, founder and editor-in-chief at Smashing Magazine

Twitter -@smashingmag

How do we create fast, resilient and flexible responsive design systems that utilise all the shiny web technologies we have available to us... Responsive adventures game...

- "This is not best practices... this may be bad practices...! This is new stuff."
- The presentation was a Stranger Things themed game called "Responsive Adventures"
- Level 1 - Storytelling
	- "We try and find really good solutions in a limited amount of time"
	- The design process can be weird - squiggle process, but in reality it's more like a set of paths and dead ends
	- The web all boils down to one single thing, outstanding storytelling through great art direction
	- When we think about storytelling, we think about fairy tales, not the interface of websites and apps
	- Vitaly used the example of Uber - he said he would switch from away from Uber without much thought at all because he doesn't feel an emotional connection to them
	- Mailchimp on the other hand, he feels involved, because they have an engaging personality and brand (showed some cute pics from a Mailchimp colouring book)
	- There are a lot of "commandments" about design, "thou shalt not do this....", design often ends up somewhere between all these rules
	- What happens if we break these rules?
	- Should they be more just guidelines?
	- If we do have the courage to break them, can we create something more memorable?
		- Bloomberg Businessweek Design 2016 (conference?) - everything on the page animates in some crazy way, seems like overkill however tickets sold out in only six mins!
		- aftershock.cc - pretty out there colour scheme, and again strangely over animated and memorable
		- Hans Brinker Hotel - a very terrible hotel that made use of being the worst, they actually hired a comedian to write the copy for the site
		- storytrail.co - a site based around a single line, they built the whole design around it
		- 7h34.fr - beautiful and bold carousel on this site
- Level 2 - The System
	- So we want an amazing design, but what happens if we have to support multiple languages?
	- Simple things like dates can change between languages
	- What if your text now needs to read from right to left, not left to right?
	- Everything in the design should be flexible
	- If you optimise for only one language then you are likely to run into problems in any other (if you need to render your website in German expect some text breaking out of a box)
	- Need to build "neutral"  components which can be easily extended and adjusted if needed
	- The BBC news website used .json files for configuration, and capturing things like languages, direction, social media buttons, etc...
		- $russian = true;
		  @if russian {}
		- Contextual styling can then be based on the language direction, they have a flip mixin that selected things like floats
- Level 3 Bonus level - Battery Status API
	- https://www.w3.org/TR/battery-status/
	- This API provides information about the battery status of the hosting device
	- Was intended to help developers make decisions based on the battery status, eg. don't auto play videos if the battery is below 20%
	- However, companies like Uber are using it super aggressively, if your battery is under 6% then they apply a surcharge because they know you need a ride quickly
	- Has led to Firefox removing it from the browser, though the spec is still alive
- Level 4 - Hover
	- Is there a way to reliably check whether the user can use hover?
	- With CSS4 there is a hover media query
	- Can I use good info http://caniuse.com/#feat=css-media-interaction
	- This works out what the primary input is
	- If used in combination with supports, can tailor styles to the users device
- Level 5 - Selectors
	- We all know about the fancy selectors, but are we overlooking the simple and powerful selectors
	- :not()
	- Build quantity queries on this site http://quantityqueries.com/
	- Selectors are getting more difficult to read, remember that the browser reads selectors from right to left
		- li:nth-child(n+6) - six or more items
		- li:nth-child(n+6):first-child ~ li {} - adding general sibling selector finds the condition and then selects everything around it
		- li:nth-child(3n):first-child ~ li {} - find by sets only divisible by three
- Progressive Web Apps
	- Vitaly admits that he doesn't know what to think of offline first still
	- People don't really expect a website to work offline?
	- Most users don't install a lot of apps, have the ones they use regularly then run out of storage space on their device
	- The retention rate of apps is very low - only 10% of people that download an app will keep using it once installed
	- Mobile web usage is growing around twice as fast as app usage
	- Should we be switching design systems between platforms?
	- 2/1000 of mobile users tap share buttons! Two out of a thousand!
	- Be wary of using push notifications, 52% of users find them annoying
- Service Workers
	- Service workers behave as a proxy server on the users device
	- Take very little time and effort to set up
	- Common offline strategy is quite simple: explicitly cache static resources, cache the homepage in case network fails, for other pages have a 'fallback’ offline page
	- Need to register the service worker and define its scope (so that it applies everywhere)
	- Install the service worker
	- Cap the cache of the serviceworker.js at 24 hours, otherwise people can not get updated version of the site
	- Pragmatic guide to service workers https://next.smashingmagazine.com/speaker/lyza-danger-gardner/
- The end
	- As developers we shouldn't be afraid of being experimental and go out and breaking things on the web so we can fix them in a few weeks time!

### Design Systems + Dreams - delivering at scale - Rebecca Hendry, Design Quality Principal for Westpac’s Experience Design & Delivery team

A talk about how the Westpac group design system GEL was created, how it evolved and most importantly, what they learnt...

- Rebecca opened her talk with the full disclosure that she is not a developer, not a designer... but an enabler
- https://gel.westpacgroup.com.au/index.html
- Once upon a time Westpac had it pretty easy, one brand, one small website
- Currently the Westpac group is now made of six brands all with their own visual identity
- They were inspired by the BCC Global Experience Language (GEL) http://www.bbc.co.uk/gel
- They hired a digital brand director, Justin, so there was someone dedicated to solving the 'problem'
- How to start? Top down, bottom up?
	- Top down = when you have budget, buy in and leadership support
	- Bottom up = when it starts with the developers and works up through the layers of the business
- Growth can actually stifle progress
- The team knew they needed five things if the project was to succeed:
	- skillet
	- attitude
	- toolset
	- support (exec buy in)
	- projects to actually apply it to
- At this point there was no dedicated FE dev so they had a go at using Bootstrap V3
- Good way to get the project off the ground?
- Westpac GEL V1.0 - colour, typography, iconography and grid
- What worked?
	- Just starting - don't wait for perfect, just get going
	- Getting their hands dirty - use it for real
	- Working out who to add to the team next - where are the gaps?
- What didn't work?
	- Asking people to change the way they work - get pickets of appetite, but generally more resistance
	- Co-iterate, don't just create, having passionate people that want to ship things is good but engage everyone
	- Not starting by creating an end to end story that takes the full situation(s) into account, there are a lot of things going on the user landscape
- Why should companies have a design system?
	- Consistency
	- Quality
	- Efficiency
- A user interface audit revealed many different buttons - good idea to crowd source pattern audits (don't polish the Ferrari in the showroom for too long)
- Atomic design is a great anchor point - not just the team telling people what to do, but an industry framework to refer to
- The team needed to sell the idea up the chain, and made a compelling case, but it didn't stick
	- People needed to hear more about the roadmap for getting there
	- They were asked how urgent it was, what are the risks of not doing it?
	- Why are you telling us how to do our jobs?
- Westpac GEL V2.0
	- A front-end dev (Dominik, bit of an atomic design fanboy) and product owner were added to the team
	- They created a website and started building their own framework to replace Bootstrap
	- Created started kits for both devs and designers
	- Ran workshops, started creating the idea of a community of people using the system
	- A living design system and shared toolkit, and collaborative work practices were the goal
	- Open source, transparent and accessible to everyone (a little controversial for a bank at that time) https://github.com/WestpacCXTeam/GUI-source / http://westpaccxteam.github.io/GUI-source/
- What worked?
	- It had a destination - MVP
	- The system was modular and simple
	- They had recognition and the right mix of skills
	- Listened more
- What's next?
	- Adoption - should have started with this early
	- Distributed ownership - better than the 'solitary overlord' approach
	- End-to-end owned
- The structure around contributions is really important
- Recommended reading: Nathan Curtis, Team Models for Scaling a Design System
- You need a good mix of optimists and pessimists, this kind of balance is good
- The work can be hard and demoralising some days
- Don't let the dream die...!


### Building a ubiquitous design language with components - Michael Taranto, Principal UI Engineer at Seek

Twitter - @michaeltaranto

The world of components gives us the opportunity to create abstractions that directly model the design teams intent...

- Designers and developers talk in pixels
- Wireframes only share the outcome of the design process
- They basically ask a developer to reverse engineer an idea from a few pictures - they need to work out the purpose and semantics and make it accessible and responsive
- This can lead to an inconsistent user experience
- We should be focusing on building a common language
- This markup is what will be used at build time
- Largely this is expressed by abstracting the markup away and building components
- Even then, as developers we still tend to focus on things like buttons, and not so much on the principles
- Michaels team at Seek are tying to capture the designers intent, and not just the outcomes and distill that knowledge into their code
- Why is it we normally end up nudging pixels around - most of the time these conversations are about whitespace, and what's not right
- What happens is we set typography first?
	- What does a 21px heading on a 27px line height really mean?
	- It's part of a type hierarchy of scaling on a base value
	- It's not 21px, it's 2.1 x base size of 10px
	- The line height is not 27px, it's 3 x 9px row height
- This is based on extracting the design principles and not just the design outcomes
- This means the code can follow the right paths
- The language can be extended without talking about pixels
- Pixels only exist in a compiled output...
- CSS does not speak design
- Line height means something entirely different in CSS than it does in typography layout
- True typography measures line height from the baseline, so the height isn't right, and this is often what leads to build time 'nudging'
- This information can be put into SCSS variables
	- Capture the descender height and nudge the text down to where the designers expect it to be
	- Michael has created an open source library to do this: https://github.com/michaeltaranto/basekick
- Now the conversation is happening in design principles rather than pixels
- Component interface becomes the new design language
- This is a great way to form understanding between teams
- This can be applied to colour as well
- What's the intent of some green text? 
	- It was being used to reinforce positivity, positive beats green as a design language
- "Controlling the snowflakes..."
	- People always think that they have a special case
	- Seek are driving consistency by default
	- Variation gets pushed into design discussions that can then be mainstreamed
- What's worked?
	- Nothing is too small to be a component, think small, compassable components
	- Cross-pairing with design
- What didn't work?
	- Naming things is hard
	- Justifying the why is even harder, what's missing is the system
- The Seek style guide: http://seek-oss.github.io/seek-style-guide/


### The Anatomy of an Accessible Auto-suggest - Adem Cifcioglu, A11y Consultant at Intopia Digital

Twitter - @ademcifci

How to make a fully accessible auto-suggest component...

- Every framework has an auto-suggest component these days
- However, they have only done half of the work, these are not normally keyboard or screenreader accessible
- First step, understand the requirements
- Search field needs:
	- a label element
	- role="combobox"
	- aria-autocomplete attr
	- aria-owns attr
	- aria-activedescendent attr
- Need to manage the keyboard access, should have visible focus states
- Should be able to use arrow keys for moving through the suggestions
- Pressing enter or the right arrow to select an option and close the list
- Arrows should wrap inside the list
- Pressing escape should close the list and leave what's been typed in the input field
- List needs:
	- role="listbox"
	- each suggestion has role="option"
	- selected has aria-selected="true"
- Second step is to understand the code
	- Codepen: https://codepen.io/ademcifcioglu/pen/xdOyXv
- Aria-live has three settings:
	- none
	- polite
	- assertive
- Be very careful using aria-live
- Adam ran a demo of a bad autocomplete and a good one, and the difference was pretty full on
- Most implementations of an autocomplete don't announce the autosuggests, many block the input
- Something to remember, don't override native semantics
- In the Q&A session after the talk someone asked Adam if there is anyway to detect if screen readers are being used on desktops
	- His answer was no, as they can't be detected by the native web layer... yet!


### Responsive, progressive fluid typography - Mike Riethmuller, Web Developer

Twitter - @MikeRiethmuller

An overview of unit-types and values in CSS, with a specific focus on how viewports units and the calc() expression work...

- An alternative approach to responsive design...
- Maybe we need to move past breakpoints and media queries and look at things like relative units and the power they can bring
- We need to stop thinking in pixels or some abstraction of them
- Limitations shape our thinking
- Perceived limitations can also shape over thinking
	- Like cats who will sit inside a circle of tape on the floor, we just just sit where we think we have to
- It's very easy to carry over our perceived limitations from the past
- It takes effort to break the paradigm of pixels
- Browser fundamentals:
	- There are 27 different unit types in CSS
	- Most people only use maybe three per project
	- Browsers break down CSS in a three step process
		- specified value - author specified
		- computed value - resolved the specified value as far as possible without rendering the page
		- used value - used for actual rendering
- Understanding calc()
	- It allows us to simple calculations in native CSS - the normal order of operations applies
- There are two keys rules for calc():
	- You can add and subtract units with a similar type
		- e.g. length units, , calc(10px + 2rem) resolves to 42px
	- You can multiply and divide real numbers with CSS units
		- e.g. calc(3 * 2rem)
- This brings us to responsive typography, existing techniques aren't really ideal e.g. relying on breakpoints
- Viewport units are good, but they do have limitations
	- vw, vh, vmin, vmax
	- On their own they can be difficult, e.g. text can become too large or too small
- You can set a minimum font size with with calc()
	- calc(18px + 3vw)
- You can set a max font size with with the breakpoint using font-size / (viewport units / 100) to calculate the breakpoint
- Still can't control the rate at which viewport units scale though
- There is a better way of doing this, we can use a function is CSS
	- font-size: calc (16px + (24 - 16)*(100vw - 400px) / (800 - 400))
	- We can apply this to the HTML element, then selectively disable it simply by applying a fixed font-size to a class or other selector
	- Or we can set the fixed width to HTML and enable fluid type with a class
	- To make life easier we could just use a mixin in SCSS
- Now we have fluid type, we can move on to fluid modular scales (where each heading level is 1.2 times as large as the last)
	- To do this we use a modular scale for small and large screens
	- We can calculate the values with tools like:
		- http://type-scale.com/
		- http://www.modularscale.com/
	- This means the scale will fluidly change as the screen size changes
- This technique has very high browser support
- Possible to set a fixed callback if you want to and adding +100% fixes some strange bugs with mobile Safari and IE10
- This also works with things other than typography
	- It's possible to scale images and layout
	- You can even change colour based on the viewport
- Interpolation in design...
- Media queries generally reflect the limits of a design
	- It's the point in a design where it can no longer cope with the layout or content
- The closer we get the breakpoints the more signs of pressure start to show normally
- There is an 'ideal range' where things look great, but as you move out of that range there is increasing pressure
- Then you hit a breakpoint, and need to change to find the next 'sweet spot'
- Variable fonts:
	- The future of fluid typography?
- Variable fonts allow devs to scale the glyphs / shapes and eight of a single web font
- Article: https://alistapart.com/article/live-font-interpolation-on-the-web
- Mike has an open issue with the CSS working group for a native interpolation function in CSS
- It's very easy to be caught thinking about a new tech in the mind frame of old tech
- Remember to always be looking for new techniques that will allow us to break away from the perceived limitations
- Always question constraints
- Think about your intentions and how the available technology can help you get there
- https://madebymike.com.au/
- https://codepen.io/MadeByMike/pens/tags/2/?selected_tag=responsive+typography


### Sharpen up your text with The Power of Three - Mandy Michael, Lead Front-end Developer at Seven West Media

Twitter - @Mandy_Kerr

The key enabling technology of "PWAs" is the Service Worker...

- It's easy to forget the power of CSS
- There are three powerful things front-end devs should be using
	- data attributes - custom attr that allows info to pass from HTML into the DOM
	- pseudo elements
	- clip paths
- We can make a copy of our content available in a data attribute:
	- <h1 data-heading="hello">Hello</h1>
- We can add and style pseudo elements:
	- <h1 data-heading="hello"> 
	  ::before
	  Hello
	  ::after
	  </h1>
- Amazing examples on Codepen:
	- CSS only 3D paper fold text effect
	- 80s style text with clip path and layered fonts
	- Split emoji text effect with css
	- Single element, multi coloured 3d text effect
	- Flickering Light Text Effect
	- Stripy Rainbow Text Effect
	- Split fractured text
- You can do awesome effects with clip-path
- This allows you to draw a shape onto an element and then screen out / clip the content in that shape
- Clip-paths work much better with multi-line text
- Not supported in all browsers yet so use with caution


### Creative (yet still useful) SVG animation - Brett Snaidero, Interactive Designer and Front-end Developer

Twitter - @brettsnaidero

Using CSS properties to style SVG can be fun, simple and is an easy way to engage your audience...

- Talk about SVG, inline SVG, elements and attributes of SVG, styling them with CSS and even animating them
- SVG is awesome... 
- It can scale indefinitely
- Just as designers needed something to scale up to billboard size, we need things to scale to the viewport
- SVG looks and feels similar to HTML
- We can put it directly inline in our HTML
- We can also work with SVG elements the same way we work with HTML elements (inspect them, style them, use JS on them)
- SVG tags
	- <circle /> <ellipse /> <line /> <polygon /> <polyline /> <rect /> <path /> <text />
- We can even write out own SVG - it's complicated, but we can do it
- Optimising SVGs
	- Minimise size and improve readability
		- Remove unnecessary tags
		- Simplify paths
		- Clean up attributes
	- https://github.com/svg/svgo
	- https://jakearchibald.github.io/svgomg/
- SVG viewbox
	- <svg viewbox="0 0 10 10"></svg>
	- This set up a 10 x 10 grid
	- 0, 0 is the top left
	- 10, 10 is the bottom right
	- Elements inside the SVG are placed according to that grid
- Once an SVG is available inline, we can apply CSS eg. via a class:
	- <path class="star" d="..." />
- This is really powerful when we start using animation and transform
- Animating the stroke (border) of SVG elements allows a lot of amazing effects, like loading bars; animated icons; etc.
- SVG Animated Hamburger Menu
	- Creating the animated hamburger:
		- created a graphic with three paths that are the 'rails’
		- use stoke-dasharray and stroke-dashoffset to animate 'lines’ along those 'rails’
		- add some transitions to get easing and control the speed of the three lines
- Tutorial: https://tympanus.net/codrops/2015/11/12/animating-svg-menu-icon-segment/
- SVG has a lot of advantages including 
	- Scalability
	- Small file size, 
	- Ability to make them accessible
	- Great browser support
- Lots of JS libraries out there to help if we want to use JS
	- https://greensock.com/gsap
	- http://snapsvg.io/
	- http://velocityjs.org/
	- http://svgjs.com/
	- https://bonsaijs.org/
	- https://github.com/ConnorAtherton/walkway
- Think of SVG as an extension of HTML which allows you to do more in the browser
- Crazy animated SVG xbox https://www.polygon.com/a/xbox-one-review


### The Web in Motion - Rachel Nabors, Program Manager on the Microsoft Edge Team, and animation advocate

Twitter - @rachelnabors

As the lines begin to blur between “native” and “web" apps, animation is becoming more and more important to building a web that can meet user expectations...

- Let’s play a game called “app vs site”!
- Web apps have all kinds of stateful animation, but sites often vary from apps
- They may have high fidelity of typography and colour but still vary a lot with animation
- AirBnB and Amazon were two examples Rachel used where the animation varies a lot between desktop and mobile
- It is possible to have a 1:1 app:site relationship with animation?
- https://www.duolingo.com/
	- Does a great job, even though the form factor is different the experience feels the same as well as looking the same
- At its core, animation is the visual representation of a rate of change over time
- It’s a visual doppler effect
- You can get this effect by speeding up a sound (example video of a zebra crossing with beeps that speed up when you need to hustle)
- Animation can be used to reinforce relationships, structure, cause and effect
- In UI this helps the user understand the experience
- Gestures are seeping into desktop experience, microsoft surface...
- Meanwhile the web is working purely with jump cuts
- No animation, things just appear and disappear
- This makes sense back in the day because when the web was being built, computers didn’t have the grunt for lots of animation, but the web hasn't caught up with the hardware
- Cause and effect: when one thing follows another
- We think the first causes the second
- We also mentally fill in the blanks of transitions
- Because we stare at screens all day, we can understand a jump-cut dropdown… but it makes the brain work
- If animation is provided, the brain effectively offloads it to the visual cortex
- This can be thought of as the brains GPU (graphics processing unit)
- It means we can handle more information and tasks, because our brain is not actively processing as much
- Animacy: how “alive” something appears to be
- Human attention can be grabbed by two things: colour and motion
- We are deeply wired to not eat the dangerously-coloured things and to notice the movements of dangerous things approaching
- To abuse this, make an ad bright and jiggly!
- Humans are more likely to notice a colour change in the centre of our field of vision
- We are more likely to notice animation at the edges
- So in the middle of an app, it will be better to use colour, on the edges, animation
- Don’t overdo anything: New Yorkers do not notice the overwhelming amounts of animation at Times Square any more
- When everything vies for our attention, nothing commands our attention
- The Web Animations API has awesome stuff in it like the ability to sync multiple animations; seeking forwards and backwards along a timeline…
- More info > http://rachelnabors.com/waapi
- Animation is an official part of the front-end developer toolkit
- Firefox and Chrome have good dev tools for animation now
- https://www.chromestatus.com/metrics/css/popularity
- http://mojs.io/
- http://snapsvg.io/
- https://d3js.org/
- http://three.js/
- https://greensock.com/
- https://www.ibm.com/design/ - they went to the IBM museum and recorded the motion of old IBM devices like typewriters
- Wireframes just don't cut it anymore, they don't convey animations - use storyboards instead
- They are used in film, why not for the web
- An animation is worth a thousand meetings...
- Animations are not deliverables, or good for user testing
- They are good for getting buy-in and for explaining things
- Great prototyping tools:
	- InVisionApp.com
	- principleformac.com
	- framerjs.com
- Systems like Material Design showed animation could and should be a core part of a design language
- Designers, devs and UX all need to come to the table and talk about animation
- Animation belongs to all of us now - let us set the web in motion together
- Some Codepen examples:
	- Red Queen's Race (with Web Animations API)
	- Growing/Shrinking Alice Game : Alice in Web Animations API Land
	- From walk to run
	- Down the Hipster Rabbit Hole
