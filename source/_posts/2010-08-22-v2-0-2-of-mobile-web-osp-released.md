---
title: v2.0.2 of Mobile Web OSP Released
author: Dave Olsen
layout: post
permalink: /2010/08/22/v2-0-2-of-mobile-web-osp-released
categories:
  - Mobile Web OSP
tags:
  - google analytics
  - mobile web osp
  - v202
---
Hot on the heels of v2.0.1 of [Mobile Web OSP][1] comes v2.0.2. There are two diffs that cover the code changes ([diff #1][2] & [diff #2][3]). The code is obviously [in the repo][4]. This release addresses two issues:

1.  The homescreen icons for WebKit devices in the default theme are now properly referenced. They'll now load correctly when you first bring up the system.
2.  The reference to the Google Analytics tracking pixel in the basic template has been updated. This was causing a doubling of hits in the PageViews table for devices using those templates. It shouldn't have skewed stats too much but definitely put this fix into your own code if you can.

If you've found an issue or bug [please let me know][5] so that I can fix it for others.

 [1]: http://mobilewebosp.pbworks.com/
 [2]: http://github.com/dmolsen/MIT-Mobile-Web/commit/042fa30649a5cbcf7a5914c056c55f312a8a200a
 [3]: http://github.com/dmolsen/MIT-Mobile-Web/commit/a7453a611b21b3e6d58c64a5b75bbdba9d64d903
 [4]: http://github.com/dmolsen/MIT-Mobile-Web/
 [5]: http://github.com/dmolsen/MIT-Mobile-Web/issues