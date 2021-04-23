## Respond 2016 - Day Two

### Real Art Direction on the Web - Jen Simmons, Designer Advocate at Mozilla and podcaster

Twitter - @jensimmons

What is Art Direction anyway? Clearly it's directing… the art…

- Is it about the brand? Is it about aesthetics?
- It's part of being in a conversation, with other people, or the world outside of your project...
- Why was the Apple watch set in a particular way, doesn't look like a tech logo?
	- It was being positioned within fashion brands
	- Association with brands like Hermes, Gucci, Prada, etc.
- A lot of web design is still occupied with looking at what works for other people and copying that
- Or we just think about making things pretty
- A lot of design is about conveying an idea
- Every choice that is made in the way an article is presented in a magazine goes back to conveying the idea, supporting the story
- If we have the same article on a website we lose all of that - it gets dropped into a common layout and isn't as effective
- Libraries like Bootstrap have turned layout into a multiple choice question and this has led to websites looking the same
- Don't prototype with Bootstrap or it will point you towards a particular result
- We need to separate the tooling and the design process - "the design should be the design"
- People have been studying layout for over a century, we don't have to start from scratch on this
- In print there was an actual associated cost to have whitespace so it was hard to justify, but the web isn't like that, it's free!!!!!!

Lots of things coming in CSS that will allow us to do things with our layouts that we couldn't do before:

