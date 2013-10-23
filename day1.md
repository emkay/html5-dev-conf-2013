# Day 1 - October 22nd

## Keynote

### From Grassroots to Green Pastures: Freedom of Choice and the Era of Integrated Computing
Speaker: [Christos Giorgiopoulos](http://html5devconf.com/speakers/christos_georgiopoulos.html), Intel

What is a hardware company doing at html5 conf?

* Intel does a lot of software too
* Commitment to an open cross platform community

#### Three Eras of Computing

* Task-Based
* Lifestyle
* Integrated

##### Task Based

Mainframes doing tasks. Punchcards. Very scarce resource.

##### Lifestyle

PC Era moved us into lifestyle computing. Moores law. Put notebooks, tablets, etc. into the hands of people.

Device centric.

##### Integrated

Computing becomes seamlessly integrated with our lifestyle. Less about the device, more about what the user is trying to accomplish.

This type of computing has to solve problems that we haven't tried to solve.

#### 50 Billion Devices / Freedom of Choice

Rich diversity between devices, OS's.

System Oriented Arch. (SOC). Modular hardware components packaged into devices. 

Multiple OS's on these devices. Developer has a big challenge to deliver a seamless user experience because of this diversity.

We need open cross platform technologies in order to run our programs seamlessly.

#### Gartner Hype Cycle

1. Tech Trigger
2. Peak of Inflated Expectations
3. Trough of Disillusionment
4. Slope of Enlightenment
5. Plateau of Productivity

#### HTML5

Developing into a widely used standard language. Saves time, don't have to write/re-compile for different devices.
Less time developing, more time marketing.

Will not and cannot replace everything. There is still a place for native programming.
But HTML5 has to become the foundation for application creation.

A complete solution requires an open cloud + cross platform tools.

#### Misc.

Intel is a huge contributor to Linux, Chrome, and Android.

Intel XDK New? Test emulate and build for multiple OS/Platforms.

Adobe Brackets Editor?

#### Smart Notify

Sounds like scripted dialog. They used XDK, then moved away because they started using phonegap.

#### Live.ly

Did not use XDK. Needed to deal with DRM video/audio and needed to stream directly to native client.

#### Lost Decade Games 

Using tools like [node-webkit](https://github.com/rogerwang/node-webkit) to wrap html5 games into native apps. helps with monitization.

Mobile game with [cocoon.js](http://www.ludei.com/tech/cocoonjs). 

#### [HTML Hub](http://html5hub.com/)

HTML5 community for developers.

## First Session

### Scaling Mobile Development @twitter
Speaker: [@jeremysf](https://twitter.com/jeremysf)

#### Features

Different buckets of features.

* Business partners -> Comcast -> change DVR stuff inside a tweet
* Fema Twitter Alerts
* Platform specific - photo filters. 
* Core Twitter - Conversations - messing with the timeline. 
* Platform - Twitter Cards

#### History of Engineering around Mobile
Early on twitter wasn't super stable. Implemented as a monolithic rails app. Did not scale.

Decomposed the monolith to SOA. Broke it down to a number of different services. Moved to JVM using Scala.

Huge shift to how twitter thought about engineering.

Past year alone twitter has doubled in users. Lot's more mobile users.

Mobile started out with a couple folks in the corner. Mobile was hitting the same public API that the rest of the services were using.

Started out as a mobile first service (SMS) and evolved to a web orientated company and api based service.

Brought in a bunch of employees that were super excited about mobile.

Didn't have a ton of mobile engineers. Started taking a mobile engineer and embedding them in different teams.
Engineer didn't have time to get domain knowledge on the team, there wasn't a sense of ownership of the code for the mobile dev.

How do you get feedback on how the mobile enginner is doing since they are switching teams so much?

Next step was to build full stack teams with mobile integrated on the team.

#### Culture Shift
Some of the biggest stumbling blocks.

The number one problem, iPhone. Everyone in the company is carrying an iPhone. 
But Android is a huge platform that you can't ignore.

Mobile is Android AND iPhone. Started talking about Android features first. Use the phones that your customers use.

Getting people to understand that mobile is not like the web. App is out there forever. 
Yes there is autoupdate on Android and now on iOS 7, but version is out there for life. Hopefully people will update.

Have ideas and then measure them.

#### Tech Challenges
Apple app store process has changed the way they operate. 15 day review process. 
QA it like crazy so they make sure they get it right. Make sure there are no bugs.
Make sure there are lots of features to QA/Release.


## Second Session

### Unmasking the GPU: Using Hardware Acceleration Correctly with CSS
Speaker: [Divya Manian](http://html5devconf.com/speakers/divya_manian.html), Adobe

#### Web Platform Team

http://html.adobe.com/webplatform
http://makethewebawesome.com

Features they work on:
* Regions
* Shapes
* __Blend Modes__
* __Filters__

#### Paint the Pixels

Browsers just paint the pixels on the screen.

How do the pixels render? Creates DOM, matches styles to the DOM nodes, etc.

##### Layout/Reflow
Calculation of information required to display visible DOM nodes.

##### When does it happen?
* Style changes
* Fetching of layout values/scroll values.
* Adding/removing elements from the DOM

#### How to minimize Layout?
* Move content away from the flow.
* Use only on the element with least children.
* Apply layout changes on `requestAnimationFrame`

See talk: [Rendering without the lumpy bits](http://vimeo.com/64733304) by Jake Archibald.

Do not read/write for every `requestAnimationFrame` as it makes things janky.

#### Paints
Browser changes the pixel values of an area of the viewport

##### Two Kinds of painting
* Paint an element
* Combine overlapping elements to present a flat image in the viewport

##### When does it happen?
* Scrolling
* Hover
* Basically all the time

#### Render Layers

Stacking contexts create RenderLayer Objects

##### Traditional Stacking Contexts
* Root Object(html)
* position: relative, position: absolute
* opacity < 1
* overflow is set

CPU paints to ONE Bitmap on the screen, which is the viewport. 

##### GPU
Like the CPU but optimized for processing large blocks of data in parallel.

* No Repains, relayouts
* If area is large, tiled textures to swap in and out textures quickly
* Larger power consumption (vs. not using the features)

GPU reduces burden on CPU, but
* Limited by memory
* Limited by CPU/GPU bandwidth for communication

###### Flicker Happens
* GPU scrambles to swap new textures into tiles as you scroll
* Browser is switching from CPU rendering to a GPU rendering

##### What happens to painting when the GPU is involved?

###### New Stacking Contexts
* Transforms
* Blend Modes
* Filters

Now there are:
* Many bitmaps not just ONE.
* Most bitmaps rendered directly by GPU.
* Broswer determines which render layers go into which bitmap

###### How does the browser decide which bitmaps are painted by the GPU?

* Intense painting occurs: video WebGL or canvas
* 3D Transformed elements
* Animated filters, masks, blend modes, reflections, opacity
* position: fixed
* content overlapping existing GPU-rendered bitmaps

#### Memory
* All data & GPU textures are stored.
* Android & iOS can force quit browser or webview to free memory (unlike Desktop).
* More apps open, smaller the size of memory availble to your page.

#### Reduce Memory Usage
* Smaller images (dimensions of image * 4 bytes)
* Smaller js/css files
* Smaller/fewer textures to GPU
* Fewer GPU layers

#### Reduce CPU/GPU Communication
Animate only
* Opacity
* Transform
* Filters
* Blend Modes

##### Others
* Don't animate z-index
* try not to animate non-hardware-accelerated properties on GPU-accelerated content.
* Use Opacity to toggle visibility of GPU-accelerated content

##### Why Opacity?
* Textures remain in the GPU
* visibility: hidden removes textures from GPU
* display: none causes repaints
* removing elements from DOM causes style recalculations, layout, repaint, firing of events.

#### In Summary
* Rendering is a beast.
* Do layout, repaint, GPU acceleration apringly.
* Memory can quickly get out of hand!
* Reduce CPU/GPU communication
* Use Browser dev tools to test

### JavaScript Insights: Tools for Improving JS Code Quality
Speaker: [Ariya Hidayat](http://twitter.com/ariyahidayat) & [Ann Robson](http://twitter.com/arobson), Sencha/Yammer

The co-speaker thing is weird.

#### Why JavaScript code Quality Tools?

It's how we work together. And it's how we level up. Robert Downey Jr. -> Iron Man.

#### JavaScript Tools
* varied
* some to be developed
* all are open source

##### Power(ful) Tools

* Linter
* Code Coverage
* Cyclomatic Complexity

###### Linter
* Enforces style guide
* Team standards: .jshintrc

Yammer team doesn't really agree on code style, so they don't have a .jshintrc.

###### Code Coverage

Istanbul

###### Code Complexity

* [jscomplexity](http://jscomplexity.org)
* [plato](http://github.com/es-analysis/plato)


### Creating Cross-Platform Games with One HTML5 Code Base
Speaker: [Tyler Smith](http://twitter.com/html5tyler)- html5 tech evangelist for Intel

#### Overview
* Decide if you should use a game engine
* What to look for before you decide to develop for a platform
* Optimize mobile performance
* Browsers versus hybrid app deployment
* Accelerating your html5 game to look native
* Packaing and deploy your game

#### Should I use a Game Engine

##### How to decide
* How complex will your game be? (collision detection, level creator, sprite animator, multi-player)
* Have you made an html5 game before?
* What's your time frame?

If you haven't made a game before maybe dabble with a game engine to learn other peoples mistakes and see how things work.

Builing your own:
* more time intensive
* Optimized for your game
* Lean functionality

Use a game engine:
* Less time to get started
* Bigger code base
* a lot of funtionality

#### Game Engines
* Is it designed to be responsive?
* Maintained/Forums/Support
* Debugging tools
* Cost
* Does it run well on mobile?
* Does the game engine allow pre-rendering

#### Research Supported Platforms
* Controls
    * Placement on screen
    * How will they appear/work while on desktop?
    * Will you need multi-touch
* HTML5 Support
    * Canvas tag
    * Audio tag
    * HTML5 performance
* Screen width/height

html5hub article on landscape screen width

#### Mobile Performance
* Huge performance bump on mobile webview
* Manage draw calls
* Size optimazation
    * Pull sound out of the binary
    * Dynamically cache depending on device
    * Use jpegs isntead of pngs when able (1/10 of kb)

#### Hybrid App vs Browser (Mobile)

Hybrid Deployment:
* Sell in the app stores
* Native in app purchasing
* Native JS API for social integration
* Full screen
* locking orientation
* Access to harware acceleration
* Native sounds
* Less fragmented environment
* Acess to local machine resources
* Desktop Icon

Browser Deployment:
* HTML5 Ad networks
* New tab and sign in
* No more full screen in iOS7
* No locking orientation
* Nitro in Safari (iOS)
* V8 engine (Android)
* Audio tag
* Multiple Browsers
* Restricted to browser
* Bookmark

#### Hardware Acceleration
* Graphics acceleration speeds up html5 2-10 times
* Multi-touch support for Android
* Still write once and deploy everywhere
* WebGL support


#### Deploy
* PhoneGap (iOS, Android, Blackberry, Windows Phone 8, WebOS)
* Intel XDK (iOS, Android, Amazon, Nook, Windows 8, Tizen, Facebook, Chrome, WebApp)
* Cocoon (iOS, Android (WebGL support))
* Ejecta (iOS WebGL)
* Awesomium (EXE DMG)

[Phaser](https://github.com/photonstorm/phaser)
[impactjs](http://impactjs.com/)


### Javascript for Makers
Speaker: [Peter Christensen](http://pchristensen.com)

#### Why is software different?
* Hello world of software is easier than hello world of surgery
* Software is easy to distribute
* huge variety of tools

#### What if the UI went beyond the browser?
Maker Faire (videos of robotic bugs, car with fish and lobsters singing)

#### Hardware becoming software
[The Hardware Renaissance by PG](http://www.paulgraham.com/hw.html)

* arduinos
* raspberry pi

You don't have to figure out a lot of the hard things about hardware to use them in your software anymore.
The community around hardware -> software has grown.

#### How did I get involved?
[OpenROV](http://openrov.com/)
