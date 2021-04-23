## Code 2016 - Day One

### Once More with Feeling - Tim Kadlec, Front End Peformance advocate at Akamai and author

Twitter -@tkadlec

As an industry, we’re starting to recognise that what really matters for performance is how fast the experience feels...

- The human brain is a processor
- "Pereception is reality..." → perception frames reality and this affects how we perceive things
- Perception is surprisingly easy to trick
- The bouba / kiki effect - there is a non-arbitrary mapping between speech sounds and the visual shape of objects
- Living with lag (an experiment by Oculus Rift) - adding 300m/s of lag turns people from being functional human beings into being farily useless
- Amazon found every 100ms of latency cost them 1% in sales
- What happens looking up a website?
	- DNS lookup - Chrome has a tool that visualises DNS lookups in Chrome Canary
	- TCP Connection - Three way handshake
	- SSL Negotiation - HTTPS, two round trips required to negotiate
	- Request - Request HTML, may not all come back in one go
- There are nine request before a secure site starts serving actual assets
- "The fastest request is no request..." - said every performance advocate ever
- Everything should have a value - because everything has a cost
- How do we balance richness with speed?
- Performance used to be considered "the developers problem" - but that perception is very flawed
- Classic performance story:
	- There was a slow lift in an office building. The lifts had to service a lot of floors and it would take a long time. The engineers came in and determined there was nothing they could do to make the lift faster and keep the elevator safe. So the building manager called a meeting and someone asked "Why are people complaining? Why do they all hate the lift so much...?" They came to the conclusion that putting a bunch of strangers in a metal box with nothing to do was the problem. They put mirrors in the lift. This meant people could check their appearance, look at other people in the lift, etc. Complaints about the lift being slow dropped off and eventually stopped altogether.
	- The point of this story...?
	- The actual performance wasn't changed, perceived performance was improved!
- If someone is waiting for something there is an unavoidable period of time
	- start -----> waiting -----> end
- There are two kinds of waiting, active and passive
- Passive waiting: nothing to do or distract
- Active waiting: something to do, some sort of visual activity maybe?
- People who are waiting passively over-estimate the wait time by 36%
- There are specifications that let you preload resources so the user can have a reduced load time on subsequent actions:
	- link rel="dns-prefetch" – just gets a head start on DNS lookup
	- link rel="preconnect" - this means when you hit the domain, the request fires immediately without DNS/TCP/SSL delay
	- link rel="preload" - feed the browser a specific resource to request ahead of time
	- link rel="prerender" – preload and pre-rener the whole page as though the user has already loaded it - this probably makes sense for Google results but could easily be problematic for less linear experiences
- These are all hints that the browser can choose to ignore but used carefully could improve the overall user experience
- If they are used poorly they can hammer the users connection and use lots of CPU
- Looking at the way browsers render content it is easy to see that critical resources block further rendering
	- e.g. CSS and JS in the <head>
- JS can be loaded with async - the JS is parsed in paralel and the executed later
- There is also defer (not ready for production yet, but watch this space) which pushes the execution of the JS right to the end
- CSS tends to be a little harder to handle, it needs to be split up into CSS that handles the above-the-fold content, inline the critical CSS and then inject the rest of the CSS later on with JS and set a cookie that on subsequent views means the stylesheet can be linked to and should be cached
- Don't do this manually - put it inside a build tool?
- Theoretically that would mean we wouldn't have any blocking resources then
- How beneficial is the inline CSS hack really - it feels dirty?
- Wired did it as an experiment and the optimised page loaded in 3.9 seconds instead of 12.5 seconds (the user had viewable / readable content after 3.9 seconds)
- "Progress bars are the fold music of the internet..." - they basically draw attention to the fact that the user is waiting
- An alternative to spinners and progress bars is the use 'skeleton screens' - Facebook does this on the activity stream, the grey box hints at the layout that is loading
	- This gets the user to focus on what they are going to get instead of focusing on nothing
