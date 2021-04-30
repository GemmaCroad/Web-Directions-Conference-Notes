## Hover 2021 - Day Two

### Neurodiversity (and why you hate CSS) - Facundo Corradini, Front-end Developer

- What is neurodiversity?
  - Traditionally, sociologists and neuroscientists have been classifying people in two broad groups according to their neurocognitive functioning: neurotypical referring to those who adheres to the societal standards of "normal", and neurodivergent for those who diverge substantially from it, such as people in the autistic spectrum disorder, ADHD or dyslexia
  - Quite a negative way of looking at it
  - In 1983, psychologist Howard Gardner shook the neurosciences world when he proposed the existence of multiple intelligences
  - He wrote a set of criteria from which he derived different intelligences modalities, among which we can find: Visual-spatial intelligence, dealing with the spatial judgment and the ability to visualize with the mind's eye
    - Linguistic-verbal, dealing with the ability to understand, and reason concepts using words, and more broadly linked to problem solving, pattern recognition, and working memory
    - Logical-mathematical, that obviously deals with logic, abstractions, numbers, and critical thinking
    - Bodily-kinesthetic, dealing with the ability to control our bodies in a skillful way
    - Musical, interpersonal, and extrapersonal, all pretty self-explanatory
- But where exactly does CSS fit in all of this?
  - Some companies give the CSS tasks to the front-end developers, which lately have been dealing mostly with JS-heavy stuff
  - Other companies lure programmers in by boldly claiming: "Our designers make the CSS." At the end of the day, neither group seems to be enjoying it
- Is CSS a design task?
- It results in a visual representation, but looks an awful lot more like coding, and there are two key differences: graphic design very specifically instructs the final result, while CSS only provides suggestions for the browser, which has the final word in how things are represented.
- Graphic design usually deals with known sizes, while designing for the web is essentially designing for an unknown, infinite canvas.
- Is it closer to programming then?
- Is CSS a programming language?
- Maybe it's not that simple and depends on what we understand by 'programming language'.
- _"CSS is a declarative, domain-specific programming language..."_
- _"CSS is more of a language than it is programming..."_
- With CSS, we are not really designing the interface, we're describing, telling the browser: _"This is how I like things to look and feel"_
- It's up to the rendering engine to provide the final result.
  - It will make the calculations to give each element the right size and set it in the right place, work out how they relate to each other and even adapt them to the different viewport sizes.
  - It might not truly understand what we meant by something and choose to discard that part, but still do its best to keep the rest of our conversation going.
- We can see browser compatibility as if speaking with someone with different levels of CSS vocabulary
- CSS has grammar
- CSS is really, really contextual - stacking context, cascade, origin, formatting context, specificity, inheritance etc.
- CSS is therefore a rich and complex language
- CSS has idioms
- A crash course only leads to a crash
- Coding boot camps and courses everywhere are brushing over CSS to get people as fast as possible to the JS heavy part, as that's where most of the demand from the industry is
- Practice expanding your CSS vocabulary
- Expand your social sphere to include more CSS people
- You shouldn't feel obliged to learn CSS - ou might still find it out of your scope, lack interest, or simply cannot wrap your mind around its linguistic nature
- Allow people to shine in their trade
- Why are we forcing designers and developers to do CSS instead of seeing the value of a third role, and pushing to integrate somebody else into the team?
- Celebrate diversity!


### The New CSS Logical Properties - Elad Shechter, CSS/HTML Architect

- The internet wasn't created for regular websites like most of it is today
- One of the basic things that we really use the most, reading content, isn't implemented in a great way
- Creating a multilanguage website, until now, required different style sheets for the same website, and lots of duplication
- Axis of the web
  - Two axis
    - Block axis: Main flow of the site (top to bottom)
    - Inline axis: Left to write for English, but in Japan it's top to bottom
    - Maybe the inline axis is being rotated 90 degrees to the right? But this is only half of the truth, because in traditional Japanese and traditional Chinese languages, it is like to take an English website and rotate all of it 90 degrees to the right.
    - And now, the header of the website is on the right.
    - The footer of the website is far on the left.