The small things:
- Initial letter – we haven't been able to do good drop caps easily with decent support, Initial letter lets you specify how many lines of text to match
- CSS Feature Query - @supports (initial-letter: 4) { // rule using initial-letter: 4 }
- Viewport units – allows really robust whole-viewport headers (“It's like a splash page, with scrolling!”)
- Object fit – allows resizing of photos within a size, maintaining aspect ratio
- Clip path – everything on the web is a box, but clip path can let you do a non-rectangular shape without a whole lot of code
- CSS shapes – this is so common in print layout and we just don't think to do it on the web

The big things:
- Flexbox - flexbox tends to think of everything as one big row or column
- Grid layout – has similar capabilities to flexbox, but has more powerful layout features. It's still a work in progress
- Flexbox vs Grid – fundamental difference is that flexbox is still thinking of things flowing through a page; where grid is thinking of fitting content into a grid
- Circular screens – with the popularity of smart watches, there is movement to create a circular layout system… which means we can use circles everywhere, don't just think of tiny screens

So what is the process for creating an awesome layout?
1. organise content – what content are you working with?
2. create HTML and set the source order – helps understand the content better
3. sketch ideas for page layout – use whatever tool works to figure out your ideas… but don't get final approval at this phase!
4. design a custom grid – do a live prototype at this point
5. apply CSS – write your own layout!!
- Remember, you don't have to use all the pieces, just because they are there
- Use the pieces that make sense!
- Use things that work in a browser
- Don't be scared to let things be different in a browser
- The people with older browsers don't know they are missing something nicer
	- So long as they get the content do they really care?


## Performance: HTTP2 in a 1.5 world - Peter Wilson, Front-end developer and CSS junkie

Twitter - @pwcc

What does the transition to HTTP2 really means for us as developers...

- There is increasing browser support for HTTP2
- The HTTP archive tracks how the Web is built - http://httparchive.org/
- Where are we now:
	- Currently sitting at an average page weight above 2.5megs on desktop and 1.2meg on mobile
	- The average weight is 2.5 what it was just 2 years ago
	- Average load time is 15.23 seconds (even worse on mobile)
- We have damaged the Web
- Performance issues are nothing but frustrating for users
- Performance costs money at the end of the day ->  users will go to competitors
- On average 100ms delay costs 1% of sales
	- here are plenty of case studies backing this up (Walmart, Yahoo… Amazon would lose an estimated $1.6b by slowing their site down by 1 second)
- Google PageSpeed is ok as a metric, but it doesn't have a huge level of insight
- WebPageTest gives far more depth of information
	- The three important metrics are: start render, render complete, document loaded
	- imeline view is really useful as it illustrates the reality – what does it actually look like at certain points
	- It does give a single-number metric as well
- About 65% of traffic globally us using a browser that offers full support of HTTP2
- Yet only 6.6% of sites are using HTTP2
- HTTP2 requires a secure connection
- The truth is that HTTP1's best practices can be harmful over HTTP2
- eg. techniques to improve performance in HTTP1 that doesn't help in HTTP2: inline critical path CSS in the <head>
- It helps a lot in HTTP1 but it's just making your HTML bigger in HTTP2
- Server push lets you detect HTTP2 and push CSS and JS
- A trap here is that doing it via HTTP headers will push these files on every load even though they are now cached
- Server push is unsophisticated
- Our code cannot query actual cache detection; so we have to set a cookie on the first load so the server can ignore it from then on
- There are server packages to manage this, like H20 CASPer
- So what is a 1.5 or transitional approach....
- Web fonts – they look great but they've had a negative effect on performance
- A better approach for HTTP1 is “font events” (“CSS Font Loading” on caniuse.com)
- HTTP2 will lower the chance of fonts slowing down loading time, but not eliminate it –  still need to consider lazy loading fonts
- HTTP2 offers two great ways to break the web (again)
- The new rule is, sadly, “everything you know about performance is now twice as complicated”


### CSS variables coming to a browser near you - Michael Mifsud, Front-end developer at 99designs

Twitter - @xzyfer

Why you should care...
- Most developers are familiar with the variables from Sass
- That also means they are familiar with the limitations... (e.g. scope implications, compile time)
- CSS is different - the language has different primitives to Sass
- CSS has access to the live DOM
- We have had the single variable currentColour for a while while
	- It refers to the most recent value set in the cascade
- As well as variables, CSS has custom properties
- The double dash namespaces for author-custom properties
- Single-dash is for in browsers
- Common pattern that is useful for APIs
	- :root { --background-colour: #bad455; } element { background-color: var(--background-color); } .elementvariant { --background-colour: #fec0ff; }
- Very early days, no best practice has emerged yet
- JavaScript can access CSS variables
- CSS can set a media query condition and then pass that to JS
- W3c spec - https://www.w3.org/TR/css-variables/


### CSS Selectors Redux - Kevin Yank, lead developer at Culture Amp

Twitter - @sentience

We have so many options...

- Core selectors
- Pseudo classes
- Pseudo elements
- Combinators
- There are lots of niggly little issues, like needing :blank not :empty, or :user-error not :invalid
- :not() is really powerful
	- A cool trick is :not([class]) which will find any unmodified instance of an element
	- This means you can create mutually-exclusive rules that don't compete for specificity
- What about the new stuff???
	- i keyword for case-insenstitivy
	- :matches() e.g. a:matches(:link, :visited)
	- :placeholder-shown
- Hmm this stuff is okay, but people are using BEM, frameworks, stuff with lots of classes
- Even CSS modules is just writing lots and lots of classes...
- This means people are abandoning HTML semantics
- Portlanda - put a bird on it https://www.youtube.com/watch?v=iHmLljk2t8M
	- They know just one way to make things "pretty" so they do it to everything
	- We are becoming "put a class in it" developers
- Effortless Style by Hedon talks about prescriptive/axiomatic or unintelligent/intelligent styling - http://slides.com/heydon/effortless-style/#/35
- CSS4 has cool stuff:
	- local link pseudo selector
	- reference combinator /for/
- Stuff that is still in play:
	- :has() is a form of parent selector - element:has(.something) but there is a caveat
		- there is a new profile known as the static profile which means you can only use it in JavaScript :(
- We have to use the Macguyver approach?
- This is where the "lobotomosied owl" comes from - great base style http://alistapart.com/article/axiomatic-css-and-lobotomized-owls / https://css-tricks.com/lobotomized-owls/
- Everyone should play with the selectors and give feedback to CSSWG https://www.w3.org/Style/CSS/members.en.php3


### Accessible web components without tears - Russ Weakley, Web designer and Front-end developer, A11y advocate

Twitter - @russmaxdesign

We need to ask ourselves the painful questions...

- Start with the four painful questions:
	- Have you ever navigated your site with just the keyboard?
	- Could you do every action?
	- Could you always see which element was in focus?
	- Did the tab order make sense?
- Over the past five years or so there has been a major change in the way frontend developers work
- A lot of "full stack" developers have forgotten some core principles of the web - like basic understanding of HTML, CSS, accessibility and progressive enhancement
- The rise of the Stack Overflow developers means there are people who don't know the why behind many prices of code
- People not knowing why a DIV can't go inside a SPAN
- Assistive technology is far more than just screen readers, but we can cover a lot more with a few simple tricks
- Keyboard-only usage
- ARIA – roles, state, purpose, properties (allows us to make HTML elements more meaningful for assistive tech)
- Dynamic content
	- Problem: the AT is not aware that the DOM has updated, so a simple thing like injecting a message is not announced to the user
	- Solution: aria-live
	- This also works on things like sortable tables, to announce the fact that the table has changed
- aria-live has levels
	- off: don't announce updates, but announce the change if the user focuses the element again after the update (doesn't mean the content is not announced)
	- polite: waits for the next logical pause in vocalisation, then announces the change
	- assertive: announces the update immediately, will interrupt any other activity - use very sparingly, this is not supported well
- aria-relevant
	- gives a hint about what kind of change has occurred
	- additions: nodes added
	- removals: nodes removed
	- text: text added or removed
	- all: announce all (tends to be too verbose)
- role=”alert”
	- Has implicit aria-live=”assertive” ...and is also poorly supported


- Accessible areas
	- Screen readers have two modes: read (navigate the page as normal), forms (interacts with form elements). Readers switch automatically.
	- Catch – in forms mode, content not directly related to the control may not be announced. A paragraph next to a form input is not announced – you would have to manually switch to read mode to hear it. So many users will read a form twice, once in each mode, just to make sure they're not missing things.
	- Validation gotcha – form control errors aren't announced until after the input has lost focus; and if the error message is not programmatically linked, the user may never hear it. Plus the user may never know the entire form is invalid as focus may stay on the submit button – so nothing's being announced.
- Solutions:
	- Programmatically link inputs with labels and errors (use label for to link labels and inputs; and aria-describedby to link inputs and errors)
	- Don't use colour alone to indicate invalid forms
	- Error message should have proximity to the input
	- Error should be informative
	- Send focus to the error-state input, so the user hears the information and can fix it
	- Global error messages should have jump links to error-state inputs (eg. put a list of errors at the top). Use role=alert aria-live=polite and aria-label to describe what's going on.
	- Know your tabindex: -1 means an element won't get focus; 0 means it can be focused without changing the natural tab order (don't use other values)
- Modal problems
	- keyboard users can tab out of them while the modal is active and if they are also blind, they have no idea what's happening
	- AT not informed when the modal is triggered; nor what it's for (input information? Is it an error?)
	- Focus sent back to the top of the page when the modal is closed
- Modal solutions
	- Ensure the modal is properly hidden when not in use – display:none and aria-hiden=”true”
	- Set initial focus to the actual modal, not the first form input; and set the modal to <div role=”dialog” aria-labelledby=”idofmodallabel”> … then <h2 id=”idofmodallabel”>
	- Prevent people tabbing out of the modal – cycle through the tabable elements
	- Don't intercept keys - allow people to shift-tab, use arrows, etc
	- Esc should close the modal
	- You can add extra description to the submit or cancel buttons to inform them what will happen next – where will they be taken, what happens to the data
	- Don't use “X” as the label of a close button.
	- When the modal closes – focus the relevant element (the trigger element if that is not confusing; or the element that has changed as a result of the modal's actions). Don't focus the top of the page; don't make the AT repeat the original instruction.
- Tabs (in-page tabs)
	- No programmatic relationship between the tab control and the tab panel/content – sometimes it's not clear what the content relates to
		- See the code in the demo for the various roles – tab, tabpanel, aria-labelledby
		- See the code in the demo for the various states – aria-selected, aria-hidden,aria-expanded
		- tabindex should be managed as well to prevent people tabbing through the controls (should be arrow)
		- If the tab controls are inside a list, set the LI to role=”presentation” so spurious list information is not announced
	- non-semantic elements used as controls. A SPAN used with click events is not available to keyboard users – you can't focus the element
	- Use TAB&ARROW “straight through pass” pattern.. use tab to get to the tab set; and arrow keys to get to each tab (and immediately show the contents of that tab, so hitting tab takes you to the right content). This mirrors form elements and Operating System usability.
	- If you can't get 100% of this done in the first pass – start with basic keyboard accessibility
- Some tips:
	- test keyboard-only navigation
	- check for visible focus
	- test with accessibility checking tools (see slides for links)
	- test with a screen reader – Voiceover on OSX, NVDA on Windows
	- note screen readers work (or don't) differently depending on the browser
	- get an accessibility audit


### <picture> Perfect: Designing with responsive images - Matthew Kairys, Front-end developer

Twitter - @mkairys

What are the advantages...

- A poll by Smashing Magazine in Feb 2016 showed that 58% of developers weren't using any responsive image solution
- There are many advantages to doing this, particularly with the wide range of screen sizes now available
- We want to send smaller files to devices on expensive and slow connections
- This means there can be better art direction to suit the experience
- Srcset:
	- Comma separated list of images, the browser chooses which to display
	- Can also supply a pixel density
- sizes:
	- Has a media condition, display size and fallback size
	- Allows for control of the finer points of displaying the image (e.g. full-bleed for mobile, putting a gutter around the image at higher sizes, etc.)
- <picture> 
	- Acts as a rapper for specific images and sources and gives focused art direction
- <source>
	- Each instance defines a source image and the appropriate media query to load it
- <img>
	- nested as a fallback
- Can use different file types to determine what laods
- If a browser can't use a format it skips that source and tries the next one
- Very common way to load an SVG is with a PNG fallback
- Browser support is good, apart from IE and opera mini
- So what's the catch, why aren't we using this?
	- The actual final code is verbose and fairly complicated
	- Implementation itself is quite straightforward but the design process will need to accommodate extra images
- Great resource for responsive images - http://ricg.io/


### In Search of the Element Query - Chris Wright, Front-end developer at Campaign Monitor

Twitter - @cwrightdesign

We understand the media query, it enabled us to adapt content to fit lots of devices... Enter the element query!

- We understand the media query, it has enabled us to adapt out content to fit lots of different devices
	- However our understanding of the web was very page-orientated for a long time and our technology reflected that
- Along came content-driven breakpoints
	- Should the content drive the layout?
- This meant things got really complicated!! (Chris reviewed 50 highly-regarded responsive websites and discovered one that had 905 media queries, the average was 256)
- We are now in the atomic design era
- We think in terms of small units that are combines in many contexts, but we can only do queries about the entire viewport
- Enter the idea of the element query, something like
	- .foo:min-width(300px) { // conditional css }
- This creates a potential endless loop, in this above example if the conditional CSS makes the element bigger than 300px it will not longer meet the query and won't be applied at more - at which point the query is met and the conditional CSS is reapplied...
- To date the circular dependencies / endless loop problem has not been solves, so for now there is no standards based option
- People will want things like Molten Leading and adaptive layout
- A form need to be laid out according to the space available and not according to the space in the viewport
- Element flow - properties which automatically control the way the element is displayed (uses flexbox tricks)
- Container sized ordering - this can be done using media queries plus flexbox
- display:content - collapse the element according to content
- So after all of this there is still not real container query, so what can we do?
	- Try experiments, get involved with working groups, give feedback
- http://tink.uk/flexbox-the-keyboard-navigation-disconnect/


### Adaptive Content, Context and Controversy - Karen McGrane, UX advocate, writer and content strategist

Twitter - @karenmcgrane

The web is its own medium, defined by its fluidity and accessibility... 

- The web is not print, it is not TV, it is it's own medium and we can use all sorts of devices and connections to access it...
- We do not need to fragment and silo it
- W3C's One Web philosophy - – one documented displayed many ways and places
	- https://www.w3.org/Consortium/mission
- The dream is to have one single code base, one team, one pipeline, delivering one responsive site… but so many organisations don't do that - why???
- Three strategies come up:
	- responsive – flexible fluid site that reflows continuously at arbitrary sizes; the flexibility occurs in client-side code
	- adaptive – a bit of a catch-all term for “serving something different”; but typified by serving several fixed width layouts at different breakpoints
	- mdot – whole separate site usually served at m-dot-domain-dot-com
- Karen's definition: "Adaptive means serving something different..."
- The server detects the device and serves accordingly, opposed to responsive where the client differentiates the layout
- Responsive is Google's recommended approach for mobile devices
- Responsive = completely fluid
- Adaptive = snaps into place at certain breakpoints
- There are lots of real world scenarios where you may need to serve a different version of a page - politics of a homepage for example
- Can A/B testing process cope with fully responsive sites?
- Perhaps the whole page doesn't need to be different - maybe it just needs to serve a different feature
	- The rest of the site could be responsive but that one feature could be adaptive
- Fidelity had problems serving large tables so had to serve two versions of the table
- Adjust layout fluidity on the client side - the server doesn't need to get involved in this
- Adjust content on the server side. display:none is not a content strategy
- COPE - create once, publish everywhere
- Each display of the core asset can request a subset of the content
- NPR used this for a while, but eventually went responsive
- Content should be modelled carefully
