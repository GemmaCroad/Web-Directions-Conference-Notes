## Access All Areas 2021 - Day One

### Accessibility APIs: Where the magic happens! - Adem Cifcioglu, Co-Founder & Director of Accessible Technologies Intopia

- The accessibility tree: accessibility tree is a subset of the DOM that is a hierarchical representation of the accessibility information of elements in the UI
- Accessibility APIs: accessibility APIs are a collection of interfaces to facilitate the communication of accessibility information about a user interface to assistive technologies
- The markup is the foundation of any website
- Using semantic HTML and native elements will give you a lot of the accessibility you need for free
- What's in the accessibility tree:
  - name
  - roles
  - states
  - properties
  - relationship
- What's in an accessible name?
  - Can come from many sources, can come from the element's content, an attribute, an associated element or ARIA Attributes
- Accessibility APIs act as translators
- Different browsers each have different accessibility APIs
- What happens when something changes?
    - Web page -> accessibility API -> accessibility tree -> assistive technologies
- You can view the accessibility tree in the dev tools of all modern browsers
- With iOS and Android, you can plug in your device and use the dev tools in Safari and Chrome to view the API or view the tree on mobile


### More to give than just the div: semantics and how to get them right - Hidde de Vries, Accessibility specialist

- Semantics: what stuff means
- Ludwig Wittgenstein famously concluded, and this contradicts his own earlier work, that the meaning of a word is not the thing it refers to, but its use in the language
- Kate Crawford: Atlas of AI (book) - classification is hard and AI isn't great at it
- Semantics on the web:
  - With XML schemas, you can create your own language
  - With an XSD file, you can define your own schema and say, what's what in your world, which is helpful for validation
- HTML is a standard way for your website to declare its semantics
- It's not a way to declare what something looks like on the page
- HTML enables:
  - A multi-device web
  - Default style sheets, even in documents with no styles there can be some kind of visual distinction
  - Browse by heading, only works if headings are marked up as headings
  - Default behaviour, as it is tied to semantics
  - Reader mode, if pages have useful markup like headings and lists and images, reader modes and browsers can read them
- Not all websites get their HTML right
- Hire for HTML expertise, HTML knowledge in a team can save an organisation money
- Semantics in HTML is in `<elements attributes="value">`
- Recent Twitter button controversy, Corey LaViska echoed that in design systems, he likes to use one component for buttons and for links
- Buttons that look like links, links that look like buttons
- Key questions to ask when building a design system
  - Can it output the right semantics when I need them, and do the docs clearly explain which semantics should I pick
- Bruce Lawson explains semantic HTML is a posh term for choosing the right HTML element for content
  - He goes on to say that this isn't a philosophical exercise, it has observable practical benefits for the end user
- There are a lot of tags available in HTML, and it makes sense as developers we don't know them all
- developers.whatwg.org is a great resource
- Overriding semantics causes problems for assistive technology, e.g. using display can override things
- If you do `list-style: none`, Safari will not expose that as a list to assistive tech
- Sometimes browsers will undo semantics when you nest unexpectedly
- There are many heuristics that screen readers apply that could somewhat mess with our intentions
  - When you set `text-transform: uppercase`, some assistive technologies will read it like an abbreviation
  - Using the CSS feature generated content to add some content for styling reasons, like an icon, this content isn't just considered stylistic or decorative by assistive technology, it becomes part of the accessible name
- The future
  - Does the web need more semantics?
    - Design systems commonly contain things that are not built into HTML
    - The open UI community group at the W3C is trying to change this
    - The goals of open UI:
      - Document component names as they exist today
      - A common languages for describing UIs and design systems
      - Browser standard for web app components
  - Do developers of the future still need to define semantics, or can machines help?
    - Hidde is sceptical about this
    - AI is bad at understanding intentions and context, and this is at the core of semantics

[Slides](talks.hiddedevries.nl)