- Another approach could be to cache the application shell on a mobile so the wrapper loads immediately and the content comes in later
- Travelocity used a descriptive progress bar which talks about the tasks it's doing behind the scenes (finding flights, finding shortest routes, etc) - even though it's not literally doing them at that time
- It makes the users value the results more, and they engage better as the perceived value has changed
- This kind of feedback eases anxiety
- Faster is not always better....
- H&R Block found that users didn't trust a calculation that ran too fast, the manual equivalent was hard and slow so users expected even the computer would be a little slow
	- They put an artificial delay into the app and the suers were much happier - they felt the computer was doing "enough work" that it was right
- Operational Transparency - showing the work is being done, reassuring that that what is being done... is being done
- Include meaningful feedback, be careful about not over compromising on speed
- Apple product pages tend to come in at about 80MB each
- Performance isn't a race to the finish - its's more like choreography
- Performance is, and should be, about how the user feels


### CSS Grid Layout - Rachel Andrew, Founder and Front-end developer at Perch

Twitter -@rachelandrew

The CSS Grid Layout module bring us a native CSS Grid system for the first time...

- How do we visually describe layout?
- Modern CSS is awesome in many areas - but CSS for layouts got stuck in about 2006, it was never designed for the complicated layouts we are creating today
- Our great hopes to solve this are:
	- Flexbox https://www.w3.org/TR/css-flexbox-1/
	- CSS Grid https://www.w3.org/TR/css-grid-1/
	- Box Alignment https://www.w3.org/TR/css-align-3/
- This talk was focused on grid
- First you define a grid, then you define the tracks, rows and columns, then you set up the gaps between the tracks
- We can mix fractional and absolute units, so you for example have a 400px column followed by fractional grids to divide the remaining space
- There is a repeat shorthand: repeat(3, 1fr) /* three one-fraction elements */
- We can use auto-fill, auto-fit and minmax() to create extremely flexible grids that always fill the space available but adapt themselves when things no longer fit
- Where grid tracks are the spaces, grid lines are for drawing lines
- Grid cells are the smallest unit in a grid
- Grid areas are groups of cells
- Once the grid is set up you can then place content in the grid
- This can be done with grid-column and grid-row shorthand, or with grid-area which runs through grid-row-start, grid-column-start, grid-row-end, grid-column-end
- We can name the lines in the grid and then position against the names
- Grid is very table-like in some ways
	- Unlike tables though, the content doesn't need to follow source order
	- Can be moved at different breakpoints to play nice responsively
- Grid item placement algorithm 
	- Determines the rules of content placement
	- It tries to ensure no matter what we do, nothing will overlap
- With complex grid layouts naming lines becomes more important
- It is possible to position against the start of content and not the start of a specific display location
- The named areas means we can name things like "header", "content", "footer" and the ascii art style lets us do things like "sidebar content"
- The above means it is great for rapid prototyping
- Could this actually let us replicate the classic twelve and sixteen column layouts popularised by libraries like Bootstrap?
	- There is a big cost of using something like Bootstrap, pushes up the weight and makes the markup more complex
- CSS Grid would let us describe complex layouts in the CSS and redefine at different breakpoints meaning it's a much lighter way to do things
- Is Grid a competing specification to Flexox...?
	- Not really, whilst they share many similarities, these are contained in CSS modules
	- The css-alighn module is used in both
	- This leaves the other modules to solve the different use cases they are best suited to
- When should we use Grid over Flexbox?
	- Flexbox is for one dimensional layouts, Grid is for two dimensional layouts
	- Grid is much better at aligning content against the position of other content
	- Flexbox works from the content out
- Accessibility should still be carefully considered, Grid is not an excuse to forget about logical source order!
- Nested grids, a grid item can be a grid for child elements
- There is a subgrid value although it is at risk of being removed from the spec
- This is still an emerging spec so now is the time to experiment with it, try it out and give feedback
- Browser support - not good, it's currently behind feature flags and in early dev versions, but not actually in any mainstream browsers
- A collection of usage examples for the CSS Grid Layout spec can be found here


### Flexing your layout muscles - a pragmatic look at Flexbox - Stephanie Rewis, Lead Developer on Design Systems at Salesforce

Twitter - @stefsull

Flexbox, a combination of simplicity, complexity, joy and frustration...

