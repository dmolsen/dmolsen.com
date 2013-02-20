---
title: Deep Links and JavaScript Mobile Frameworks Suck
author: Dave Olsen
layout: post
permalink: /2011/01/11/deep-links-and-javascript-mobile-frameworks-suck
categories:
  - Mobile Web OSP
tags:
  - deep links
  - jqtouch
  - mobile web osp
  - scope creep
---
When I chose [jQTouch][1] for the WebKit templates in [Mobile Web OSP][2] I gained some interesting look & feel functionality. Unfortunately, I *gave up* a very important feature, **deep linking**. Basically I killed one of the best features of mobile web compared to native apps. That is to say, I killed the ability to actually use the web as it was intended which is to *link from any one bit of content to any other <span style="text-decoration: underline;">directly</span>*. It was the price I paid for a "cool framework that looked native."

In testing the new location functionality for the campus map module I grew increasingly frustrated with this state of affairs. Every tweak I made to the map detail template required me to: reload the app, click the map icon, select "favorites", select a building, and then load the map. It'd be so much easier if I could just hit freaking reload! So that's what I set out to fix.

## What I've Tweaked in Mobile Web OSP to Allow Deep Linking

First off, the fix to this situation doesn't really affect jQTouch so if you're curious about how to implement this in your jQTouch app you're out of luck. The beauty of Mobile Web OSP is that every page is dynamically created. This means that I can pass variables around and modify templates on the fly. Second, all this passing around of vars gets ugly… fast.

To view a diff of all of the changes that went into this fix [check out the commits on GitHub][3]. But the basics of what's happening are below:

*   Every request is checked to see if a) it's coming from a WebKit device and b) if it has the request variable `ir` (*aka internal request*) 
    *   if it's from a WebKit device and has the request variable `ir` then Mobile Web OSP handles the request normally
    *   if it's missing the request variable `ir` then that's where things get interesting…
*   The request is then redirected to the index page ([*code*][4]) where: 
    *   the general header with all the necessary elements for jQTouch and the rest of the system are loaded
    *   behind-the-scenes a request with the request variable `ir` is made to get the contents of the initially requested page. a second variable `dl` (*aka direct lin*k) is included so that the toolbar is modified to show a link to *home* instead of the normal *back* button.
    *   the general footer is loaded
*   At this point everything *should* work normally

Eyes glazed over yet?

## Caveats & Notes

If you're implementing this in a similar system to Mobile Web OSP there are a couple of gotchas:

*   The biggest gotcha is if you need anything dynamically loaded on page/panel load. For example, in the campus map module I use jQTouch's `pageAnimationStart` callback on the map detail div to initialize and load Google Maps. Well, if you deep link to the map detail the `pageAnimation` never runs and no map loads. I addressed this issue by including a `document.ready` call in the map detail div to load the map when it's directly requested. This also affected the favorites check in Calendar and People.
*   There is [one small tweak][5] to jQTouch to include the request variable `ir` on each `GET` request.
*   For form fields I also included the request variable `ir` as a hidden input. I'm not sure it's really needed but better safe than sorry.
*   At the moment this only handles a link back to the main home page instead of the section in which the detail may be from (*e.g. a link to the map detail will have a link back to home instead of map*). Hopefully I can address this at some point. Something is better than nothing though.

## Conclusion

Deep link support opens a lot of options for developers. Now I can feel much more comfortable including a "share" feature that I know will work across all the templates. When pushing requests from external sources like our main calendar I can now directly target the calendar module. But the best part should be that it reduces user confusion and frustration. It should definitely reduce developer frustration when testing new features

## Addendum: Scope Creep Also Sucks

I'm definitely suffering from scope creep on this latest release. Originally it was going to be a 2.1 release with some bug fixes, then a 2.5 releases with some decent new features and now I think I'm getting close a full point (3.0) release with all the big changes I've made. The [CHANGELOG is getting seriously long][6]. Unfortunately, as I come across "itches" in the system I can't seem to stop from itching them. Hopefully all the changes make a better product in the future and no one is waiting on me too long.

> *I swear a non-Mobile Web OSP blog post will show up here shortly. I have some interesting things related to statistics in the works. Thanks for bearing with me...*

 [1]: http://www.jqtouch.com/
 [2]: http://mobilewebosp.pbworks.com/
 [3]: https://github.com/dmolsen/MIT-Mobile-Web/compare/8358e7bd74...9052bf1e35
 [4]: https://github.com/dmolsen/MIT-Mobile-Web/compare/8358e7bd74...9052bf1e35#diff-6
 [5]: https://github.com/dmolsen/MIT-Mobile-Web/compare/8358e7bd74...9052bf1e35#diff-15
 [6]: https://github.com/dmolsen/MIT-Mobile-Web/blob/9052bf1e35419d9e30133faa9a5fd44f0f4a8ce9/CHANGELOG