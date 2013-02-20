---
title: v2.0.1 of Mobile Web OSP Released
author: Dave Olsen
layout: post
permalink: /2010/08/16/v2-0-1-of-mobile-web-osp-released
categories:
  - Mobile Web OSP
tags:
  - fixes
  - mobile web osp
---
On Friday of last week I made some minor fixes to [Mobile Web OSP][1] based on some bug reports. Those changes are now in the [GitHub repo][2]. Here's the [diff that shows all the changes to the code][3] if you need to recreate them in your own copy. The following changes were made:

1.  The device detection has been updated to recognize Opera Mobile.
2.  The device detection has been updated so that deprecation errors aren't thrown in PHP 5.3+. All of the references to `eregi()` should have been replaced with `preg_match()`.
3.  The `input` text color for the default theme is now black  for easier readability.
4.  The big fix was to the category drop-down in the map section. That should now work and switch the view based on the selected option.

If you've found an issue or bug [please let me know][4] so that I can fix it for others.

 [1]: http://mobilewebosp.pbworks.com
 [2]: http://github.com/dmolsen/MIT-Mobile-Web
 [3]: http://github.com/dmolsen/MIT-Mobile-Web/commit/0d56b4c3f64572a1b01d56228c6dae234648632a
 [4]: http://github.com/dmolsen/MIT-Mobile-Web/issues