- The problem with layout is that we have been using many methods and we have been using them for things they were never designed to be used for
- Floating relies on some order - and this is not always the order we want
- display:inline-block means we fight the whitespace
- display:table means we are left with single rows
- Now we have display: flex! 
- Can flexbox be used in production, what is the browser support like?
	- Yes if you are supporting IE 10+
	- There are polyfils available for IE 9 if needed
- Use a tool like autoprefixer to avoid manually prefixing things
- The "almost complete guide to flexbox without flexbox"
- The key pieces of flexbox:
	- flexbox containers
	- flexbox items
- Flexbox container properties:
	- flex/inline-flex
	- flex-direction (set the main axis to be a column or a row)
	- flex-wrap
	- flex-row
	- align-content
- Need to be aware of the flex axes - main axis and cross axis
	- Both have a start and end which is important for alignment
	- These are not horizontal and vertical, main axis is set by flex-direction and cross axis is the opposite/crossing axis
	- Using flex-start and flex-end is great for internationalisation
- Flexbox items:
	- flex-grow
	- flex-shrink
	- flex-basis
- Remember to be judicious and keep accessibility in mind
	- Don't mess with the order, Firefox in particular is problematic as it follows CSS order
- What can we actually do with flexbox?
	- Display flex: equal height boxes
		- The default layout is great for headers where the heading in the middle needs to fill between the logo on the left and the controls on the right. But it's not so great for body content.
		- To control the widths you can set a min width… then you can use justify-content:space-around or space-between to ensure there isn't an awkward lopsided gap at the end, it's evenly spaced out.
	- You can align things to the top or bottom
	- You can choose if things stretch to fill vertically
	- You can centre-align content - vertically centred
	- Classic OOCSS items like the media object are really easy and the DOM order ends up being cleaner and better for accessibility.
	- Horizontal lists are incredibly easy
		- pagination can be set up to always space correctly no matter how many items there are
		- you can use margin auto to bump the first and last item out and away from the rest, which will still evenly space
		- horizontal navigation can be set up with nice even items
	- You can make a box of content always centred – vertically and horizontally – no matter how much content they have, just with display:flex on the parent and margin:auto on the child
- Grids… a flexbox grid starts with:
	- .grid { display:flex } .item { flex: 1 1 auto; }
- Can add modifiers to reverse rows, create columns, etc
- We can also control whether items will wrap
- At Salesforce there were long discussions about how to handle responsive design, the team uses Cap Watkins' sliding scale to resolve disagreements
- Visual regression testing?


### Does Your Web App Speak Schadenfreude? - Greg Rewis, Lead Developer Evangelist at Salesforce

Twitter - @garazi

Even if you don't speak another language, chances are good that your web application will need to...

- Schadenfreude – taking pleasure from someone else's misfortune
- What does schadenfreude have to do with a web site?
	- Internationalisation and localisation obviously!
	- When we get this wrong we inflict (accidental) schadenfreude on people who use our sites and applications
- In order to be a truly global presence a site would need to speak 16 languages
- We should be thinking globally and coding locally
- It is our responsibility and developers and designers to understand how the design and code decisions can affect our ability to deliver our sites to a wiser audience
- Localisation is the actual process of adapting a product to meet the language and cultural requirements of a local market - this includes:
	- Dates
	- Numbers
	- Currency
	- Phone numbers
	- Symbols/icons
- All of the above, is not handled carefully, can have an adverse affect on users
- It is not just about translation strings
- Phone numbers are a great example - in the US people will write dashes in phone numbers without even noticing they have done it, but not all forms can handle this
- If a user screws up something in the form don't wipe the form field - it can be extremely frustrating
- Use placeholders or pattern examples if the form validations requires a certain format
- Most translations are done via XML documents
- Translation challenges are compounded when the text is techincal
- Words that are taken out of context are very hard to translate eg. device in context might mean the phone that you are using,  but the French translation called it “peripherique” - which means a peripheral device like a printer, not a primary device like the phone
- Even when translated correctly the words may be far bigger eg. "edit" is “bearbeiten” in German
- Text expansion creates laytou trouble if a design is only focused on the English version
- The general accepted idea was that we should allow about 20% extra space for translation however this is not correct
- Multiple words can become one word - we can wrap multiple words but not one word
- Translate the word "views" - in Korean it is much shorter, however in Italian it is 300 x longer!
- How do we start planning for this?
	- the W3C came up with a real expansion ratios for i10n - up to 10 words needed 200-300% explansion, over 70 words comes down to 130%
