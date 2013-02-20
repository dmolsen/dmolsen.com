---
title: 'Detector v0.5 Released: ua-parser-php Integration, Browser Families, Expanded Feature Tests, &#038; New Wiki'
author: Dave Olsen
layout: post
permalink: /2012/02/21/detector-v0-5-released-ua-parser-php-integration-browser-families-expanded-feature-tests-new-wiki
categories:
  - General
tags:
  - detector
  - modernizr
  - ua-parser
  - ua-parser-php
---
**Feb. 27, 2012:** A small update, v0.5.1, was made to Detector to clean up PHP Notices as well as add two methods to [push Detector data to the browser][1] so the data can be used a la Modernizr.

Detector v0.5 has been [posted to GitHub][2]. The [Detector demo site][3] has also been updated to reflect the new version.

## About Detector

[Detector][4] is a simple, PHP- and JavaScript-based browser- and feature-detection library that can adapt to new devices & browsers on its own without the need to pull from a central database of browser information. Detector dynamically creates profiles using a browser's *(mainly)* unique user-agent string as a key. Using [Modernizr][5] it records the HTML5 & CSS3 features a requesting browser may or may not support. [ua-parser-php][6] is used to collect and record any useful information *(like OS or device name)* the user-agent string may contain.

With Detector a developer can serve the appropriate markup, stylesheets, and JavaScript to a requesting browser without being completely dependent on a front-end-only resource loader nor a browser-detection library being up-to-date. Detector can be used with a solution like [Mustache][7] to [provide robust templating support][8].

The following are the major changes in this release:

## ua-parser-php Integration

I was unhappy with the original browser detection library in Detector so I created a PHP-based pseudo-fork of the [ua-parser project][9] called [ua-parser-php][6]. It is included as a submodule of Detector and provides a much more robust classification system for browsers and mobile devices. Because of the [number of attributes][6] it parses out of a user-agent string it should give developers more flexibility when developing solutions.

## Browser Families

With the new [families feature][10] in Detector developers can organize browsers that share certain traits into groupings. With families a developer can test for a browser's grouping rather than each individual feature that browser may support when displaying content. This might be especially useful for templating solutions.

## Expanded Feature Tests

[Modernizr 2.5.2][11] has been included with this release as well as an expanded set of features including tests for cssremunit, deviceorientation, devicemotion, and lowbandwidth support. See the [full list of Detector's core tests][12].

## Detector Wiki Added

I've attempted to grow the [documentation for Detector][13] beyond the original, limited README by using the wiki that comes with a GitHub repository. Content includes:

*   [How Detector Works][14]
*   [Adding & Using Detector With Your Application][15]
*   [Detector Test Tutorial][16]
*   [Detector Family Tutorial][10]
*   [Templating with Detector & Mustache Tutorial][8]

## Other Changes

Those are the big changes but their are a few other, minor changes:

*   a configuration file for setting debug mode as well of locations of files & directories is now included
*   both core and extended profiles can now be versioned
*   the original layout of the files has been cleaned up some
*   two simple demos, one for [including a YouTube video][17] and the [other for templating][18], are now included
*   while not a change in Detector per se, the [archive of user agents][19] now contains **170+ user agents** and their associated feature tests

If you have any questions about the project please feel free to drop a line in the comments.

 [1]: https://github.com/dmolsen/Detector/wiki/Pushing-Detector-Data-to-the-Browser-Tutorial
 [2]: http://github.com/dmolsen/Detector/
 [3]: http://detector.dmolsen.com/
 [4]: https://github.com/dmolsen/Detector
 [5]: http://modernizr.com/
 [6]: https://github.com/dmolsen/ua-parser-php
 [7]: http://mustache.github.com/
 [8]: https://github.com/dmolsen/Detector/wiki/Templating-with-Detector-&-Mustache-Tutorial
 [9]: http://code.google.com/p/ua-parser/
 [10]: https://github.com/dmolsen/Detector/wiki/Detector-Family-Tutorial
 [11]: http://modernizr.com
 [12]: http://detector.dmolsen.com/demo/modernizr-listing/
 [13]: https://github.com/dmolsen/Detector/wiki
 [14]: https://github.com/dmolsen/Detector/wiki/How-Detector-Works
 [15]: https://github.com/dmolsen/Detector/wiki/Adding-&-Using-Detector-With-Your-Application
 [16]: https://github.com/dmolsen/Detector/wiki/Detector-Test-Tutorial
 [17]: http://detector.dmolsen.com/demo/ytembed/
 [18]: http://detector.dmolsen.com/demo/mustache/
 [19]: http://detector.dmolsen.com/archive.php