## Respond 2017 - Day Two

### The Great Accessibility Bake-off - Cordelia McGee-Tubb, Web Developer and Accessibility specialist at Dropbox

Twitter - @cordeliadillon

It’s always better to bake in accessibility from the very beginning of your project than tack it on after the fact...

- Accessibility is about making products, services and spaces that everyone can use and enjoy, in all contexts, regardless of their abilities
- We tend to think about things in four dimensions:
	- Visual
	- Motor
	- Auditory
	- Cognitive
- This should also include situational and temporary disabilities
	- Someone who is in a loud bar has the same problems hearing their phone as someone who has a hearing impediment
	- Trying to use a system in a language you don't know could be considered a cognitive problem
- We should be creating flexible systems that consider all user experiences from the very start
- It should be baked in, not added on...
- You can't add the blueberries to the blueberry muffin after you have baked them
- If you cram blueberries into a baked muffin, you end up with a mess...
- The internet is guilty of 'let's make this look like the designs and we'll worry about the functionality later'
- Example of this is buttony things, where people create a clickable div and then cram in lots of extra markup to make it work like a button
- Why not just use a button in the first place?
- Intro to the Great British Bake Off:
	- A TV show where amateur bakers compete in a range of challenges (signature, technical and showstopper) to be the best baker
	- They are really competing with themselves rather than each other
	- Quintessentially British TV show
- Cordelia wants us to to take part in the Great Accessibility Bake Off...
- We should consider users with different needs, mouse, touch screen, braille input, voice control. laptop, single button clicker...
- Main ingredients of an accessible UI:
	- semantic HTML
	- a dash of ARIA
	- alt attrs
	- names for all interactive items
	- sufficient text contrast
	- mouse/keyboard parity
- Semantic HTML is the foundation of accessibility
- If you are only sending your users divs, spans and a tags then you aren't really giving them anything meaningful
- As web apps evolve, plain HTML doesn't handle some of the more complex interactions we have going on now
- This should be where ARIA comes in...
- It should help us describe rich interactions
- ARIA lets a developer communicate with assistive technologies
	- role
	- state
	- properties
- The first rule of ARIA is don't use it if you don't have to
- Cordelia suggests thinking of it like cinnamon, it's good, but not if you eat a big spoonful of it - you can have too much of a good thing
- Alternative text
	- Images with contextual context should have the text you would want to see in a text-only version of the page
	- Decorative images should include and empty alt of aria-hidden="true"
- What are the criteria for our Great Accessibility Bake Off?
	- Does it look amazing?
	- Does it function as expected?
	- Has it been over or under engineered?
- Everything you make should be tested with:
	- a mouse
	- a keyboard
	- screenreaders (specific combination can make a massive difference here)
		- NVDA+firefox
		- JAWS+IE11
		- Voiceover+Safari
	- grayscale mode
	- real users
- Signature challenge: make an accessible form
	- On the TV show this is making something simple really well
	- Simple subscribe, text input, email input (required), checkbox, button
	- Things that are needed:
		- Visible focus indicators
		- A label that is associated with its input using the for attr
		- Placeholders are not label!
			- They are low contrast
			- They look like the field has been pre-filled
			- They disappear when a user starts typing
		- Associated error messages with aria-describedby linked to the input by ID
		- Put an icon on the error as well as changing the colour, so users in grayscale mode see something useful
- Technical challenge: accessible tree view / file system tree
	- On the show this would be the challenge where the contestants get a recipe with information missing so they need to fill in those blanks
	- Tree views don't really have markup for this, so semantic HTML on its own is not sufficient
	- ARIA has a tree view!
	- W3 provides a lot of recipes that can be super helpful in instances like this: https://www.w3.org/TR/wai-aria-practices/#TreeView
	- Can still hit bugs, don't assume that it will be smooth sailing - can be hard to debug as well
	- Good resources for debugging:
		- http://whoseline.a11yideas.com/bugs.html
		- http://web-a11y.herokuapp.com/
- Showstopper challenge: drag 'n' drop
	- On the TV show this is the grandest piece, normally a big extravagant creation
	- Drag and drop can be really challenging as there is a lot going on
	- A good way to think about it is as a way to move something and it doesn't seem as complicated
	- Drag and drop patterns usually fall into one of three patterns: 
		- Drag something into a bucket (file uploads, kanban boards)
		- Rearranging lists (ranking something)
		- Move an element on a canvas (less common on the web, but likely to happen more in future)
	- Useful article: http://sitepoint.com/accessible-drag-drop
	- Kanban board: focus the card, press space/enter to open a menu that lets you choose which column to move the card into
	- ARIA 1.1 has deprecated aria-grabbed and aria-dropeffect
	- They will 'probably' keep working
	- ARIA authors relying on the native drag and drop API?
	- Dropbox gives users an alternative interface, when they click move, they can then simply choose the new location of in a modal