- Symbols can also be an issue - a button with a + icon grows in Korean due to the character set being different
- Thai languages have much taller ascenders than English
- Tabs pose their own special problem, fixed width tab navigation tends to truncate meaningful information
- Same with breadcrumb navigation
- We shouldn't be forcing capitlisation - not all langauges capitalise things in the same way, e.g. In Danish nothing but the first letter is capitilisied, ever!
- Use the right encoding, don't skip diacritics and other modified characters - UTF-8 tends to be the best
- Don't attempt to translate, maintain the language
- Labels should always have context
- The words 'start' and 'end' tend to translate better than 'from' and 'to'
- Some languages just don't abbreviate
- Never put text into an image - ever!!!
- Plugin for Sketch that can check languages in designs and help identify untranslated strings, unencoded symbols and other issues
- The culture we grow up in plays a huge part in the way we percieve things, and therefore how we build things
- Culture is like an iceberg - a small tip of the things we notice and think about and there is a whole lot of stuff going on under the water that we don't think about
- Things as fundamental as the way people read are totally different in different culture
	- In English, eye tracking will show an F-shaped heat map while in Japanese, Chinese and Korean will produce a lot more smaller hotsports in a broader distribution
- Contextual Design - Edward Hall
	- People in different culture communicate differently
	- Some are high context and some are low context
- Colours change significance - http://www.informationisbeautiful.net/visualizations/colours-in-cultures/
	- In China red is good, in most English speaking cultures it is perceived as bad
- How should we indicate the availability of different languages?
	- Flags are bad!
	- Flags indicate a country, and multiple countries speak the same language
	- Countries can speak multiple languages
	- There is a push for a standard language icon - http://www.languageicon.org/
- The unofficial localisation checklist - http://l10nchecklist.com/


### The Power and Responsibility of Unicode Adoption - Katie McLaughlin, Operations Engineer and Software Developer

Twitter - @glasnt

Why the extended character set provided by the Unicode standard needs to be treated with responsibility by users and platforms alike...

