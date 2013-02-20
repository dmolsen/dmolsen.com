---
title: 'Help Needed: Reviewing &#038; Updating Detector&#8217;s Feature &#038; Test Suite'
author: Dave Olsen
layout: post
permalink: /2012/06/19/help-needed-reviewing-updating-detectors-feature-test-suite
categories:
  - General
tags:
  - css3
  - detector
  - html5
  - javascript
  - modernizr
  - ringmark
  - tests
  - w3c
  - wciu
  - whatwg
---
As I push towards the v1.0 release of [Detector][1] I've decided to focus on refining the list of tests that form the core of Detector's "browser map." My original listing of tests was cherry-picked from Modernizr's "build tool." While a useful listing it doesn't cover every feature that may be of interest to developers. Especially, as I found, those developers primarily interested in mobile.

The [draft listing of Detector's v1.0 tests][2] is [available as a Google Doc][2]. I wasn't sure of the best way to leave feedback so I guess you can either reply to this post or put your comments in the "User Contributed Notes" section of each sheet. The primary criteria for a listed test is simply my own interest in that particular feature. The only type of tests that I've ruled out for now are ones that simply test browser performance (*e.g. FPS*).

The listing was built using the following resources:

*   [Modernizr's core tests & extra tests][3] listed in their repo
*   [Ringmark's core tests][4]
*   [The When I Can I Use tests][5]

In locations where I've listed that a test doesn't exist (*primarily Modernizr*) I simply mean that it's not included in the official repo for that library. It could exist elsewhere. Ringmark didn't contain every test I expected (*e.g. battery*) so maybe I overlooked something there as well. Suffice it to say it's been a few late nights.

I also referred to the following material as reference:

*   [HTML5 Rocks][6]
*   [Mobile HTML5 Compatibility Sheet][7]
*   [The HTML5 Test][8]
*   [WHATWG][9]
*   [W3C Standards & Drafts][10]

To explain the organization of the sheets a little bit… Each sheet is my attempt to organize tests into logical groups. There is overlap. The most important column is B as that determines what's happening with a  particular test. The key is included at the bottom of each sheet.

I would love feedback on the list. Suggestions of tests to include or remove are very much welcome. I know the doc is overwhelming but I wanted to record as much information as I could while doing this process rather than have to look up things later on. I haven't looked at performance issues yet, fine-tuned tests, or anything as I'm simply trying to decide if the features could prove useful to developers and act as a quality snapshot of a UA. All of that will come as I narrow down what will be in the v1.0 test suite.

Thanks.

 [1]: http://detector.dmolsen.com
 [2]: https://docs.google.com/spreadsheet/ccc?key=0AntZUVoCEOyYdFRpUjZOWUZyaWxoSTlLLW1XVHVldHc
 [3]: https://github.com/Modernizr/Modernizr
 [4]: https://github.com/facebook/coremob-tests/tree/master/tests
 [5]: http://tests.caniuse.com/
 [6]: http://www.html5rocks.com/
 [7]: http://mobilehtml5.org
 [8]: http://html5test.com/
 [9]: http://www.whatwg.org/specs/web-apps/current-work/multipage/#auto-toc-8
 [10]: http://www.w3.org/TR/