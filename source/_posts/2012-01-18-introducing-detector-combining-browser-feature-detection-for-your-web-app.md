---
title: 'Introducing Detector: Combining Browser- &#038; Feature-Detection for Your Web App'
author: Dave Olsen
layout: post
permalink: /2012/01/18/introducing-detector-combining-browser-feature-detection-for-your-web-app
categories:
  - General
  - Tools
tags:
  - browser detection
  - bryanrieger
  - detector
  - device detection
  - feature detection
  - ffly
  - future friendly
  - jamesgpearce
  - lukew
  - modernizr
  - modernizr-server
  - open device knowledge
  - responsive web design
  - ress
  - stephanierieger
  - yabfdl
  - yiibu
---
**Feb. 21, 2012**: v0.5 of Detector was pushed out. [Read about the new features][1].

**Feb. 27, 2012:** A small update, v0.5.1, was made to Detector to clean up PHP Notices as well as add two methods to [push Detector data to the browser][2] so the data can be used a la Modernizr.

With the initial release of [Yiibu's][3] [Profile][4], [Detector][5] is already YABFDL *(Yet Another Browser- and Feature-Detection Library)*. The main question behind Detector, "*How does one go about *intelligently *combining browser- and feature-detection into one package?*," has been floating around in my head ever since I heard Yiibu's talk, [Adaptation][6]. Because of two recent events, our [holiday card project][7] and the [OpenDDR/WURFL/ScientiaMobile kerfuffle][8], I decided to finally tackle that question and see what I could come up with to answer it.

## Introducing Detector

[Detector][9] (*[demo][5] & [code][10]*)  is a simple, PHP- and JavaScript-based browser- and feature-detection library that is still in its infancy. Detector gives server-side developers information about what types of devices may be requesting their content as well as the HTML5 & CSS3 features a requesting browser on that device may or may not support. With Detector a developer can serve the appropriate markup, stylesheets, and JavaScript to a requesting browser without being completely dependent on a browser-detection library being up-to-date nor completely dependent on a front-end-only script loader. [Detector][5] is based on [Modernizr][11], [modernizr-server][12], and the browser-detection library from [Mobile Web OSP][13]. It also benefits from a healthy dose of inspiration from [Yiibu's][3] [Profile][4]. Want more of the gory, technical details? [Check out the README][10] for more information.

## Why Create Detector?

With [Yiibu's][3] [Profile][4], Luke Wroblewski's ([@lukew][14]) article, "*[RESS: Responsive Design + Server Side Components][15],*" and the [Future Friendly][16] movement I think that more and more folks are accepting that server-side technologies still have a large part to play in delivering mobile-optimized solutions. That being said, browser-detection cheerleaders like myself can learn a thing or two from the responsive design/feature-detection folks. Detector was created as a way of, hopefully, combining the best of both browser- and feature-detection and giving server-side developers a lot of power and flexibility in developing cross-browser, as well as mobile, solutions.

### Flexible & Future Friendly

I wanted to address two primary goals when developing Detector. The first goal was to create a solution that was forward looking and could adapt to new devices and browsers on its own. I didn't want a developer to have to worry that their website might break if a new a browser came out with a different user-agent than those already being tracked. This is one of the real strengths of using feature-detection as a solution. A feature is either available or it isn't. The first time Detector gets a visit from a new user-agent string it tests that browser for all of its available features and saves that profile to disk for future use with other browsers with that same user-agent. In this way Detector can grow and adapt to changes in the browser & mobile landscape. Also, because Modernizr (*and it's long list of [pre-built tests][17]*) serves as the core feature-detection library of Detector a developer can add and track their own tests just by using the [Modernizer.addTest() plug-in API][18].

### Open Browser & Device Knowledge

My second goal was to see if I could find a way to capture and share device knowledge. While Detector is focused on *browser* knowledge as opposed to *device* knowledge I think the information is still useful overall. Especially to web developers who are, for the most part, only ever going to interact with the browser anyway. I feel very strongly that their should be a central, **open** resource for developers to rely upon to not only learn what browsers support what features but a way to use that data within their applications. Because of that I have signed onto the [Open Device Knowledge Collaborative][19]. Detector is not nearly stable enough to help create that resource now but I do hope that it can in the future. At some point I will create a central repository of browser profiles that anyone can use in their applications (*with or without Detector!*) and, via Git, developers will be able to submit their own profiles back to the central repository for others to use. It's an ambitious idea and their are a lot of hurdles yet to overcome but I do think it's an important goal for Detector and the community at large.

## Where Detector is Going

Detector is far from perfect as a solution. As I said, it's in its infancy. I'd love to see the following get addressed:

*   New profiles could contain bad data that, in its current incarnation, wouldn't get updated by more "reliable" browser visits in the future. Basically, is there a sampling and/or confidence metrics that could be used to re-test browsers?
*   Modernizr-based media query tests seem to be really flaky and it's obviously a problem with Detector itself. When I use the media queries outside of Detector they work as expected.
*   Versioning of profiles as well as creating that central repository so profiles can be used by anyone.
*   Most importantly, **Detector needs more browsers to use it to really test its capabilities and accuracy**.

While it is still early days for Detector hopefully lessons can be learned from its implementation for others developing similar solutions.

## Helping Me Test Detector

If you can, please hit the [Detector demo ][5](*<http://detector.dmolsen.com/>*) on, preferably, your mobile device of choice and see if Detector works as expected. If it doesn't please shoot me a note from the contact link under the Browser Profile information.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/2012/02/21/detector-v0-5-released-ua-parser-php-integration-browser-families-expanded-feature-tests-new-wiki/
 [2]: https://github.com/dmolsen/Detector/wiki/Pushing-Detector-Data-to-the-Browser-Tutorial
 [3]: http://yiibu.com/
 [4]: https://github.com/yiibu/profile
 [5]: http://detector.dmolsen.com/
 [6]: http://www.slideshare.net/yiibu/adaptation-why-responsive-design-actually-begins-on-the-server
 [7]: http://happyholidays.wvu.edu/
 [8]: http://openddr.org/takedown.html
 [9]: http://detector.dmolsen.com
 [10]: https://github.com/dmolsen/Detector
 [11]: http://www.modernizr.com/
 [12]: https://github.com/jamesgpearce/modernizr-server
 [13]: https://github.com/dmolsen/MIT-Mobile-Web
 [14]: http://twitter.com/lukew/
 [15]: http://www.lukew.com/ff/entry.asp?1392
 [16]: http://futurefriend.ly/
 [17]: http://www.modernizr.com/docs/#s2
 [18]: http://www.modernizr.com/docs/#addtest
 [19]: http://www.opendeviceknowledge.com/vision

 *[YABFDL]: Yet Another Browser- and Feature-Detection Library