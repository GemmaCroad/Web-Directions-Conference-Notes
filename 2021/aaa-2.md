## Access All Areas 2021 - Day Two

### Building the most inaccessible site possible with a perfect Lighthouse score - Manuel Matuzović, Senior Frontend Developer

- Accessibility does not equal usability
- There's also a lot of criticism because there are many people who say that these numbers, these scores from Google's built in lighthouse tools, are in fact just numbers and that they don't tell anything about the quality of the site
- Things can pass an automatic accessibility test and not be accessible
- This is not a talk about Lighthouse, about the tool or about the Google Chrome team that built it
- It's about us, and how we interpret automated testing results
- WARNING: lots of sarcasm ahead, this is not how we should be building websites...
- Manuel came up with two principles:
  - Progressive degradation - every line you write, you make the experience worse for the user
  - Rule of most power - if possible, for any given task, use the most powerful language, for example don't use HTML to create a paragraph, use canvas
- Easiest way to exclude screen-reader users is to use `aria-hidden="true"` on the body, but because it isn't allowed on the body element you can wrap all the content on the page in a div and apply it to that div
  - Removes it from the accessibility tree
- Excluding keyboard users is also really easy
  - Select all items in the page in the styles and set the focus outline state to be none
- One of the most privileged groups are mouse users, we can make their life hard as well
  - In the CSS select all items in the page and set the hover cursor state to none, you can use the mouse but there is no cursor...
- You can blur or filter the opacity of text to make it totally unreadable and still get a score of 100
- Users can still view the page source, to solve this you can turn all characters on the page into HTML entities
- Testing across other tools, the results are fairly similar (WAVE, AXE, etc.)
- These tools are designed to catch low-hanging fruit, that is all
- These tools should be used at the start of the journey
- Do manual testing
- Test with real users