- Give users choice and flexibility - they will pick the method that works best for them
- There is not caniuse for ARIA - not yet...
- We need to talk to our users and find out if they are happy - we shouldn't just be guessing
- Ask people who really use this whether it’s working for them
Designing OneABC, a typeface for Australia - Wayne Thompson, type designer and typography educator


### How do you design your country’s national font? Wayne was asked to do this by the ABC, Australia’s most trusted media brand...

Twitter- @WayneATF

- Has been working on type for decades - originally inspired by a Letraset book when he was a kid
- Studied other things but carved out his own niche as a typeface designer - not raelly a course you can do to get to this, you can learn typography but there is no formal way to learn typeface design
- Wayne was asked to create a new suite of typefaces for the ABC
- The brief was a sizeable 13 pages document
- Key elements of the brief:
	- How might the ABC make a coherent experience for all its properties?
	- How could this typographic system encapsulate Australia’s eclectic and multicultural identity; and express a contemporary and relevant ABC?
	- How can ABC Sans be a major brand carrier for the ABC?
- So, what is our National character?
	- Wayne asked people on Facebook and lots of typical Aussie words came back ('Straya, thongs, etc.) and 99.94 → Donald Bradmans batting average
- Some of it wasn't useful but common phrases started emerging, including “wide, brown land”
- Australia - open space / a connection to the land in some way
- "Over it all, an impossibly open sky, dwarfing everything" – Tim Winton
- The three characterists Wayne settled on:
	- Open pspace
	- Proudly inclusive
	- Larrikin element
- Started looking at other typefaces supposed to represent a nations character:
	- Sweden Sans (soderhavet.com) – it has a principle of lagom – balance, avoiding excess
	- Johnston, the typeface used for the London Underground – not intended, but it’s become strongly associated with things that are very English
	- Helvetica – known as being very Swiss - precision
- So where do you start with something like this? Just strart drawing!
- Had ideas of trying to involve Uluru, shaping the capital letters and a strong baseline that implied a 'connection to the land'
- In hindsight it was a terrible idea - but it was part of the process
- You have to meander your way to the final result, it’s never a straight path
- Things started to clarify:
	- inclusiveness: open rather than closed apertures
	- connection to country & open space: wide measure, generous proportions when compared with other fonts
	- the ABC’s logo is a lissajous figure, which gives a curve that could be used on some letter shapes
- Sketched a great deal on paper, leading up to clean alphabets on A3 tracing paper
- Kept all of this in a sketchbook so he could show the process later
- Presented this to the ABC and found himself being filmed for posterity
- Got the green light to go ahead and make the typeface
- There was a full day workshop with the entire design team, where most people on the team contributed something to the final shapes
- The final typeface was created, moving shapes from Illustrator to Fontlab
- Had to fill in the entire character set; and then create all 11 weights of the font using interpolation to set the basics, then a manual review
- The ABC also needed some specialty weights like the italic, bold condensed, rounded and rounded bold (for kids programming)
- Then three serif weights (ABC Serif) were produced for internal text use - the serif font shares a common DNA with the sans
- Spacing between letters is set, then kerning variations (it has 777 kerning pairs with adjustments) - lots of manual work involved at this stage
- Fonts go out into the wild on retina screens, apps, websites and even tvs
-  HD TV it looks good, on older TVs… it doesn’t look so good
- A couple of letters will need a shape revision to help with issues discovered as the font went out to every possible place it needs to be used
- Aslo the “li” combination has spacing that feels a little wrong
- There’s also a lot of issues the font itself can’t fix
	- The non-lining numbers interfere with the rhythm when used in a paragraph
	- Sometimes people change the spacing between characters via CSS, so the spacing of ligatures no longer makes sense
- The reponse from the public has been really positive
- It seems all Australians feel a level of ownership of the ABC; and there’s been some commentary about the ABC 'wasting money’
- Chris Kenny had a dig about using non-system fonts and wildy over-estimated how much money had been spent 
- Sen James Paterson pulled up in front of the senate estimates committee as well
- Wayne views it as a privilege to work on the national typeface
- he ABC design team were truly collaborative and the success of the end product was a team success


### Designing for Growth - Mike Sharp, Web Developer

Twitter - @msharp

Mike's Five Fs of design...

- All established patterns were new once
- Take the hamburger menu for example - People think it appeared in the last few years, actually turns out the earliest known use was 1981, by Norm Cox for the Xerox Star
- What is growth design?
	- Using metrics and data to inform the way we design
	- It does not replace our gut, but it’s a way to include qual and quant data in the process
- Should always start with the experimental hypothesis:
	- We believe that [this change] will result in [a specific, measurable outcome] because [we have a rationale that says]
- Qualitative
	- User testing, prototypes
	- Great for highlighting problems early in the process
- Quantatative
	- A/B test between the existing and the new shiny version
	- Good for validating if a change 'worked’
- The Five Fs of Design
	- Foundation
		- Set up your pattern library, baking a11y in, tone and voice, design system, analytics
		- Good time to set up analytics
	- Fast
		- Going with your gut, using established patterns, fast iteration
		- Just get things out there
		- You don’t have enough users at this point to do decent quantitative analysis
	- Feature
		- This is where most people probably work
		- Getting to know your users, doing personas, slower cadence, sometimes it takes longer because you’re trying to make things closer to 'perfect’ before release
	- Facts
		- Most analytics packages do the heavy lifting
		- Define your funnel
		- Pirate metrics (AARRR): acquisition, activation, retention, referral, revenue
		- Be careful not to blow the results – eg. changing the copy will invalidate tests
		- Be aware of the whole experience, not just the specific piece you are focused on
	- Future
		- Don’t be afraid to push boundaries, but don’t make the experience worse for the sake of experimentation
		- Validate new patterns with qual before moving on to quant
		- Sometimes it pays to stick with your gut
		- Established patterns all started somewhere. If something goes well, roll it into your design language
- Tips for growth design
	- Sit designers with your devs, collaborate with them
	- Spar with other designers
	- Be aware of the bigger picture
- You never know, you may discover your own hamburger!


### Think aloud user testing - Shefik Bey, User Experience Professional at Loop11

Twitter - @shefikbey

What is the potential influence and impact of the think aloud method of user testing on the natural usage behaviour of participants?

- Creating products that resonate requires:
	- Deep customer empathy (why)
	- Target acceptance (what)
- If you don’t get it right out of the gate, you’re done! – Aarron Walter, True North Podcast
- The Think Aloud method
	- The objective of the Think Aloud method is to get people to verbalise in a monologue as they use the product
	- What are they thinking, what is their process
	- It gives powerful insights into customer behaviour, motivations and preferences
	- Jakob Nielsen advocated doing 5 sessions – it would be enough to get usable data - 80% of issues uncovered
	- Influence on natural behaviour:
		- fixation – what are people looking at and focusing on
		- fewer tasks – it takes up some time to think aloud
		- takes longer to complete tasks
		- increased cognitive load – think aloud requires multitasking
- Case study: Amazon Prime
	- Set up three tests:
		- standard loop11 usability test, no think aloud (50 people)
		- standard loop11 usability test, with think aloud (50 people)
		- video recording study with a third party tool, with think aloud (10 people)
	- Each study had identical tasks:
		- find cost of prime video
		- find cost of a series
		- find out if prim will work on my tv
	- Findings – broadly, pretty low success rates
	- They found the site wasn’t catering to natural mental models of information discovery
	- The tests had an inverse relationship between NPS/advocacy and SUS/usability
	- Contributing factors maybe
		- cognition and natural usage (does Think Aloud change this? it seemed to)
		- participant sampling (ruled out)
		- incentive (people tend to put more effort in if they’re paid more)
		- participant ratings – this is the one they felt had contributed the most in this case. In test 3, the testers get rated (high ratings lead to getting selected for more tests). This leads to a bias in the tester audience.
		- branding – Amazon is a big brand, so most testers were already users. That can impact results.
- Whenever you find yourself on the side of the majority, it is time to pause and reflect – Mark Twain
- Think Aloud is a widely-used technique, but do we stop and challenge it?


### Adventures in Conversational Commerce - Elizabeth Allen, UX researcher at Shopify

Twitter - @elizallen_

One type of tool that Shopify has developed for entrepreneurs is messaging bots that behave like “virtual employees” – they autonomously handle customer service interactions, online marketing campaigns, and even make sales...

- It’s only recently that brands started to engage with their customers on social media
- Talking to brands is becoming known as Conversational Commerce
- Things have changed in a lot of ways, there was a time not very long ago that you generally had to physically go into a store to buy things
- Shopify use quite a few bots at the moment
- Elizabeth is talking about two of them today:
	- Kit:
		- Helps merchants market their products
		- Texts you suggestions and runs small campaigns
		- Entirely automated, no human intervention
	- Messenger Bot: 
		- Helps merchants communicate and sell
		- There’s a “message us” button on stores; which starts in an automated browsing system
		- Real people from the merchant can jump in if they are available
		- Sales can be done entirely in Messenger
	- In reality these are “baby bots” rather than proper bots with natural language processing (NLP)
- Tips if you want to make a bot:
	1. Know your users
	2. Understand the medium the bot lives in
	3. Simplify the interactions
	4. Be thoughtful about the bot’s personality
	5. Solve problems, don’t create new ones
- What does Shopify know about their users?
	- Merchants: are busy, lonely, often not tech-savvy, #1 stuggle is marketing.
	- Customers: shopping online, don’t know shopify, may be skeptical of bots (don’t think they are any smarter or faster than humans).
	- Understanding users and their context helps make good choices with bots.
- The medium
	- “The medium is the message” – a conversational medium like messenger should be conversational
	- Customers may open up more in a social medium; you can even learn from the emoji they use
	- People find Messenger feels very personal
	- People tend to say thanks more in Messenger than they do for automated emails
	- ...so it’s nice if your bot knows how to acknowledge that! “Thanks” “Happy to help”
- Simplicity
	- Simple purpose
	- Simple process
	- Kit helps with marketing, which isn’t actually simple; but it sticks with things that are relatively impersonal like running an ad campaign
	- Balance being proactive with giving the user control
	- Give people options, but not so many options they get into decision paralysis
	- Messenger – they focused on making sure it worked well out of the box for busy merchants
	- Use data to guide the decisions; keep things simple and set smart defaults
- Personality
	- Bots have no personality or culture unless you create it for them
	- Users will tend to project their ideas onto the bot regardless, eg. despite the gender-neutral name, most women think Kit’s male and most men think Kit’s female
	- Keep it consistent – eg. don’t randomly change the tone from serious to informal
	- Because Kit is an assistant, it should behave like one
	- The principle became “collective success”, Kit’s a member of the merchant’s team
	- Kit says things about “we” and “our” about sales and products
	- Solo merchants really like the impression that there’s “someone there working with them”, and yes sometimes it gets a little weird
	- They also have had people send messages that really sound like they think Kit is a real person, although that is rare (most people are clear it’s a bot)
	- Watch out for lack of understanding from the user; negative reactions to the bot; context mismatch between the bot-world and the real-world
- Solve problems, don't create new ones
	- Bots are tools, they should solve problems
	- Problems that can occur:
		- Not respecting the user’s time
		- Not respecting the user’s context
	- Don’t make the bot feel like the aggressive salesperson!
	- Sometimes the messenger bot replies too fast – it makes people feel pressured to keep going
	- Merchants often feel it would be too creepy to jump into a session and take over from the bot, because it reveals they’ve been watching the user


### The (ancient) art of conversation: Styling beyond the GUI - Laura Summers, Front-end Developer

Twitter - @summerscope

What happens when your ability to persuade is your UI?

- Let’s think about how bots and conversational interfaces could look like in the future
- First though, let’s go back in time to ancient Greece and the beginning of democracy
	- There was an argument going between Plato and the Sophists, who were teaching rich people to speak in public
	- They were the dark pattern designers of the day; and Plato worried they’d fool people into making decisions against their own interests
	- Aristotle rejected Plato’s view and wrote a book about persuasion (The Art of Rhetoric)
	- Part of the idea was persuasion at scale: how to convince a large number of people to do something
- This is basically the same thing people are trying to achieve with chat bots and other conversational interfaces like recommendation engines
- Conversational UI has had a lot of bubbles and fizzles
-  People don’t have a good reason to trust bots or expect a good result
- Some of these failures can be solved by finding new heuristics
- We can look to those early philosophers for inspiration
- Aristotle’s Rhetoric has three rhetorical appeals:
	- Logos – the use of logical argument (convincing people with facts)
	- Pathos – the use of emotion (convincing people by evoking an emotional response, which can be both positive and negative emotions)
	- Ethos – the degree to which the audience perceives the speaker as credible. Intrinsic ethos comes from the domain; while extrinsic are signifiers like “I have been working in the field for 20 years”.
- The five cannons of rhetoric (Cicero in ancient Rome)
	- invention – finding an interesting way to get into the domain (comedians do this a lot)
	- arrangement – the order of the speech. In form design, clustering related fields contextually is an example.
	- style – the design of the language you can call on (Bus Uncle tells you about public transport but trolls you at the same time)
	- memory – recall, the ability to recall the speech; having a bot remember previous conversations
	- delivery – the tone, the speed and inflection of the speech
- A challenge and an opportunity – conversational UI can be deep or shallow, it can adapt to context
- A good book to read is Words Like Loaded Pistols
- We should one day expect our interface to communicate with speech and reason, not just colour and shape


### Removing everything and having a crap UI - Warwick Cox, Co-founder and CEO of Crowd Delivery

Twitter - @WazCox

When Crowd Delivery, an on demand delivery company, was first launched, it tried to make its interface like every other online shop. But then to test an idea, it basically removed everything.

- No write up - it was more a story, but one that needs to be listed to rather than conveyed via bullet points


### Styling Hilary: A design system for all Americans - Mina Markham, Senior UI Engineer at Slack

Twitter - @MinaMarkham

Mina talks about the successes and failures from nearly two years at Hillary for America, including creating CSS architecture and implementing a redesign of the main website.

- Pantsuit - The Hilary Clinton UI pattern library
- Mina describes the whole process as "kinda like an 18 month nationally televised hackathon"
- It started with a vague and mysterious email which Mina ignored, but they followed up and she got the job
- The tech team ended up being pretty big, by election day there were about 80 people
- Brief: We need a Bootstrap - and it needs a good name!
- Naming things is hard! They built…
	- pattern library – the library of UI patterns
	- framework – the frontend code that codified the patterns
	- style guide – how to put the patterns together
	- design system is all of the above and more
- Pantsuit? Mina thought no no it’s funny but she couldn’t possibly really name it Pantsuit… but people loved the name
- When time is short, why spend the time to build a system?
- hillaryclinton.com was an umbrella for multiple projects handled by different teams with different code bases
- They needed to share a single UI so people didn’t know that when they were using it
- There were many stakeholders, but the “Pantsuit team” was just Mina
- It was immediately obvious that done is better than perfect - just have to accept that sometimes you need to get things out the door quickly
- Pantsuit 1.0 was built in about 6 weeks
- There was no real need for maintainability, stability was much more important in the early days
- At the end of the campaign the code was going to go away - Mina learned to let it go and be okay with it
- Before starting Pantsuit she started with analysis of the existing CSS (the number of selectors, colours, etc), did a UI audit (the various buttons, etc)
- Used this info to help brief all stakeholders
- Started to cut up printouts as part of this process, in part because the analogue artefacts seemed to help the more visual thinkers on the team
- This was organised into groups of elements that were then turned into abstracted UI kit designs, with generic versions that could be used widely
- There was a lot of dogfooding and “pixel engineering” sessions designing in-browser
- The changes would sometimes originate in the UI Kit, sometimes in the Framework, sometimes right in the site
- The last part of the process was testing and iterating
	- Created a page called The Closet which had one of every single element, just to see how they looked outside of context and to see if things made sense
	- Used WAVE to test accessibility; plus manual testing of things like keyboard accessibility
- She didn’t really do it alone
- There was a “Pantsuit Council” that brought people together, with Mina overseeing it to provide consistency
- It was really important for people to be able to consume Pantsuit easily - so documentation became the next big thing to solve
	- Details on how to consume the assets (download, NPM, CDN)
	- How to contribute to the code
	- starter kits to design and build things with it etc.
- Automated as much as possible e.g. Slackbot to tell people when a new version of Pantsuit was released
- Everything was versioned
- What was the outcome?
	- When you work on a project for a very famous person, a lot people start talking about you
	- What was really important to Mina was the feedback from her team mates
	- They felt Pantsuit helped them build things as fast and efficiently as possible
	- It was particularly nice to get positive feedback from Hillary herself!
	- Unfortunately Mina also got a lot of extremely nasty attention from horrible people on the internet
	- Mina tried to go with “haters gonna hate” but some of these people were planning direct attacks
	- There were attack ads that tried to emulate the style of Pantsuit
	- This is one of the reasons Pantsuit was not open sourced
	- Even without the source and full details being easily available, people were able to reproduce the style with a high level of fidelity
	- You can't ever truly hide the code?
- The main take away Mina truly wants to give though is that in truth she felt loved, trusted and respected while working on the campaign
- Working on a campaign is tiring and hard
- She met former presidents
- She saw the web URL on the side of the campaign plane
- She showed hillaryclinton.com to Hillary herself
- Even after it was over, with the result people hadn’t hoped for… they found the local children had chalked messages of thanks outside their office
- The last time Mina saw Hillary, Hillary spent all her time consoling the staff who had run the campaign and giving messages of hope
- Was it worth it? HILL YES!
- Super detailed article by Mina here https://medium.com/git-out-the-vote/pantsuit-the-hillary-clinton-ui-pattern-library-238e9bf06b54