### ARIA Spec for the Uninitiated - Gerard K. Cohen, Accessibility Experience Team, Twitter Engineering Manager

- ARIA stands for accessible rich internet applications
- ARIA is a set of attributes that extend HTML
- These attributes are used to add roles, states and properties to HTML elements, so that they can be better understood by assistive technologies
- ARIA exposes more information to the accessibility API
- Dangers of ARIA:
  - ARIA is very powerful and essential to providing the level of dynamics available in today's web
  - Using ARIA incorrectly can cause some serious barriers for users of assistive technologies
  - ARIA support varies depending on the browser and assistive technology
  - Throwing ARIA at a problem is not always the solution
    - A survey of 1 million home pages by WebAIM in February of 2021 stated that "homepages with ARIA present average 41% more errors than pages without ARIA"
  - No ARIA is better than bad ARIA
  - You need to respect ARIA, and take the time to learn it and understand it
- Official ARIA Standard
  - Docs available [here](www.w3.org/TR/wai-aria)
  - Treat the official ARIA standard as an API guide to get the most up-to-date information on available options
  - [5.3 categorisation of roles](https://www.w3.org/TR/wai-aria/#roles_categorization)
    - ARIA roles provide semantics and the ARIA 1.1 Standard provides 70 usable roles
    - You can not make up your own ARIA roles
    - Of these 70 rolls in version 1.1, only 29 of them are interactive widget rules
    - In most cases, you can not pick and choose which roles are used to compose a widget
    - There are very strict parent child relationships between certain roles
    - Be very careful about how components are nested, we can break our well-intended accessibility if we don't respect the parent child relationships with roles
    - Roles do not provide interaction, they simply just describe what something is, but do not provide the expected behaviour
  - [6.6 States and properties](https://www.w3.org/TR/wai-aria/#state_prop_def)
    - As of ARIA 1.1, there are a total of 48 states and properties
    - You can not make up your own states and properties
- The five rules of ARIA
  - 1: Don't use ARIA if you can use HTML instead
    - `<div role="banner"> use <header>`
    - `<div role="main"> use <main>`
    - HTML can provide semantics, focusability and interaction
    - It's less work, less code and less of a surface area for bugs in the user experience
    - [Periodic table of semantics (draft)](https://gerardkcohen.github.io/periodic-table-of-semantics.html)
  - 2: Don't change native semantics
    - Example, adding a role link to a button
    - Roles specify semantics and semantics are a contract, the element needs to behave as expected for the role, but links don't act the same as buttons - this is breaking that contract
    - Just use a button!
  - 3: All interactive roles need to be operable by a keyboard
    - Keyboard support is fundamental for accessibility support
  - 4: Don't use `role="presentation"` or `aria-hidden="true"` on visible focusable elements
  - 5: All interactive elements must have an accessible name
    - If semantics and roles give us the type, then the accessible name gives us the what
    - Important for screen reader and braille users
    - It's also important for voice recognition users to be able to identify and interact with controls on a page
- [ARIA authoring practices](https://www.w3.org/TR/wai-aria-practices)
  - These docs demonstrate about 27 different widget roles and patterns
  - No guidance on how to work around bugs in browsers or assistive technologies
  - There is no guarantee that browser vendors and assistive technologies are going to support all the roles, states and properties
  - There's not yet a standardized approach for providing touch interactions that work across mobile browsers
  - Test! Test! Test! - preferably with real users!
  - _"The accessibility of interactive content cannot be confirmed by static checks, alone. Developers of interactive content should test for device independent access to widgets and applications, and should verify accessibility API access to all content and changes during user interaction."_

[Accessibility courses available on Pluralsight](https://www.pluralsight.com/authors/gerard-cohen)
[Slides](http://bit.ly/2Zc6TDf)


### Deep dive into ARIA - Nicolas Steenhout, Independent accessibility consultant

### Understanding Live Regions - Ugi Kutluoglu, Accessibility Lead Carbon Health

- Primarily intended for screenreader users, live regions are a powerful tool that make announcements every time content changes within a designated part of a webpage
- Live regions are very powerful because they allow developers to control screen readers to announce anything they want them to, whether the user wants to hear it or not
- When used properly and in moderation, Live regions can enhance the usability of your website immensely, but conversely, they can be a usability nightmare
- They can be very disruptive to a user's experience when implemented poorly
- Think of live regions like these announcements on a loud PA system, they are helpful when used in moderation and when providing important information
- When used too much, they disrupt the user's ability to use and enjoy your product
- Under the hood live regions are controlled with JavaScript and work by listening to mutations inside a specifically designated DOM node
- Live region announcements are transient, meaning once the announcement is made, they are gone forever
- Screen readers work by linearising content, so when the user is focused on one part of a webpage, they will not be made aware of content changes happening elsewhere
- Some examples of this might be a new chat message while the user is busy typing a response, an ebook reader or a stock market ticker that periodically refreshes web content
- Once we have designate a DOM node to be a live region that specific DOM node will be checked for changes periodically
- When new content is inserted into the region, users will be notified of the new content regardless of their focus position on the page
- Live regions can be placed anywhere in the DOM, as long as it is inside the body tag
- Any HTML tag can be used, but most commonly a generic tag, such as a div, seems to be the prevailing method
- Can also use a semantic tag such as the section element
- Live regions can be visible on the screen or hidden from visual users by using the usual hidden CSS techniques, such as moving the container outside the viewport, view port and clipping content
- However, they cannot be hidden using the display or visibility property
- Sometimes it's just best to keep the container visible
- Provide a politeness level `"aria-live="polite"`:
  - polite - user needs to know
  - assertive - user needs to act
  - off (default)
- The ARIA Specification has extra properties that gives us final control over how live regions behave
  - Support for these attributes is patchy at best
  - `aria-relevant`
  - `aria-atomic`
  - `aria-busy`
- We are not limited to aria-live attribute to create live regions
  - Can use ARIA roles alert and status
  - One interesting quirk about `role=alert` is that it pretty much works on every single screen reader, without having to insert the container in DOM first
  - Progress indicators, they're not technically live regions, but when you put a progress bar in your screen, some screen readers will either announce the progress as a percentage value or generate sounds and tones, depending on the progress
- Need to make sure the content is cleared out between updates, waiting a bit in-between
- Some common examples in the wild:
  - Toaster pop up messages
  - Loading screens / skeleton screens
  - Counts, countdowns and timers - do not announce on every key press!
  - Form errors
    - Inline validation
    - Validation blur
    - Validation on submission
  - Messaging / chat interfaces
- Common mistakes using live regions:
  - Assuming screen readers only output speech
    - `<span aria-label="wuh keg">WCAG</span>` -> don't do this, this is bad!
  - Assuming everything will be announced
    - Not always guaranteed to work
    - Can be announced in the incorrect order
  - Wrapping entire sections and components in a live region
    - Not meant to wrap large sections of a page
  - Competing live regions
    - The more you have, the more unpredictable they become
    - Manage the message queue to avoid race conditions
  - Conveying state with live regions
  - Too many updates in too little time
- Why live regions fail:
  - Two regions firing at the same time
  - Text alternative computation
  - Non-text nodes in announcements
  - CSS issues
  - Screen reader heuristics
  - Bad mutations
- Debugging:
 - Add a break point
 - Mutation observer can be attached to any DOM node and will fire whenever there is a modification on that element
 - [NerdeRegion extension](https://chrome.google.com/webstore/detail/nerderegion/lkcampbojgmgobcfinlkgkodlnlpjieb)


### What You See Is What I Get - Léonie Watson, Director and co-founder Tetralogical



### SpeakingNaturally on Dragons and other alternative navigations - Kate Kalcevich, Head of Services Fable



### Intro to Cross Screen Reader Testing - Weston Thayer, Founder Assistiv Labs
