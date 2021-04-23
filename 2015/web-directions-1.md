## Web Directions 2015 - Day One

### Design everything - Cap Watkins, VP of design at BuzzFeed, used to be a manager at Etsy

Twitter - @cap

How do you create a culture that values design...?

- It's hard. You will experience failure, and the wins won't be as big as you really want them to be.
- The only way to start making this better is to  define your ideal state of the world. Really think about it, and write it down. Organise around this.
- Don't be afraid to pretend you're already doing what you want to do. If you hire someone, tell them you're already doing it, and they will because to them "that's how you do it". That's the momentum you need to really change. 
- Don't silo design, product and engineering. Try and overlap them where possible.
- COLLABORATE - This can blur the lines, but it can be a good thing.
- Designers should code.
- Asking people to adjust their process can make them nervous, and because the future is unknown this is hard. Acknowledge this and empathise with them.
- This is all much easier when people like each other, do things to build trust and help others.
- Don't be afraid to let things go, especially the small things. Then when you do fight for something, people will believe you're serious and passionate about it.
- Use a scale - 0 [ <------ numbers of f**cks given -----> ].
- Be patient. Have a big picture vision, but work your way towards it slowly. Especially for organisational changes.


### Algorithms for animation - Courtney Hemphill, Partner and Technical Lead at CarbonFive

Twitter - @chemphill

Animations don't just make things look cool, they provide context and additional details. Algorithms give us a third dimension with which to communicate.... Time. 

- Math is a common language between developers and designers.
- As human beings we can make rapid decisions in response to motion, quicker than just colour. 
- AFFORDANCE and PERCEIVED AFFORDANCE.
- Animations are cognitive aids and allows users to discover an interface rather than having to be taught.
- Can help a user to build a map of the site in their heads.
- Use natural movements > friction, bounce, elasticity etc. We can understand physics.
- Interpolation - breaking it down [0-1].
- TDD is still applicable with animations.

Resources:

web-animations-js - can use JS to do CSS animation
Web Animation API Documentation
Animate CSS
MDN requestAnimationFrame documentation


### CSS in the age of components - Mark Dalgleish, Principle Software Dev at seek.com.au & Glen Maddern, Front-End Consultant / Freelancer

Twitter - @markdalgleish / @glenmaddern

A look at how modularisation, and local, rather than global CSS could be an option to developers in the not-too-distant future...

- https://github.com/css-modules - the end of global CSS?
- Documents v  web apps.
- Global scope is at odds with maintainability.
	- CSS zen garden - global scope is okay here, in bigger apps it is more difficult.
- How can we address the issue of global CSS?
	- Object-oriented CSS
	- Scalable and modular architecture for CSS
	- Block, element, module principle
	- SUIT CSS
	- Inline styles such as React
