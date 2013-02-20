---
title: RESS, Server-Side Feature-Detection and the Evolution of Responsive Web Design
author: Dave Olsen
layout: post
permalink: /2012/02/21/ress-and-the-evolution-of-responsive-web-design
categories:
  - General
tags:
  - beep
  - browser detection
  - dataatlas
  - detector
  - feature detection
  - ffly
  - future friendly
  - jonarnes
  - lukew
  - modernizr
  - mustache
  - responsive web design
  - ress
  - rwd
  - slightlylate
  - ua-parser-php
  - wurfl
  - yiibu
---
In May 2010 Ethan Marcotte ([@beep][1]) wrote the seminal article, *[Responsive Web Design][2]*. At first I took a dim view of the piece. Most of [my mobile experience][3] at the time was in developing mobile-optimized experiences that relied on browser-detection & serving separate templates. Honestly, it worked for me as a, primarily, server-side dev and it worked well. To me, responsive web design seemed like a front-end solution that didn't take into account many of the issues facing mobile developers… apart from screen width that is.

Fast forward a year and a half (*and quite a few arguments*)… I've now worked on [one responsive project][4], I've watched a number of other responsive projects come out of [our department][5], and I've come to appreciate where and when responsive web design works and works well. On top of that I've learned how helpful front-end projects like [Modernizr][6], [MicroJS][7], and [YepNope.js][8] can be to any developer. That being said, it's tough to teach an old dog new tricks and, to me, it still seemed as if their was something not quite right about responsive web design.

At this point I won't rehash the arguments. Yes, dear dead horse, you can have a rest. Instead, I'll focus on an article Luke Wroblewski (<a href="http://twitter.com/lukew/" rel="nofollow">@lukew</a>) wrote entitled, *<a href="http://www.lukew.com/ff/entry.asp?1392" rel="nofollow">Responsive Design + Server Side Components</a>*.

## RESS: Responsive Design + Server Side Components

