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


Speaker: [Divya Manian](http://html5devconf.com/speakers/divya_manian.html), Adobe
