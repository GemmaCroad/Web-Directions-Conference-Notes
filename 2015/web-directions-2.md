## Web Directions 2015 - Day Two

### Souls and machines - Hannah Donovan, Product Design Lead at Drip

Twitter - @han

Content and companies are adapting to become digital so what are the answers to the universal questions such as "humans vs computers", "pro vs user generated content" and "opinion vs democracy"...?

- "I design for desires, not needs...." - not solving problems that need to be solved, and that's okay.
- Chasing the intersection between product and content. 
- Content Strategy for the Web - Kristina Halvorson.
- Need to be the connective tissue between the content and the experience.
- Content without context is confusing.
	- What is the wrapper around the content so the user has a great experience with it?
- Content without connection isn't relevant.
	- Can be really personal.
- Content with perspective has no feeling.
	- The worst kind of designs are the ones that don't elicit a strong response.
	- Humans can wrap the content with a story.
- Humans can connect us in ways that computers can't and computers can connect us in ways humans can't.
- With everything we make, we have an opportunity for (the reaction between product and content).


### Embracing the network - Patrick Hamann,  Lead Software Developer at The Financial Times

Twitter - @patrickhamann

- FAILURE IS INEVITABLE!
- Networks can and will fail, and as developers we need to be able to handle that.
- There are so many points of failure where things can go wrong - the average web page makes 80 requests and comes in at around 3MB.
- Building Microservices - Sam Newman
- Testing and monitoring failure:
	- Don't create SPOFs, can stop the entire system.
	- WebPageTest - SPOF tab
	- Comcast - tool designed to simulate common network problems like latency, bandwidth restrictions, and dropped/reordered/corrupted packets.
	- Facebook have something called 2G Tuesdays so that everyone knows what is is like to use the site on a less than ideal connection.
- Designing for failure:
	- Design for reality, not just the best case scenario.
	- Skeleton screen for content you know will be loading?
	- Avoid loading spinners.
- Embracing failure:
	- Eliminating roundtrips with pre connect - Ilya Grigorik.
	- Prefetch and cache resources.
	- The best http request is the one not made...
	- The offline cookbook - Jake Archibald
	- Service Worker:
		- Controls network requests in and out.
		- Like a proxy?
		- Can combine event listeners. 
	- Use timeouts on Ajax requests.
	- How badly do you need to import lots of Google fonts?
- All of the code for the Financial Times code is available to view on Github here. 


### The two pillars of JavaScript - Eric Elliott, author, public speaker, UX consultant, and viral application consultant

Twitter - @_ericelliott

- Didn't have a slide deck just pulled up the below GitHub page with links:
	- Essential Javascript Links
- Prototypal inheritance (objects without classes, and prototype delegation, aka OLOO — Objects Linking to Other Objects).
	- "The problem with object-oriented languages is they’ve got all this implicit environment that they carry around with them. You wanted a banana but what you got was a gorilla holding the banana and the entire jungle."
- Functional programming (enabled by lambdas with closure).


### Real-life responsive web development - Vitaly Friedman, Editor-in-Chief of Smashing Magazine

Twitter - @smashingmag

- Object-fit letterboxes images > object-fit: contain, object-fit: cover, object-fit: none.
- Pro CSS3 Animation
- Nested links - put links inside links with the object tag.
- Flexbox is awesome!!!!! Add more flexbox....
- Use JavaScript fallback to support older browsers.
- It's okay to use the :not() selector where appropriate. 
- Consider using vh-units, good for scaling images if a window is resized. 
- Lobotomised owl selector??? * + *
- @supports - gives CSS the ability to perform a feature query.
- Monkey testing:
	- A software testing technique in which the testing is performed on the system under test randomly.
	- The Input data that is used to test also generated randomly and keyed into the system.
- To make something super responsive use rem in the root and em in the sub parts.
- Google Maps JavaScript API - Great API to work with, good documentation, most people don't realise it exists.
- Background check JavaScript library - defines how an element "plays" with the background, use difference and darken.
- Modularity:
	- Have a shared vocabulary for modules.
	- Identify patterns across the platform.
	- Define how these parts fit together.
