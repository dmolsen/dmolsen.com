---
title: 'Detector v0.8.0 Released: Modernizr for Your PHP App Now Cleaner, Leaner, &#038; Meaner'
author: Dave Olsen
layout: post
permalink: /2012/06/04/detector-v0-8-0-released-modernizr-for-your-php-app-now-cleaner-leaner-meaner
categories:
  - General
tags:
  - detector
---
In preparation for some summer projects I cleaned up my PHP & [Modernizr-based][1] browser- and feature-detection library, [Detector][2]. You can get a taste of what it can do by visiting the [feature list page][3] or checking out [the RESS template demo][4]. The code and feature-set are essentially where I want them to be for 1.0. I could stand to add proper unit tests and the like. I'll attempt to add them in the near future but my schedule is getting really busy. The highlights for this release include:

*   a better job of handling browsers that don't support JavaScript or cookies. This extends to customizable family properties for those same browsers as well as search engine bots. [Learn more in the docs][5].
*   the ability to change the family property for a browser via a request variable. For responsive designs this could mean "desktop" mode. [Learn more in the docs][5].
*   Modernizr-based tests can now be run once per-session for those features that need to be tested on a per browser basis but won't change in subsequent requests (*e.g. pixel density ratio*). [Learn more in the docs][6].
*   in general I've tried to DRY up the code & reduce memory footprint

On the face of it it doesn't seem like a whole lot happened. More changes are listed in the [CHANGELOG][7]. This release, in my opinion, makes Detector a robust and flexible library that brings PHP developers that much closer to their front-end brethren. Now we can build dynamic, future-friendly applications that can take advantage of browser properties server-side.

 [1]: http://modernizr.com/
 [2]: https://github.com/dmolsen/Detector
 [3]: http://detector.dmolsen.com/
 [4]: http://detector.dmolsen.com/demo/mustache/
 [5]: https://github.com/dmolsen/Detector/wiki/Detector-Family-Tutorial
 [6]: https://github.com/dmolsen/Detector/wiki/Detector-Test-Tutorial
 [7]: https://github.com/dmolsen/Detector/blob/master/CHANGELOG