- Is the age of components? Web components, polymer, react derivatives, angular derivatives.
- Traditionally we would have used Gulp/Grunt but now we can use Webpack.
	- This allows you to stop thinking about your asset types in isolation with a single dependency tree.
	- One tool can know about ALL your file types instead of a single asset type, but you still have to specify each type separately (how is this different to the old way???)
	- BEM (hmm, that's a react element)?
	- Let's add them together:
		- JS+CSS together form a component => [JS+CSS][JS+CSS][JS+CSS][JS+CSS] === a page
	- Webpacks means no more global CSS as it is locally scoped to the component.
- Are we making better interfaces for ourselves, or bending to the whim of the machines we use?
- What if local CSS was the norm?
- http://glenmaddern.com/articles/css-modules


### Automation for developer happiness - Kitt Hodsden, Developer at shopify, used to be an engineer at twitter

Twitter - @kitt

What does fast even mean...? Speed is everyones problem.

- Determine key metrics.
	- Be warned about quoted statistics.
	- Be gentle with yourself, don't get too upset if it's not ridiculously fast.
- Establish a baseline.
	- Know how fast your own website is, it's not hard!!!! Open chrome dev tools and look at the timeline waterfall.
	- CSS stats is useful for sites css stats, eg. how many font sizes and background colours you are using.
	- Enter Grunt. To get started: https://github.com/kitt/grunt-perf-template.
- Make a change.
	- Remove HTML comments.
	- Concatenate and minify CSS files if possible.
	- Optimize images.
	- etc.
- Measure the effects.
	- http://www.webpagetest.org/
	- https://run.sitespeed.io/
	- Enter Docker
		- Install Docker.
		- Start docker.
		- Pull the docker instances.
		- Start graphite.
		- Start grafana.
		- Log into grafana.
		- Seed a single metric run.
		- Setup the graphs.
		- Stick it in a cron job.
- Set a "performance budget" - Tim Kadlec http://timkadlec.com/2013/01/setting-a-performance-budget/


### Cognitive bias in software development - Julia Claview, Freelance Developer and Data Management Consultant

Twitter - @juliaclavien

"Systematic errors in judgement and decision making are common to all human beings" - Learn to identify cognitive biases and become equipped with strategies to beat them.

-  The Planning Fallacy - "The tendency of individuals to display an optimism bias and underestimate the time and resources required to complete a project."
	- Otherwise known as the optimism bias.
	- Good case study would be the building of the opera house > estimated cost was $7mil, and it ended up costing $102mil, that's 15x the original estimate.
	- Post-mortems and retros are good but next time try a a pre-mortem - Get the right people in the room and imagine you are in the future and reflect on what went wrong.
	- Motivate people to plan well.
- Group Think - "The psychological phenomenon that occurs within a group of people, in which the desire for harmony or conformity in the group results in an irrational or dysfunctional decision-making outcome."
	- Everyone just nods along.
	- Can result in lower quality decisions being made.
	- This can be countered by asking people for their opinions in advance or blind voting (even when you think it is not necessary, it can return some interesting results).
- Confirmation Bias - "Also referred to as myside bias, is the tendency to search for, interpret, favor, and recall information in a way that confirms one's beliefs or hypotheses, while giving disproportionately less consideration to alternative possibilities."
	- Eg. "Where's the nearest apple store?" - "George Street!". "No, I meant apples the fruit!"
	- Flip the framing of questions to shift the thinking, eg. Instead of asking "Is X true?", ask "Is the opposite of X false?"
	- Assign someone the role of devils advocate.
	- Intentionally seek out disconfirming evidence.
- Hyberbolic Discounting - "The tendency to prefer smaller payoffs now, over larger payoffs later. This can lead to discounting the future value when it requires sacrifices in the present."
	- "I'm definitely going to come back and document this later..." and then never do.
	- Technical debts can accumulate heavy interest.
	- Quality and future proofing are hard to manage.
	- Good to be open about this, it's okay to pause and talk about things.
- Sunk Cost Fallacy - "The tendency of individuals to base decisions on honouring previously expended costs, rather than on the future consequences."
	- How often have you been working on a project, and you know it's a dead end, but you keep trying so hard? 
	- You have invested so much time into it you're not willing to let it go easily.
	- We don't like feeling stupid, admitting that is was a bad approach.
	- Can counter this by seeking clarification on outcomes and options. Requires open channels of communication.

Extra Reading:
http://boingboing.net/2014/07/07/cognitive-bias-in-software-dev.html
http://www.worldbank.org/content/dam/Worldbank/Publications/WDR/WDR%202015/Chapter-10.pdf
http://www.academia.edu/6447648/THE_IMPACT_OF_COGNITIVE_BIASES_ON_DELAYS_IN_PRODUCT_DEVELOPMENT_TEAMS
http://www.jonathanklein.net/2013/06/cognitive-biases-in-software-engineering.html


### Checklist driven development - Jeremy Nagel, Developer at Learnosity

Twitter - @jeznag

"Bugs are not fun...". High profile programming disasters can cost millions of dollars, how do we prevent these errors from happening? With a checklist maybe?

- The Checklist Manifesto: How to Get Things Right - Atul Gawande.
- Safety Culture - examples of checklist driven development.
- WE, AS DEVELOPERS, ARE RESPONSIBLE!
- Humans are fallible, working long hours we have confirmation bias, how do we fix this? Enter checklist driven development!
- Expect pushback on this "It somehow feels beneath us to use a checklist, an embarrassment. It runs counter to deeply held beliefs about how the truly great among us - those we aspire to be - handle situations of high stakes and complexity." Also don't expect full adoption overnight.
- Beware of checklist fatigue, people will get annoyed if they are too long, keep it concise and automate steps if possible. 
- Raise the bar - use checklists to encourage people to work better than they otherwise were and enshrine best practices. 
- Can encourage collaboration for the grater benefit of everyone, has the code had a secondary review from someone familiar with the service or technology if needed?
- Helps reduce errors and avoid things going into production that shouldn't.
- Works well in Agile workflow.


### Getting customers hooked with Web Notifications - Warwick Cox, Developer at Expedia

Twitter - @wazcox

Over 250 million push notifications are sent every day, when we build a website or an app our goal is to hook our customers in and keep them coming back, is this the best way...?

- Demo - https://warwickcox.com/
- Push notifications bring people back to the product.
- How do push notifications work? With service workers.
- Like a native app it can be closed but still listening for events.
- Things you need to use push notifications:
	- Secure server (HTTPS).
	- Google cloud messaging?
	- Register the service worker and service worker file.
	- An event listener, listening for the push notification.
- Best practices with push notifications:
	- Don't spam for the sake of it.
	- Let your customers decide what type of notifications they want to receive.


### The website obesity crisis - Maciej Ceglowski, Developer and Founder of pinboard

Twitter - @baconmeteor

For the first time in the history of the internet the computers people are using to get online are getting slower, smaller and harder to interact with. Whilst our mobiles are getting slimmer our websites are getting larger. What is driving this bloat?

- This isn't about shaming anyone. 
- The average web page size is up 15% in 2014 and is now just shy of 2MB.
- Is there any way to communicate to the user how "heavy" a page is? The sides of the browser could bow out or the scroll bar could be really hard to lift?
- Tim Kadlec - lots of reading on performance. 
- So what are we trying to do about the problem?
	- Facebook's instant articles -  Announced on a 6.1MB site which only links to a 41MB video.
	- Google's AMP - Announced on a page which is theoretically infinite. The carousel gets loaded over and over and over again and it re-downloads a 3.4MB video over and over.
- So what is the actual solution?
	- Send the critical stuff to the user first.
	- Stop. Seriously, they already have the critical stuff you said they need!
- What are fat ads? 2.1MB down to 1.1MB by enabling Ad Blocker on site about how Ad Blocking is hurting publishers.
- What are fat assets? Hero images, etc. We don't tend to notice because we have fast internet connections at work. 
- What's the future of the web?
	- Minecraft style:
		- It's blocky, and will never look beautiful.
		- You can build anything you want with it.
		- It's super open.
	- The FPS style
		- Looks amazing.
		- Can't really do much with it.
		- And you can't change it, you can only opt out.
- "I want us to commit to the idea that as computers and the network gets faster, the internet gets faster. And let's break the back of the surveillance culture. We have the power to change it by doing our own thing; by being independent. We just have to stand together."