- To control the block axis we have the `writing-mode` property
- Has horizontal value as default
- For traditional Chinese or Japanese we can now use `vertical-rl` meaning "right to left"
- To control the inline axis we have the `direction` property
- `ltr` and `rtl` sets the direction of the text
- New logical properties
  - block-start
  - inline-start
  - inline-end
  - block-end
- These properties are not fixed, the positions change according to the type of language
- The top doesn't need to be the top anymore...
- In the past CSS positions had physical direction, but now these need to be updated to logical direction
- We can fix a lot of the past problems with CSS positions
- We just need to update the way we think
```
Text-align
text-align: left = text-align: start
text-align: right = text-align: end

Float
float: left = float: inline-start
float: right = float: inline-end

Resize
resize: horizontal = resize: inline
resize: vertical = resize: block

Coming Soon!
background-position-inline
background-position-block
background-repeat-inline
background-repeat-block

Assume
transform-origin-inline
transform-origin-block
```
- CSS Flexbox from the beginning was built according to the logical directions of the flexbox
- CSS Grid is already built in a logical direction
- [Browser support](https://caniuse.com/?search=css%20logical%20properties) - not all properties are available in all browsers
- Shorthand that has been used historically can be problematic to update
  - Optional solution: `margin: logical 10px 20px 8px 5px` - using the logical keyword
  - Another option being considered: `html { flow-mode: physical, flow-mode: logical }`
    - [Spec](https://github.com/w3c/csswg-drafts/issues/1282#issuecomment-443253091)


[Slides](https://docs.google.com/presentation/d/1p4iUSyWolqlG_g39sXWKQ1PTVW2jzdMtnPb_F8tQe8k/edit#slide=id.g51aa62e118_0_20)
[Examples](https://codepen.io/elad2412/pen/oQJmYQ)


### Beyond responsive design: new and future media queries - Kilian Valkhof, Browser Developer Polypane

- Responsive design - the way a design fits into different sizes
- However, browsers haven't stood still in the decades since the term responsive design was coined, and new media queries let us adapt websites not just to device properties like screen width and height, but also to user preferences
- `@media (prefers-color-scheme: dark)`: users can have a preference for a light or dark ui
  - To implement "cheap dark mode" on an existing site, invert all the colours, then hue shift by 180 degrees
- `@media (prefers-reduced-motion: reduce)`: large motion, when not expected, can cause problems for people with vestibular disorders - animations and transitions are rarely essential to a site
  - Can also check JS Animations
- `@media (prefers-reduced-data: reduce)`: tells the browser the user wants to use less data, or appreciates a faster website experience - available in Chromium already
- `@media (prefers-contrast: more)` - not available in browsers yet, in Safari preview it maps to the "increase contrast" a11y option in MacOS - what does less contrast look like, dim the blues?
- `@media (forced-colors: active)` - overwrites everything depending on the users personal preference
- `@media (color-gamut: p3)` - lets you detect if your site is being used on a screen with a wider gamut, therefore using colours outside of the sRGB colour space
- `@media (prefers-reduced-transparecnet: reduce)` - used to tone down transparecny
- `@media (light-level: washed)` - built in light sensors could detect light levels in operating systems
- `@media (environment-blending: subtractive)` - how the screen is blended with the environment
- `@custom-media` we can improve our CSS by only defining a media query once and using it everywhere
- [The Complete guide to CSS media queries](https://polypane.app/blog/the-complete-guide-to-css-media-queries/)


### CSS Comparison Functions - Ahmad Shadeed, UX Designer, Front-end Developer Uxable

- The motivation for CSS comparison functions, it's all about comparing multiple values
```
.title {
  font-size: clamp(1rem, (2vw + 1rem), 2rem)
}
```
- [Browser support](https://caniuse.com/?search=min())
- What are CSS Comparison Functions?
  - It’s all about comparing multiple values and representing one of them based on the used function
- The min() Function
  - The min() function contains one or more comma-separated calculations and represents the smallest value of them
```
  .element {
  width: min(50%, 500px);
}
```
- The max() Function
  - The max() function contains one or more comma-separated calculations and represents the largest value of them
```
.element {
  width: max(50%, 500px);
}
```
- The clamp() Function
  - What clamp() does is that it clamps a value between two determined values, minimum and maximum, it takes three parameters (min value, preferred value, max value)
```
.element {
    width: clamp(200px, 50%, 1000px);
}
```
- How clamp() Is Calculated?
```
.element {
    width: clamp(200px, 50%, 1000px);
    /* Assuming the viewport width is 1150px */
    width: max(200px, min(575px, 1000px));
    /* Resolves to */
    width: max(200px, 575px);
    /* Resolves to */
    width: 575px;
}
```
- We can use math expressions without calc()
```
.title {
    /* Force the font-size to stay between 12px and 100px */
    font-size: clamp(12px, 10 * (1vw + 1vh) / 2, 100px);
}
```
- Use Cases for CSS Comparison Functions
  - Headings Font Size
  - Don’t use min() for font-size- it’s risky for accessibility
  - Gradient Size
  - Vertical Padding
  - Dynamic Grid Gap
  - Dynamic margin
- We can manually add fallbacks
```
.hero {
    padding: 4rem 1rem;
    padding: clamp(2rem, 10vmax, 10rem) 1rem;
}
```
- Or by using the css `@supports` rule
```
.hero {
    /* Default, for non-supporting browsers */
    padding: 4rem 1rem;
}


@supports (width: clamp(10px, 5vw, 50px)) {
    /* An enhancement for supporting browsers */
    .hero {
        padding: clamp(2rem, 10vmax, 10rem) 1rem;
    }
}
```


### Move over TypeScript, here comes TypedCSS! - Rhiana Heath, Software Engineer Blake eLearning

- What are Types?
  - Strings
  - Array
  - Numbers
  - Hash
  - Date time
- Why even have Types?
  - Better errors: we can have more specific errors around the types
  - Code the documents itself: as we are writing the code we can write what types a function expects
  - Faster performance: the programming language has to do a little less work
- What Types does CSS have currently?
  - _"Strings, Strings Everywhere"_
```
.foo {
  width: 500px;
}

const widthOfFoo = $('.foo').css('width')
typeof widthOfFoo === 'string'
```
- What is Typed CSS, where does it live?
  - Typed Object Model (OM)
  - Paint API
  - Layout API
  - Properties and Values API
  - And More!
- What are CSS Typed OM?
  - Keyword
  - Unit
  - Position
  - Image
- [Typed OM](https://houdini.glitch.me/typed-om) is an extension to the existing CSS Object Model
- [Browser support](https://ishoudinireadyyet.com/)
- Houdini is just JS manipulations of CSS
  - Examples:
```
.foo {
  width: 500px;
}

const foo = $('.foo')
foo.css('width')
// "500px"

foo.attributeStyleMap.get('width')
// CSSUnitValue {
//   value: 500,
//   unit: 'px'
// }
```

```
.foo {
  width: 500px;
}

const foo = $('.foo')
foo.css('width')
// "500px"

foo.attributeStyleMap
.set('width', CSS.percent(50));

foo.attributeStyleMap.get('width');
// CSSUnitValue {
//   value: 50,
//   unit: 'percent'
// }
```

```
.foo {
  width: calc(100vw + (100% + 20px));
}

const foo = $('.foo').computedStyleMap();
cs.get('width');
// CSSMathSum {
//   operator: 'sum',
//   length: 3,
//   values: CSSNumericArray {
//     0: CSSUnitValue { value: 100, unit: 'vw' },
//     1: CSSUnitValue { value: 100, unit: 'percent' },
//     2: CSSUnitValue { value: 20, unit: 'px' },
//   },
// }
```

```
try {
  const css = CSSStyleValue
               .parse('width', 'CSS.px(not a value)');
  // use css
} catch (error) {
  console.error(`${error}: please supply a valid width value`)
}
```

[Examples](https://codepen.io/Rumyra/pen/99bc930f82fe908346254df5354066b4?editors=0110)
[Slides](https://slides.com/rhianaheath/move-over-typescript-here-comes-typedcss)


### How To Draw, With CSS - Michal Porag, Frontend Developer Outbrain




### A special Webbed Briefs - Heydon Pickering, Designer, Developer HeydonWorks