- Simple country selector?
- Using SVG to shrink your png images. jpg. + png. > SVG mask


### Designing spaces for creative professionals - Alastair Simpson & Nat Jones, Design Manager & Senior Designer at Atlassian

Twitter - @alanstairs & @natemsj

How do you infuse design thinking into every day work? How do you set up the environment to inspire people?

- How do you show the value of design thinking in everyday work across a company?
- Ideate:
	- Breakout areas - should be scattered all around the office.
	- Meeting rooms - should be configurable and should all have the correct tools in them (whiteboard pens, timer and a rubber chicken.....).
- Iterate:
	- Bring design out of the digital world and into the physical world.
	- Exhibition - Each team should have an exhibition wall. They should take care to put their work up in a careful manner and make sure it is well presented so that anyone can walk up to the wall and understand it. It should be updated regularly, and it should invite open feedback. It should also be good enough to use for user testing. 
		- All purpose - Started with whiteboards on wheels, but they were a pain to move around the office. Turned all walls into whiteboards, Should be able to jump and start writing on anything, grab colleagues and work on stuff with them.
	- Transient - Portable foam core boards that can be taken into a meeting room and then carried back to desks to carry on work.
- Creativity:
	- Statement space - A corridor with a wall of inspirational quotes picked by the staff. 
	- Art - Encourage people to personalise the space with art, even if people aren't in day-to-day creative roles inspire them to make their space inspiring to others.
	- Library - A quiet space to go and do focused work, with selected relevant books as well that people can dip into to learn stuff.
- Things not to do:
	- Movable meeting rooms that don't move!
	- Whiteboards / whiteboard paint that doesn't clean properly and ends up grey and smeary.
	- Weird folding cardboard chairs - much worse in reality!
- Make spaces adaptive!
- Make the workspace suggestive so that it encourages people to do a certain kind of work...?
- Create spaces that are inclusive and welcoming to everyone.
- Allow everyone to contribute ideas to creating these spaces, enhances collaboration. 


### Advanced responsive typography - Mike Riethmuller, Web Developer for http://www.humanservices.gov.au/

Twitter - @MikeRiethmuller

- http://slides.com/mikeriethmuller/wd15#/
- Stop thinking in pixels!
- calc() - can do simple maths calc in CSS.
- Max font size = font-size / ( number of viewport units / 100 )
- “The computed value resolves the specified value as far as possible without laying out the document or performing other expensive or hard-to-parallelize operations, such as resolving network requests or retrieving values other than from the element and its parent.”
- Steps involved in understanding CSS values in web browsers:
	- Specified value- What we write in our CSS.
	- Computed value- Calculations resolved by browser.
	- Used value- Final value used when rendering the page.
- Can cheat and use Sass!


### Style with substance - Craig Sharkie, JavaScript Developer and Author

Twitter - @twalve

- SEPARATION OF CONCERNS!!!!! Core programming fundamental. "In computer science, separation of concerns (SoC) is a design principle for separating a computer program into distinct sections, such that each section addresses a separate concern. A concern is a set of information that affects the code of a computer program."
- Structure = html.
- Behaviour = JavaScript.
- Presentation = CSS.
- matchMedia.js - test whether a CSS media type or media query applies.


### No more lipstick on pigs - Tom Loosemore, developer and driver of the experimental prototype of the new single domain for government in the UK (alpha.gov.uk)

Twitter - @tomskitomski

A call to arms from Tom Loosemore 

- "We get to invent the future... If we're going to invent stuff, then let's invent stuff that matters."
- BE BOLD! Do stuff that matters.
- Government needs fixing, enter government digital services. 
- Always remember who your users are. 
- Have a set of clear design principles. 
- Iterating our existing institutions isn't good enough.
- The first nation to create new institutions that make the most of the internet will win big. 
- Malcolm' Turnbull's push for cabinet to use Slack app.