Full blog post by Manuel can be found [here](https://www.matuzo.at/blog/building-the-most-inaccessible-site-possible-with-a-perfect-lighthouse-score/)
[CodePen demo](https://codepen.io/matuzo/pen/joeeqy) of the site


### The Low-Hanging, High Impact Accessibility Issues For Developers - Samuel Proulx, Accessibility Evangelist Fable

- Most screen reader issues are generally low-hanging fruit
- This does not mean they are low impact
  - Fixes can bring websites from completely impossible to use to usable
  - Fixes must be made before more difficult issues are tackled
- POUR guidelines
  - Perceivable
  - operable
  - Understandable
  - Robust
    - Perceivability
      - Alt-text is missing from 26% of images online
        - Can be fixed bu simply adding an alt attribute to an image
        - Can easily be detected by automatic tests
      - 45% of form inputs on the web are unlabelled
        - Requires less than one line of code per form to fix
        - Can be easily tested
        - Makes forms much easier for screen reader users to fill in
        - Allows those with physical challenges to use autocomplete and autofill solutions
      - 86% of homepages on the internet today have low contrast text
        - Automatic checkers can catch this
        - Can be easily corrected with style changes
        - Makes websites usable for those with low and declining vision
    - Operable
      - 38% of homepages skip heading levels and 10% have no heading levels at all
        - Add semantically valid heading tags
        - Represent the structure of the content using correct heading levels
        - Screen reader users can then skip the site to find what they are looking for much quicker
      - 30% of homepages have no regions and landmarks
        - Landmarks can be added with a single HTML tag
        - Tough part is figuring out where they go
        - Makes it easier to jump to parts of the page
      - ARIA is overused
        - Use natives HTML over ARIA where possible
        - The incorrect use of ARIA is a big problem for screen reader users
    - Understandable
      - Ambiguous link names were present on 22% of pages
        - Learn more, click here, more info, etc.
        - Repeated link names can be detected by tests
        - Make link names unique and meaningful
        - Will make it easier for users with cognitive challenges
      - Only 72% of web pages define a lang attribute
        - Top level HTML tag that indicates the language of the document
        - Hugely helpful for screen reader users (what language of braille to use, what language to output speech in)
        - Helps with SEO
    - Robust
      - 30% of websites don't allow easy zooming and resizing
        - Makes websites useable for those that use screen magnification
        - Fixable with very simple style changes
        - Fix that makes the website better for everyone
      - Over 50% of webpages that have video, have that video auto-play
        - Can make it impossible for screen reader users to hear the text-to-speech voice
        - Bad experience for users on low bandwidth
        - Can be distracting for users with cognitive challenges
        - Add or remove a single attribute and can be checked with automated tests
- Low hanging fruit is easy to fix, easy to test, improves SEO, makes better experiences for everyone and should be done before other more complex fixes are made


### Forced colors explained - Kilian Valkhof, Founder Polypane

- Windows only feature at the moment
- Type of media query
- Limits the number of colours
- Lets users pick those colours
- High contrast mode is useful for many types of users
- One of the only features to force all colours to use
- 4% of users using high-contrast mode
- Get to save one of the modes as "your own theme"
- No way to add, export or import a previously created theme
- Browsers are not emulating forced colours yet
  - To test you need a windows install
  - VMs only available for older browsers
- Browser support is good for the media query
- Reader mode - reformats content is a user chosen style and layout
- Prefers contrast upcoming media query - only support in Safari right now, users can ask for more or less contrast
- All about reducing visual complexity
- Dev tools will also be in high-contrast mode
- Not about making your site look good, but about respecting the visitors preferences
- Add borders to compensate for backgrounds
- Make sure icons are still visible
- Check for hidden content, especially hidden SVG icons
- Don't use colour to convey meaning
- Don't put text in images, they won't conform to the users preferences
- Focus styles should still be indicated

[Mozilla docs](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/forced-colors) on forced colors


### Color Contrast and WCAG - Todd Libby, Accessibility Analyst Webstaurant Store

- [WCAG Guideline 1.4.3](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html)
- [WCAG Guideline 1.4.6](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast7.html)
- [WCAG Guideline 1.4.11](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html)
- Low contrast is the number one failure across the web for accessibility issues
    - 86.4% of home pages surveyed in Feb 2021 had contrast errors of some sort
- Font weights, sizes and colours matter
- Test colour palettes
- Avoid stark contrast with text
- Captions: readability is the most important aspect of captions, no other rules matter
  - Can be particularly bad with busy backgrounds
- A11y is a right, **NOT** a privilege

Useful sites for checking contrast:
- https://whocanuse.com/
- https://contrast-ratio.com/
- https://webaim.org/resources/contrastchecker/
- https://contrastchecker.com/


Useful browser extensions:
- Wave
- Axe
- Tools are available in most dev tools, though some are flagged as experimental


### Accessible SVGs - Heather Migliorisi, Accessibility Program Manager Blackhawk Network

- [Responsive Huggy Laser Panda Factory (using SVGs)](https://codepen.io/sdras/pen/waXKPw)
- Hide decorative images
- Provide meaningful alt text
- Add roles to elements to make sure they map properly
- Provide focus styles
- Make sure images aren't lost in high contrast mode
- Test early, test often

[Slides](https://hmig.github.io/webdirections-accessible-svgs/#/)
[CSS Tricks article](https://css-tricks.com/accessible-svgs/)


### Making Motion Inclusive - Val Head, Senior Design Advocate Adobe

- It's a common misconception that a11y can only come at the cost of creative motion
- We can be purposeful, creative and expressive without sacrificing a11y and inclusion
- Prefers Reduced Motion preference and media feature
- On the user end, it's a preference that can be turned on through the operating system
  - Available on desktop and mobile
- Browser support is really pretty good, see [here](https://caniuse.com/?search=prefers-reduced-motion)
- Respecting the preference isn't required, but it is more inclusive and we should
- What the query looks like:
    ```
    .animation {
      animation: pulse 1s linear infinite both;
    }

    /* Tone down the animation to avoid vestibular motion triggers like scaling or panning large objects. */
    @media (prefers-reduced-motion) {
      .animation {
        animation-name: dissolve;
      }
    }
    ```
- Motion animation triggered by interaction can be disabled
- Motion animation does not include changes of colour, font and styles
- Types of motion effects that we should implement this on:
  - Multi-speed or multi-directional movement (yes, this includes parallax effects)
  - Spinning and vortex effects
  - Constant motion near text
- All animation often gets lumped into the same bucket
- Animation can improve UX and accessibility when used purposefully
- "any animation that creates the illusion of movement..."
- How do we design with this user preference in mind?
  - Identify potential triggering effects
  - Decide on the best reduced effect based on the context (replace with a non-motion effect?)
- There is not a one-size fits all solution
- The user isn't asking for a broken site or devoid of all design details
- They're asking for a site that won't make them sick
- Awareness of this preference is still growing
- Motion toggles:
  - Can still be useful, give the user a way to opt out in the browser
  - Animal Crossing [website example](https://www.animal-crossing.com/new-horizons/)

[Mozilla docs](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)
[Webkit article](https://webkit.org/blog/7551/responsive-design-for-motion/)
[Example CodePen](https://codepen.io/marcysutton/pen/yqVVeY)
[Smashing Magazine article: Design Reduced Motion Sensitivities](https://www.smashingmagazine.com/2020/09/design-reduced-motion-sensitivities/) by Val


### Overlays Underwhelm - Adrian Roselli, Consultant

- What gaps are these overlays filling?
- There are more tools and features available to users and developers than ever before
- What is an overlay?
  - AOverlays are a broad term for technologies that aim to improve the accessibility of a website
  - They apply third-party source code (typically JavaScript) to make improvements to the front-end code of the website
- Tend to overstate their abilities
- Much of WCAG requires human context to test
- The tools themselves can often present accessibility barriers
- The tools do not prevent people from making WCAG violations
- These tools don't protect from lawsuits, despite what some of them may claim
  - Many lawsuits don't name the vendor
- In 2020 over 250 companies were sued after investing in overlays
- Potential privacy risk, scripts must parse all content
- GDPR conformance is questionable
- Overlay vendors will over promise and under deliver
- They use fear of lawsuits to sell their product, not wanting to help the end users
- Some users have even written tools for blocking these overlays

[Interesting site](https://overlayfactsheet.com/)
[WordPress removes fake reviews for accessible plugin](https://wptavern.com/wordpress-org-removes-fake-reviews-for-acessibe-plugin#:~:text=After%20noticing%20suspicious%20review%20activity,thanks%20to%20Dolson's%20detailed%20research.)
[People with disabilities say this AI tool is making the web worse for them](https://www.vice.com/en/article/m7az74/people-with-disabilities-say-this-ai-tool-is-making-the-web-worse-for-them)
