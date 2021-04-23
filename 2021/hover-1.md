## Hover 2021 - Day One

### What's New In CSS 2021 - Adam Argyle, Developer Advocate with a CSS focus at Google, member of the CSS working group

31 features, rapid fire

**High Risk:**

Rad styles that might not ever make it into CSS

- Conditional Values
The ability to put a little mini media query where you put a value
```
div {
  flex-flow: if(100vw > 500px, row, column)
}
```
- Switch
Similar to the above, has a condition that needs to be met
```
.foo {
  grid-template-columns: switch(
    (available-inline-size > 1024px) 1fr 4fr 1fr
    (available-inline-size > 400px) 4fr 1fr 2fr
  )
}
```

- Relative units
We already have vw and vh
  - Line height
  - Cap height
  - Viewport inline
  - Viewport block

- Houdini Layout
Houdini brings your logic and your interesting layout, your interesting paint idea, your interesting animation, and they bring it into the engine - working in Chromium behind a flag
```
.houdini-masonry {
  display: layout(masonry)
}

.houdini-packery {
  display: layout(packery)
}
```

- @scope

Everything in CSS is global
```
@scope (.card) {
  header {
    color: var(--text)
  }
}
```

**Moderate Risk:**

- Container Queries
Being actively developed right now, could be supported in browser soon

```
.container-to-be-queried {
  contain: layout inline-size
}
```

- Leading Trim
Chop off excess in a text box, will trip to cap height and alphabetical baseline
```
p {
  leading-trim: both
}
```

- Houdini paint
A new way to paint so we can paint new backgrounds on images, new border images, etc. API is polyfillable
```
powdered-gradient {
  background:
    paint:(powdered-gradient, to-top, white, 1),
    #111212
  }
```

- @scroll-timeline
Scroll-timeline seeks to remedy all of the JavaScript solutions by providing a CSS and JavaScript API to creating scroll linked animations
```
@scroll-timeline scroll-fade {
  time-range: 4s
}
```

- Spelling & Grammar
In the browser, you can set spellcheck and contenteditable on an element, spellcheck pseudo-selector that will underline with a squiggly
```
::spelling-error {
  text-decoration: underline 1px red
}
```

- :target-within
Target-within is piggybacking on the idea of :focus-within

- Nesting
Being considered for prototpying, native nesting
```
code > pre {
  @media (hover) {
    @nest &:hover {
      color: hotpink
    }
  }
}
```

- Cascade layers
We often have some many different stlyes coming into a page, there are so many origins and types, this lets us name various layers of the style stack and push styles into them
```
@layer reset {
  * { box-sizing: border-box }
  body {margin: 0}
}

@import url(heading.css) layer(default)

@layer default, theme, components
```

- Foldables
Create styles so something looks like it is folded in half
```
main {
  display: grid
  gapp: env(fold-width)
  grind-template-columns: env(fold-left) 1fr
}
```

- Color level 5
The browser can pick a colour dynamically
```
.color-contrast {
  color: color-contrast(
    var(--bg)
    vs
    black, white
  )
}
```

- Masonry

Built on top of grid

```
.masonry {
  display: grid
  grid-template-columns: repeat(4, 1fr)
  grid-tempalte-rows: masonry
}
```

- Media queries level 5

```
@media (width <= 320px) {
  body {
    padding-block: 1rem
  }
}

@custom-media --motionOk (prefers-reduced-motion: no-preference)
```

**Low Risk:**

Even more available to use right now, but might need @supports and polyfills

- Color Level 4

#hex-with-alpha
#functional-notation
#lab-and-lch
#color-function

- HD color

Can this display do high-definition color
```
@media (dynamic-range: high) {
  .neon-pink: {
    --neon:glow: color(display-p3 0 1 0)
  }
}
```

- Typed custom properties

```
@property --hue {
  initial-value: 0
  inherits: false
  syntax: '<number>'
}
```

- Content Visibility

Still has a11y considerations that are being worked through
```
section {
  content-visibility: auto
  contain-intrinsic-size: 1000px
}
```

- Aspect Ration
Can transition

```
.box {
  width: 2000px
  aspect-ration: 1
}

img.square {
  aspect-ratio: 1
  width: 100%
  object-fit: contain
}
```

- ::marker
The free dot you get at the start of list items, there are limitations

```
li::marker {
  content: counter(list-item) "> "
  color: hotpink
}
```

- Conic Gradients
Can tuck them into corners, to get rid of hard lines use three colours, not just two
https://www.conic.style/

```
.conic-1 {
  background: conic-gradient(
    deeppink
    rebeccapurple
    deeppink
  )
}
```

- Containment
This is what unlocked container queries

```
article {
  contain: layout
}
```

- :focus-visible
Should the focus be visible? Knows if you are using mouse or keyboard

```
button:focus-visible {
  outline-offset: 5px
}
```

:focus-within
If a child element has focus

```
article:focus-within {
  box-shadow: var(--depth-short)
}
```

- Logical properties
Styling has historically been physical based, this allows user specific properties

```
p {
  max-inline-size: 40ch
}

small {
  padding-inline: 1ch
  text-align: end
}
```

- :is() and :where()
"is" will take the first, well, it will take the most expensive specificity item in the list and make that the specificity of the whole selector in general.

Whereas "where" will nullify all of these and it acts as if everything that's in there is worth zero.
```
:where(target, p) {
  color: red
}

:is(a,h1, h2) {
  border-color: red
}
```

- Data saver
I want to be in data saver mode

```
@media (prefers-reduced-data: reduce) {
  header: image: url(/grunge.png)
}
```

- ::cue
If you are waching a video with subtitles you are looking at this in work

```
::cue {
  color: white
  background-color: black
}
```

### Container Queries & The Future of CSS - Miriam Suzanne, Co-founder Offbird

_"Our medium is not done, our medium is still going through radical changes..."_

https://slides.oddbird.net/css-next/hover/

- Cascade layers
- Scoped styles
- Container queries
  - https://codepen.io/collection/XQrgJo


### The State of CSS-in-JS - Mark Dalgleish, Front-end Lead, Seek

- Space is dominated by two libraries, styled components and emotion
- things to think about when building a CSS-in-JS library
  - Bundle size
  - Performance
  - Flexibility
  - Abstractions
  - Static extraction
- The community is still experimenting
- A few different libraries that are tackling the constraints in different ways
  - Goober https://goober.js.org/
  - Stitches https://stitches.dev/
  - Vanilla-extract https://github.com/seek-oss/vanilla-extract
  - Complied https://github.com/atlassian-labs/compiled


### CSS Aspect Ratio - Anton Ball, Front End Developer, Doist

- Part of the sizing 4 spec, in a working draft state currently
- Aspect ratio is the ratio between the width and height of an element
- `aspect-ratio: auto | <ratio>`
- support: https://caniuse.com/?search=aspect-ratio
- https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio
- https://css-tricks.com/a-first-look-at-aspect-ratio/


### CSS Variables for Real Life - Matt Colman, Senior Engineer, Atlassian

- CSS Variables is still a bit of a buzz word. Many of us have googled it, looked at some examples, maybe even done a tutorial, but how many of us have used CSS Variables in production?
- https://codeburst.io/css-variables-explained-with-5-examples-84adaffaa5bd
- https://kentcdodds.com/blog/super-simple-start-to-css-variables
- currentColor is a CSS variable, it was the first!

### Typography superpower with variable fonts and CSS - Ananya Neogi, Frontend developer Shopify
