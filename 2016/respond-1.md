## Respond 2016 - Day One

### Laziness in the the Time of Responsive Design - Ethan Marcotte, Web Designer, Web Developer, and writer

Twitter -@beep

Intelligent laziness could be a virtue...?

- A webpage should be a network of content that can be rearranged at any screen size to convey a message
	- It should all be one holistic design - don't think of it as seperate designs
	- It should not be about individual device screens
	- Our layouts are becoming more flexible and responsive; our interfaces, more immersive
- We are living in a time where we have to deal with more browsers and more device sizes that ever before
- Access  to the web via game devices is increasing?
- 60% of the worlds web connections are sub 3G...
- Laziness is bad though.... right? 
	- Intelligent laziness could be a virtue, but how do we embrace that in Responsive Design?
- The Illusion of Life - Disney Animations (how disney defined the animation medium)
- The web is still young, we are still defining our medium
- We should be thinking about the content outside of the device context
- Modern frameworks feel conceptually heavy and often have a lot of baggage, there is often a lot of focus on one page still
- The Web needs more philosophical frameworks - conceptual
- The Wittenburg Museum and the "responsive W"
- Karl Gerstnerr - Designing Programmes
- Nathan Ford - Content-out Layout
- Design a vocabulary to support your decisions!
- Making it fit should the the baseline - how do we make the content feel at home?
- Navigation:
	- Maybe as an industry we have a hamburger problem...?
		- More and more sites using hamburgers as navigation on all devices
		- Icon driven navigation should be user tested
		- Just because we can conceal content, doesn't mean we should - how valuable is the content if we are okay with hiding it?
	- Don't avoid the hard stuff!!!!!!
	- Examples of interesting navigation:
		- http://www.bbc.com/
		- http://www.theguardian.com/au
		- https://www.coop.se
		- https://www.filamentgroup.com/
		- http://www.frankchimero.com/writing/
	- Maybe it's about a conservation of effort?
- Animations:
	- Design the transaction, not the interface
	- A well designed responsive design should be device agnostic!
	- Design deffensively?
	- Can the users browsers hand the advanced code? 
- The web is everywehre and is every size...
- “In the beginner’s mind there are many possibilities, but in the expert’s there are few” - Zen Mind


### How we learned to love iterative design at Fairfax - Dina Gohil & Lucinda Burtt, Fairfax Media

Twitter - @dinagohil and @LucindaBurtt

Walking the line between internal needs and commercial considerations... A redesign of the SMH site.

- Get the right people in place as quickly as possible
	- Clear goals
	- Constant delivery and iterations
	- A cross functional team
	- Make fast decisions together
- Set page performance as a KPI?
- Deliver high value items first
	- No wireframes???? "Hour of power" - UX, UI, devs capped at 60 mins all in one room
	- Quick and dirty is okay - use style tiles and design principles
		- Needs to be essential, purposeful and useful
- "Tablet is where adaptive design lives or dies"
- Lean user testing and then feed the results into the build
- Internal front-end shop of component that are like Lego blocks, can be re-used and fit together
- If something isn't easy to share socially then the user won't share it
- Project lessons:
	- Cultural change isn't easy but can happen
	- Choose your battles
	- Have a transparent backlog
	- Communicate that there will be further interations
- Design lessons:
	- Ditch perfect design
	- Adapt an iterative mindset
	- Design for today - that is all you can do
	- Try, try, try again...
- It's important to have the freedom to fail...
- http://beta.smh.com.au/


## Incremental responsive redesign at Kogan.com - Simon Knox, Front-end Developer at Kogan.com.au

Twitter -@psimyn

Incremental responsive rewrites allow sites and web apps to transition from desktop-only, without the need for ever stopping existing development. 

- Used to have two codebases at Kogan, one for mobile and one for desktop
- Don't have fixed width on page containers!
- Responsive goals:
	- Feature parity
	- Responsive design
	- Speed - it shouldn't be slow just because it is responsive
	- Consistent
	- Doesn't break stuff!
- Start simple
- Hacks and bad advice:
	- If float layouts work then keep using them
	- Don't use a wrapper class for legacy code, it increases the specificity and encourages bad code
	- If desperate for an override then chain duplicate classes, pretty nasty but it works eg. .foo.foo.foo {} 
	- CSS vars - start near the implementation and expand from thre
	- Don't worry about big ugly selectors at first, get it working and then optimise
	- Use the checkbox hack to avoid unnecessary JS


### SVG + CSS: A designer's delight - Sara Soueidan, Freelance Front-end Web Developer and SVG advocate

Twitter - @SaraSoueidan

SVG can be used to extend the capabilities of CSS...