- "I love emoji... I love how broken they are!"
- If you use unicode most languages will be fine, but Japanese has multiple character sets, including emoji!
- Emoji came from a closed mobile network in Japan which had 16 x 16 pixel characters which were pictures
- They were not images, they were not emoiticons, they were something else we now call emoji
- The unicode consitorim initially refused to include emoji in the Japanese charater set, but people kept asking and the basic set of emoji went into unicode
- Then ioS5 included emoji and snuck it into English character sets and it exploded worldwide
- Now emoji are expanding to include non-Japanese cultural references like popcorn and burritos...!
- Emjoi don't look the same everywhere, they were rushed, mistakes were made
	- The yellow heart was translated in unicode with speckling, which is an old way to encode gold in black-and-white (used in old heraldry systems) - the first android emoji for “yellow heart” was the infamous translated from speckled into a hairy pink heart
	- Flushed face emoji look so different on different platforms that they might look flushed, embarrassed or even like they're doing an “aww shucks”
	  Some emoji for “clapping” showed hands with thumbs pointed out – palms not facing each other
	- The emoji for “blonde” isn't always blonde
	- Question mark is sometimes an exclamation mark
	- Grinning and Grimace – most people are confused by this, the eyes change to indicate extreme happiness vs extreme sadness (there's a whole paper on this from the University of Minnesota)
- So how do you get a new emoji or glyph included - the unicode consortium take applications on grounds including:
	- For backwards compatibility – eg. the Yahoo Messenger cowboy
	- To complete a set – one implementation didn't have the entire zodiac set
	- Cultural pressure – asking often enough gets you bacon and tacos
- Brands, memes, etc. will not get in, nor will things that are too specific, so "cocktail" would be a yes, but "cosmopolitan" would be a no
- The broader use of unicode characters presents some challenges
	- Emoji will break certain features of JavaScript
	- URLs don't always work (there is a text fallback?)
- http://xn--9q9h.ws/ (spoon emoji) is an acutal website
-  RFC3492 is proposing a way to encode emoji into a standard alphanumeric string, because URLs have to work somehow
- You can't use certain javascript string operations on emoji, so careful testing is required
- Emoji input can be hard, people have tried to standardise this, but Slack and HipChat do different glyphs for cake and neither is technically an emoji
- Autocomplete can cause problems as well, :$ should not become "money mouth" emoji
- If you do decide to use emoji then be careful:
	- Include fallback text and use title, alt and aria correctly
	- Use the formal name
	- Sitck to the standards
	- Remember to actually declare meta charset UTF-8 otherwise it will be ascii
- So what is the future of emoji - there are lots more coming!
- So what is the key takeaway of this talk:
	- We need to implement emoji reponsibly
	- Don't forget to have a little fun with it as well


### Progressing your Web Apps with Service Worker - Marcos Caceres, Platform Engineer on Mozilla's DOM team

Twitter - @marcosc

The key enabling technology of "PWAs" is the Service Worker...

- The way standards evolve can be strange - "HTML5 is basically reverse engineering IE6..."
- There are lots of APIs out there in the world which aren't really all that great
- The got the standards community thinking - we kinda suck at APIs
- Particularly the appcache debacle, people decided to start focusing on the primitives and stop trying to be clever
- The approach behind service workers is to work out primiatives - simple pieces that can be combined into more complex things
- The architecture of the services worker: it's really just a glorified event listener at its core
- Little services that run up, do something and then disappear quickly
- Service workers have short life cycles and publish events to reflect that life cycle e.g. activate when it starts up
- Most APIs are available in the window object e.g. window.caches
- The building blocks:
	- Fetch API
	- Cache API
	- Notifications
	- Push API
- There pieces are all intentionally simple and are not necessarily simple to use, to ensure they stay simple without being dumbed down
- These are the things we as developers should be trying out
	- If you need to send notifications to users, you should try using the notiications API, lets you send text but also has cool things like vibrataion patterns
- The dev tools in Chrome and Firefox are pretty good, they let you inspect these objects, send fake notifications etc
- The hard part goes to the authors to come up with good use cases, and to implement good architecture that actually solves a problem
- The specs aren't going to try and be clever, because they don't want to "appcache it" again...
- Encourage people to get into it and play with service workers
- Service workers are hard and maybe people get put off by that
- It is a lot of work to set up initially
- All developers should be making the effort to understand HTTP / HTTPS
- https://wicg.io/


### CSS: Code Smell Sanitation - Fiona Chan, Technical Recruiter and LookAhead Search and former Front-end developer

Twitter - @mobywhale

How to spot some of the early symptoms of code smell and how you can make your CSS more robust...

- Most of us have a love / hate relationship with CSS
- We love it because it's pretty easy to learn and it's very powerful
- But CSS can get messy very quickly
- To some people CSS is some kind of dark magic
- There are so many ways to do one things... Which one is the right way?
- Which one do you pull up on a code review?
- There are some things that can be done to minimise problems..?
- CSS linting - checks for basic syntax issues, but can enforce things like code style and naming conventions
	- We should be inspecting and modifying the default rules to suit our projects and out teams
	- Running just default rules probably isn't going to go over that well
	- The linter can be run ideally in a build before a merge
	- At author time in editors like Sublime Text and Atom (both have plugins)
	- Or both!
- Linting is goooooood, but we should not be relying soley on linting
- Generally speaking we should never rely entirely on tooling
- So, what else can we do?
- Simple measure can be surprisingly effective
- Very long selectors, very long rules
	- Is it all really necessary
	- If it loks big and complex then it probably is
	- If a selector seems excessively long, it probably doesn't need to be that long
- Avoid magic numbers
	- Numbers that "just work" but aren't explained
	- This creates very brittle CSS
	- Whever possible use non-magic number implementation
	- If you do have to use a magic number then write a explanatory comment about how it's derived
	- Flexbox can help avoid a lot of the old cases that required hard-coded numbers so if you're not using it already consider using it
- Stress test your UI
	- Don't just write and test the perfect scenario
	- Change the font size
	- Test across as many different screen sizes and devices as possible
- Old prefixes
	- Do you still have code that we no longer need
	- Have you changed your browser support and have reduntant autoprefixers
- Review the build in the browser
	- Don't just read the code - acutally go to the effort of checking it out and looking at it
	- Inspect things - kick the types
	- Use the inspector to turn off properties, is there anything unecessary floating around
- Consider maintainability
	- Are things names clearly
	- Is the code organised and well structured
- Don't just relying on linting, spend time doing proper code reviews
- Check out the code in real broswers
- A developer has spent time writing the code so spend time reviewing it properly


### The Zen of JavaScript - Dmitry Baranovskiy, Senior Computer Scientist at Adobe

Twitter - @DmitryBaranovsk

What JavaScript has been trying to tell us for all these years...

- Dmitry is not about to tell us that everything we know about JavaScript is wrong... although it is....
- As developers we are guilty of not asking JavaScript what it wants
- "Those who are unaware they are walking in darkness will never see the light..."
- The problem with JavaScript is everybody knows it, nobody knows it
- People don't pick up JavaScript so much as they run into it
- JavaScript has been bent to meet the expectations of the developers writing it - you can tell when it has been written by a Ruby dev or a Java dev
- What is the JavaScript way of writing JavaScript?
- Well there is no wrong way....
- Zen has the well known conundrum "what is the sound of one hand clapping"
- In JavaScript the question should probably be "what number is not a number"
- Developers are afraid of NaN!
- What if NaN was there for a reason?
- If we have a function that returns a number but returns bull if there's an error - why not return NaN instead of null?
- People are afraid of NaN because the first time you get NaN it's normally because you messed up - so from then on, if you see NaN you think you did something wrong
- We should be more accepting of NaN, it's there, it's exists and we can use it
- Is JavaScript good or bad at equality - depends on who you ask and how you look at it
- == is hated... why so much hate?
- Dmitry's current team has a rule that you cannot use == and you should use === instead
- There are unexpected and confusing results when you use ==
- But === is not fixing the problem, it's covering it up!
- What about <=, >=, > and <? 
- Not using these is like hiding by covering your face
- If you don't understand what you are doing with these then you will get into trouble
- People tend to look at JavaScript and come up with theories on how it works and then write code according to these theories
- Don't make up theories - read the spec, there is no mystery, it's all been documented
- JavaScript is very accepting - it accepts all your gate, all your blame, all your love
- .charAt() doesn't care what you pass it - be like .chatAt()
- It always returns something, why throw exceptions, why be so rude?
- It doesn't care what it is running on either, pass it a number and it returns a number, pass it NaN and it returns a character from NaN
- Emptiness is a very important concept in Zen, JavaScript has three emptinesses: NaN, null and undefined
- Undefined isn't even null - it's more empty than null!
- But JavaScript has something even more empty that that... JavaScript can have a placeholder that returns undefined
- But if there's no placeholder it's not even undefined...
- The 'new' keyword doesn't smell like JavaScript, it was put in because Java was fashionable at the time and when that was falling out of fashion people started leaving it out
- Functions can be used in five ways:
	- You can call a function
	- You can return  a function
	- You can create context and closures with functions
	- You can use a function as a constructor
	- You can call it with strings or numbers
- Developers write rubbish JavaScript - JavaScript forgives you
- All you bad code...
- All your libraries...
- You want to run JavaScript on servers and on phones...
- JavaScript forgives you
- You want to put commas first...
- You want to omit semicolons...
- JavaScript forgives you
- Dmitry doesn't but JavaScript does
- JavaScript is not a weak language - it's a flexible language
- It's an encouraging language
- You don't have to follow the rules of Python or Java to write it
- You can follow your own rules, it gives you that freedom
- "And those who were seen dancing were thought to be insane by those who could not hear the music..." - Nietsche
- Be the ones who hear the music!
