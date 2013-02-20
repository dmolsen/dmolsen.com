---
title: Current Status of Mobile Web OSP 2.5
author: Dave Olsen
layout: post
permalink: /2010/12/22/current-status-of-mobile-web-osp-2-5
categories:
  - Mobile Web OSP
tags:
  - mobile web osp
---
For the last few weeks I've been hard at work on Mobile Web OSP 2.5. Today I [committed][1] the first of my [content adapters][2] for the system and it's related to the calendar. While that's been one of the big features I wanted to include based on recent conversations I've had I've also implemented some other things that folks my find interesting and that go a bit beyond what I discussed in my [State of Mobile Web OSP post][3].

All of these changes are currently available in the [master branch][4] of the project. Because their are still some commits I haven't made the master branch should be considered *very unstable and may not work properly* but hopefully there's something there to be gleaned.

## Database Support Expanded

[MDB2 support][5] has been added and the project will come with drivers for MySQL, MSSQL, and PostgreSQL. MySQL will be the only database that I actively test though. Because MDB2 doesn't currently support SQLite3 that option is now turned off but I hope to find a solution before launching 2.5.

## Device Detection & Classification Updates

The core feature of Mobile Web OSP is the ability to display content in different templates based on the type of device requesting that content. In my "*State of…*" post I talked about being unsure on what I wanted to do with this future. Well, in the short term, I've attempted to expand the number of devices that get classified by the system as well as [breaking that service out into it's own class][6] to hopefully make it easier to utilize and update. There are some [neat functions][6] where you can deliver tweaks in templates based on type of device as well as version.

I've also added a JSON-based [simple API][7] for allowing other applications on your campus to use Mobile Web OSP as a device classification service. This should lead to only needing to update one place for all your device detection and classification needs.

That being said I'm still not sure this in-system feature will last. Looking ahead the Android tablets will cause my system a few headaches.

## More Granular Statistics

The internal statistics package has been upgraded to allow for more granularity in reporting devices based on the device classification class. For example, if you add special classifications for the Palm Pixi or Nokia handsets to the device detection class those devices will start to be automatically tracked in the internal stats as their own line item. Also, any new modules you may add to the system will also start tracking immediately without any changes to the databases. Note:* because of these changes access to year-over-year data goes out the window because it was such a major change. *

[Google Analytics support has been updated][8] to use the async version as well as properly tracking outgoing links, outgoing phone calls, and outgoing emails via Google Analytics Event Tracking feature. A bug with tracking clicks on the back button in WebKit templates has also been cleaned up.

## Accessibility Improvements

I've made some accessibility improvements for the heavily-JavaScript WebKit templates using jQTouch. The improvements [include better focus() support][9] for newly loaded "pages" as well as the addition of some ARIA roles for navigation assistance. Many thanks to Dave Mulder ([@davidlmulder][10]) for the feedback/help on this very important topic. The source for jQuery Mobile was also very informative.

## Module-specific Improvements

Some module-specific improvements:

*   Better RSS support in the News & Emergency modules including cache support through the use of Simple RSS (*this may change by launch of Mobile Web OSP 2.5 as I turn the RSS reader into a content adapter as well*)
*   A simple include file for the Emergency module so that one can quickly add a message that gets pushed to all three templates
*   Weather module now properly works with the new template scheme.
*   Module-specific JavaScript for creating new local databases on devices has been moved from a system-wide db.init.js file into the module-specific JavaScript init files.

## Security

The [example Apache virtualhost file][11] has been updated to give tips on how to properly restrict web access to parts of the system that don't need to be exposed that way.

## Delivery Date?

I'll have a better idea in early January on when this project will be delivered to the outside world. My goal is to get a new version of WVU Mobile Web rolled out before the kids come back for the Spring semester. That may be a bit ambitious as it includes quite a few sections that I need to develop from scratch. I'll try to keep you all updated though.

**Update December 28, 2010:** The second content adapter for the map has been committed.

**Update January 6, 2010:** There's also a new feature [proposal for federated search][12]. I've currently committed federated search functionality for maps and calendar.

 [1]: https://github.com/dmolsen/MIT-Mobile-Web/compare/49fba68a5b...6be7edcf0a
 [2]: http://www.dmolsen.com/mobile-in-higher-ed/?p=154
 [3]: http://www.dmolsen.com/mobile-in-higher-ed/?p=149
 [4]: https://github.com/dmolsen/MIT-Mobile-Web/tree/master
 [5]: http://pear.php.net/package/MDB2/redirected
 [6]: https://github.com/dmolsen/MIT-Mobile-Web/blob/master/web/page_builder/detection.php
 [7]: https://github.com/dmolsen/MIT-Mobile-Web/blob/master/web/api/index.php
 [8]: https://github.com/dmolsen/MIT-Mobile-Web/blob/master/web/templates/webkit/javascripts/ga.init.js
 [9]: https://github.com/dmolsen/MIT-Mobile-Web/blob/master/web/templates/webkit/javascripts/aria.init.js
 [10]: http://twitter.com/davidlmulder/
 [11]: https://github.com/dmolsen/MIT-Mobile-Web/blob/master/extra/mobile_vhost.conf
 [12]: http://www.dmolsen.com/mobile-in-higher-ed/?p=159