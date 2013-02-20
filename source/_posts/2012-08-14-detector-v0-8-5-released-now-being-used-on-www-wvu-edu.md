---
title: 'Detector v0.8.5 Released: Now Being Used on www.wvu.edu'
author: Dave Olsen
layout: post
permalink: /2012/08/14/detector-v0-8-5-released-now-being-used-on-www-wvu-edu
categories:
  - Tools
tags:
  - detector
  - ress
---
With the release of the [new home page for West Virginia University][1] Detector is finally being used in production. Unfortunately, there were a few bugs that were uncovered with this move. [v0.8.5][2] fixes these issues and I now feel comfortable most folks can use [Detector][2] in their own production environments. The issues fixed include:

*   a very rare bug where the cookie used to set-up a profile wasn't properly cleared so a future visit would overwrite the profile with empty data.
*   the call to `addUAToList()` is now commented out. it became an unnecessary performance bottleneck.
*   profiles are now saved in directories that are based on the first two characters of the hash of the user-agent. this way one directory doesn't fill up with a ton of files and thereby possibly affecting performance. more on this below.

<div>
  But it's not all bug fixes…
</div>

## New Feature: Smarter Mustache Templating

One feature that I'm really excited about is the smarter fallbacks when using Detector with my [fork of mustache-php][3] (*included in the Detector project*). When using Detector and mustache-php to build a [RESS-based][4] website you can organize your Mustache partials based on [Detector's families feature][5]. Essentially, Mustache looks for partials based on the browser's family first and then fallbacks to a default directory of partials that's shared amongst all the families. I've written a [tutorial that explains how it all works][6].

With [v0.8.5][7] I've added a wrinkle to that default behavior. If you set splitFamily to true in config.ini Mustache will still look for a partial based on the browser's family first but then it will attempt to split the family name based on dashes rather than falling back to a default directory. This should give developers more flexibility when setting up families as well as limit duplicated partials. At least it did for us. A good example of how this feature might be useful is for delivering Retina images.

For the most part, the partials shared between a family set-up to address the layout needs of a Retina-capable mobile browser and the partials for a family set-up to address the layout needs of a modern mobile browser will be the same. Rather than duplicate these partials we can, with this new feature, simply set-up our Retina-quality family so that its name builds off of the latter family name. For example, the family name for the regular modern mobile browser might be ‘mobile-advanced'. We can then name our Retina-related family ‘mobile-advanced-retina'. Any partials shared between the two simply need to go in ‘mobile-advanced' as partial requests that aren't found in ‘mobile-advanced-retina' will fall back to it first.

## Early Stats

I've been very curious how Detector would perform once it was thrown into production. Most importantly, I wanted to know how many profiles it would create once a lot of different browsers could hit it. Performance has been fine. The profile numbers on the other hand have blown me away and they're almost entirely driven by IE 7 and 8. Since we launched at midnight on Thursday, August 2nd our home page has had ~72,000 unique visitors and ~238,000 pageviews. This is a slow time of year for us though our traffic should ramp up quickly. Based on those ~72,000 unique visitors **Detector has created 11,002 profiles**. They take up 45MB of disk space. The kicker really is IE 7 & 8. **Combined, IE 7 & 8 account for 7,952 of the 11,002 profiles (**72.3%)** **. I find it incredible that there's that much variation in IE user-agent strings. I guess Microsoft allowed anything to be stuck in the UA. For what it's worth, **IE 7 & 8 have only provided 25% of the visits during the same time period**.

I'll be keeping an eye on the disk usage. Maybe I'll need to think about a garbage collection routine for old profiles. Otherwise things seem to be working well.

 [1]: http://www.wvu.edu/
 [2]: http://github.com/dmolsen/Detector/
 [3]: https://github.com/dmolsen/Detector/tree/master/web/demo/mustache/lib/mustache-php
 [4]: http://www.dmolsen.com/mobile-in-higher-ed/2012/02/21/ress-and-the-evolution-of-responsive-web-design/
 [5]: https://github.com/dmolsen/Detector/wiki/Detector-Family-Tutorial
 [6]: https://github.com/dmolsen/Detector/wiki/Templating-with-Detector-&-Mustache-Tutorial
 [7]: http://github.com/dmolsen/Detector