- http://styleguides.io/examples.html - amazing examples of great styleguides / living styleguides 
- http://tympanus.net/codrops/2014/08/19/making-svgs-responsive-with-css/
- SVG intro:
	- The four main SVG grouping and referencing elements are: <g>, <defs>, <use> and <symbol>
		- The <g> element (short for “group”) is used for logically grouping together sets of related graphical elements
			- Grouping elements together is useful for when you want to apply a style and have that style be inherited by all the elements in the group, and is particularly useful for when you want to animate a group of elements while maintaining their spatial relationships with each other
		- The <defs> element is used to define elements that you want to reuse later
			- Defining elements with <defs>is useful for when you want to create sort of a “template” that you want to use multiple times throughout the document
			- Elements defined inside a <defs> element are not rendered on the canvas except if you “call” them somewhere in the document
		- The <symbol> element combines the benefits of both the <defs> and the <g> elements in that it is used to group together elements that define a template that is going to be referenced elsewhere in the document
			- Unlike <defs>, <symbol> is not usually used to define patterns, but is mostly used to define symbols such as icons, for example, that are referenced throughout the document
			- The <symbol> element has an important advantage over the other two elements: it accepts a viewBoxattribute which allows it to scale-to-fit inside any viewport it is rendered in
		- The <use> element is the element you use to reference any element defined elsewhere in the document
			- It lets you reuse existing elements, giving you a similar functionality to the copy-paste functionality in a graphics editor
			- It can be used to reuse a single element, or a group of elements defined with the <g>element, the <defs> element, or a <symbol>


### Farewell Photoshop: advanced CSS image techniques - Jessica Edwards, Creative Developer at Snakk Media

Twitter - @jsscclr

Create engaging visual effects with just CSS...

- linear-gradient() mostly takes the direction, angle and colours to produce a gradient. Nice and simple. If you need to tweak this during creative it's easy – just change the code or use a variable.
- radial-gradient() is much the same, setting a shape and origin. However you can also layer these, eg. to put repeating dots above a background.
- repeating-radial-gradient() is a little hard to find a real use case for, although it looks psychedelic
- repeating-linear-gradient() is great for creating stripes; or layer them to create effects like wood panelling
- blend-mode() example was polka dots over a pic of a cat
- background-blend-mode: blend-mode
- mix-blend-mode: blend-mode really great for having an element's background blend into the page background; and can even be used with videos.

Considerations:
- Browser support for these properties varies a great deal
- Consistency is not at all guaranteed across devices
- Accessibility needs to be considered – very easy to lose contrast or make text unreadable
- mix-blend-mode creates a new stacking context so be careful...

Filters
- Lots of great options – blur, brightness, hue-rotate
- Can be chained/combined
- Has some performance problems, eg. opacity can really thrash rendering
- drop-shadow() is nice as it can snap to transparent areas in an image
- hue-rotate is useful because it rotates the colour wheel – so if you need to present a lot of differently-coloured items, you can use one and apply hue-rotate

Considerations:
- Much the same considerations as properties – support, a11y, etc.
vw + vh === vnice - Craig Sharkie, JavaScript Developer and Author


### Title missing

Twitter - @twalve

In the continued flux of viewports, allowing those viewports to dictate scaling truly embodies the spirit of Responsive Design...

- The viewport is the area where the browser renders the site
- Browser supports is incredibly good for viewport units: http://caniuse.com/#feat=viewport-units
- What are viewport units?
	- 1vw = 1% of viewport width
	- 1vh = 1% of viewport height
	- 1vmin = 1vw or 1vh, whichever is smaller
	- 1vmax = 1vw or 1vh, whichever is larger
- Viewport units allow you to tightly couple the size relationship of, say, a typographic header and the content it goes with
-  Mike Riethmuller - http://madebymike.com.au/writing/precise-control-responsive-typography/ 
- Danny Markov - http://tutorialzine.com/2015/05/simplify-your-stylesheets-with-the-magical-css-viewport-units/
- Chris Coyier - https://css-tricks.com/viewport-sized-typography/


### Designing secure experiences - Rachel Simpson, UX Designer at Google Chrome

Twitter - @rilan

The world is moving inside digital devices and we are the gatekeepers as people live more and more online...

- Users are the weakest link the in the security  chain... Are they really?
- User are only human at the end of the day, and that means the following things are a factor:
	- Memory 
	- Attention, not all about is, peripheral details can be filtered out
	- Cognitive load
	- Previous context
- Users are still struggling to create secure different passwords, still using the same password over and over
- The policies associated with passwords can trip users up
- Each email address in America is associated with ~130 different accounts!
- Memory is a limited resource that gets worse with time
- Users tend not to know if a password is hard to crack or not
- What can we do to help users?
	- 2 factor authentication (possibly with tokens?)
	- We need to be more flexible - but not too flexible because this is still security!
		- Users don't actually notice the security triangle in the address bar
		- Attention is focused on the task at hand...
	- Be timely and meaningful with warnings
		- Should only appear when relevant
	- Interstitials
		- When Google Chrome changed their SSL warning the number of users clicking through anyway dropped from 63% dowm to 38%
		- We should always remember that "making decisions has a cost..."
	- Offer a clear opinion
		- If we lower the difficulty of the decision it helps the users
- Phising - there is no patch for human stupidity
- Users don't know what they don't know...
- The Monkey Business Illusion - https://www.youtube.com/watch?v=IGQmdoK_ZfY
- Always know your audience!