For a while now I've felt like I was somehow out of touch for still preferring browser-detection over responsive design (*like I said, I'm an old dog*). I'm assuming it's because I tend to follow front-end folks on Twitter who are very much on the responsive web design bandwagon. But between [Luke's article][9], [Yiibu's][10] talk, *[Adaptation][11],* as well as their [Profile tool][12], and the news that [82% of Alexa's top 100 properties used server-side detection to modify some amount of their content][13] I started to feel a little less out of touch.

The principle concept that I found so intriguing in Luke's article, as well as the work done by Yiibu, is that **browser-detection can be used to help inform an overall responsive design as opposed to being the be-all-end-all for templating**. By this I mean that partial pieces of content can be inserted intelligently and where appropriate (*think images*) into a larger layout that's given to all browsers and is governed by responsive design principles. Hence the combining of "*responsive design*" and "*server side components*" in Luke's name for the technique.

This isn't something that I should consider revolutionary. On the face of it's sort of "*Duh!*" but sometimes even the obvious has to be pointed out. It's nice to see a bridge of sorts form between these two competing concepts. Their is value on both sides of the fence and they can and should work together. The question is "*How?*"

## Implementing a RESS Solution

Luke does a good job of [taking a reader through a theoretical(?) RESS solution][9] that is based on his experiences at his start-up, Bagcheck. He shows,  quite clearly, how the server-defined partials fit in nicely with an overall responsive design. One thing that the original RESS example fails to review is *how* content is classified for browsers though there is a nod towards user agent detection. I was curious to see how that part of a RESS solution worked so I put together one of my own that used [Mustache][14] just like in his example and [Detector.][15]

[My implementation of a RESS solution][16] is very simple. I didn't explore much beyond modifying some markup, adaptive images, and CSS. The first thing that I realized when I started tackling the "*how*" was that I was going to have to categorize browsers into classes (*to be fair, Luke does mention classes*). For the [purposes of the example][16] I set the browser classes to be [desktop][17], [mobile-advanced][18], and [mobile-basic][19]. The desktop class has "regular-sized" images, the mobile-advanced class has smaller images as well as some modified CSS, and the mobile-basic class has a very simple layout that utilizes accesskeys.

If you're interested in how I set-up [the demo][16] and [how it all works][20] please [check out the tutorial][20] and [the source][21]. What I'd like to talk about now is how I ended up with my classifications and how I think it points to more responsive solutions *on the server* and not just in the browser.

## Taking Feature-Detection Server-Side

Developers have been using server-side libraries & services like [WURFL][22], [DeviceAtlas][23], and [51Degrees.mobi][24] to provide mobile device characteristics for ages. In that respect, server-side feature-detection is nothing new. I would propose that we update our terminology a bit though. "*Device detection*" seems anachronistic and, frankly, misguided to me. Who cares what a device can do if the browser, the bit we as developers actually interact with, can't access them?  This is not to suggest that these device databases don't contain that kind of information but rather that they include details that, for the most part, might not matter to developers. In order to get more relevant data there is one technique that server-side developers should appropriate from our front-end brethren and it's *browser* *feature-detection*.

In his article, *[Cutting the Interrogation Short][25]*, Alex Russell ([@slightlylate][26]) makes an interesting proposal. He suggests, "*feature tests should only ever be run* ***when you don't know what UA you're running in***." This is a proposal I wholeheartedly agree with. So where to store the results of these feature tests that you want to run only once per user-agent? Alex suggests a few methods that rely on the front-end detection libraries but I would suggest that the results get stored in a server-side cache (*but, hey, I'm biased*). Feature test results stored on the server, using the user agent as a key, gives server-side code the ability to act on them making the server-side code that much smarter about what should be delivered. If necessary, the server-side code can always pass the list of features for a particular user agent to the browser as a cookie or a JavaScript include. Also, if tests are stored server-side the initial set of tests can be [extremely robust][27]. The developer would capture a lot of details but still have control over what gets delivered to the browser thereby optimizing the experience for their visitors. Hopefully, it could make for a "*best of both worlds*" scenario.

And server-side feature-detection is what is being done in my [RESS demo][16] and helping me classify browsers… well, sort of. The demo was created to help put my browser- and feature-detection library, [Detector][28], through its paces. One of its core features is offering [browser families][29] based on definitions that combine information from traditional user agent parsing (*via [ua-parser-php][30]*) and information from [Modernizr][31]-based tests (*[full list][27]*). The families in the demo are not based purely on browser features as determined feature-detection but that's not to say that Detector couldn't (*and it probably should*) be expanded to include more information on, say, browser-window width (*which is currently one of the few things it doesn't capture*) and could then rely almost exclusively on feature tests. But there's actually one area where these cached feature tests would offer a lot of help…

## It's Not Just About Mobile Versus Desktop

RESS, server-side feature-detection, and Detector are *not* mobile solutions. Yes, they come from people focused on mobile-related issues but any of these options can be used in helping deliver optimized experiences to *any* browser. In the same way that Modernizr helps polyfill for older browsers, server-side feature-detection and RESS can and do offer similar capabilities. I'd hate to see them get pigeonholed as solutions that are only implemented by mobile developers. I believe that the combination of these techniques can offer a very robust platform for building [future friendly][32] websites and apps. That said, there is still work to do to make these solutions as robust as possible.

## RESS Doesn't Solve the Dumb Content Problem… Yet

In *[Next Steps of Responsive Web Design][33]* Jon Arnes Sæterås ([@jonarnes][34]) writes, "*It is not only the **design** of the web site and the **layout** of content that needs to be adapted of enhanced; the idea of being responsive, adaptive and enhancing, must be implemented in the whole value chain.*" His value chain contains four parts:

*   Stupid Editor
*   Stupid CMS
*   Stupid Web Server
*   Device (*I'd suggest browser*) assumed to be intelligent

RESS and storing feature-detection results on the server  can go a long way in making the web server smarter and giving us a better idea of just how intelligent that browser is. But even addressing those two things only means that the *output* is smarter. Neither solutions address how content enters the system (*e.g. the editor*) and how it's stored (*e.g. the CMS*). For example, in the [mobile-advanced layout of the demo][18] on whom or what does it fall to properly crop & size the images?

In the same way that responsive web design made designers and front-end developers think more about how to be both mobile and [future friendly][35] I'm hopeful that RESS and server-side feature-detection can start a conversation amongst those of us focused on the server end of things (*especially content management systems!*) about how we can better deliver content to make those responsive web designs that much better. Can we help responsive web design evolve that much more?

 [1]: http://twitter.com/beep
 [2]: http://www.alistapart.com/articles/responsive-web-design/
 [3]: http://m.wvu.edu/
 [4]: http://happyholidays.wvu.edu/
 [5]: http://universityrelations.wvu.edu/
 [6]: http://modernizr.com/
 [7]: http://microjs.com/
 [8]: http://yepnopejs.com/
 [9]: http://www.lukew.com/ff/entry.asp?1392
 [10]: http://yiibu.com/
 [11]: http://www.slideshare.net/yiibu/adaptation-why-responsive-design-actually-begins-on-the-server
 [12]: https://github.com/yiibu/profile
 [13]: http://www.circleid.com/posts/20120111_analysis_of_server_side_mobile_web_detection/
 [14]: http://mustache.github.com/
 [15]: http://detector.dmolsen.com
 [16]: http://detector.dmolsen.com/demo/mustache/
 [17]: http://detector.dmolsen.com/demo/mustache/?pid=13ee8513d6fb7f97aef6635309b91f40
 [18]: http://detector.dmolsen.com/demo/mustache/?pid=e1bd58cc186d3a2156b6ebddb558fd41
 [19]: http://detector.dmolsen.com/demo/mustache/?pid=658e6d9b003bb3f3a3d9ae6e5ca1a42a
 [20]: https://github.com/dmolsen/Detector/wiki/Templating-with-Detector-&-Mustache-Tutorial
 [21]: https://github.com/dmolsen/Detector/tree/master/web/demo/mustache
 [22]: http://wurfl.sourceforge.net/
 [23]: http://deviceatlas.com/
 [24]: http://51degrees.mobi/
 [25]: http://infrequently.org/2011/01/cutting-the-interrogation-short/
 [26]: http://twitter.com/slightlylate
 [27]: http://detector.dmolsen.com/demo/modernizr-listing/
 [28]: http://detector.dmolsen.com/
 [29]: https://github.com/dmolsen/Detector/wiki/Detector-Family-Tutorial
 [30]: https://github.com/dmolsen/ua-parser-php
 [31]: http://modernizr.com
 [32]: http://futurefriend.ly
 [33]: http://mpulp.mobi/2011/05/next-steps-of-responsive-web-design/
 [34]: http://twitter.com/jonarnes
 [35]: http://futurefriend.ly/