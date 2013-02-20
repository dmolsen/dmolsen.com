---
title: 'Responsive Web Design &#038; The Mobile Web'
author: Dave Olsen
layout: post
permalink: /2010/08/10/responsive-web-design-the-mobile-web
categories:
  - General
tags:
  - beep
  - context
  - fling
  - grigs
  - jcroft
  - mobile web
  - responsive web design
---
I guess I'm not as up on the latest buzz in the web world as I thought I was. Back at the end of May Ethan Marcotte ([@beep][1]) posted an article on [A List Apart][2] entitled [*Responsive Web Design*][3]. The core position of the article is that by using the media query tag you can provide the appropriate CSS markup for any type of device, especially mobile devices. For example, `media="print"` would provide a particular stylesheet for the page when a user prints vs `media="screen"` which provides a stylesheet for users on desktops. Pretty old school, standard stuff. The trick is that in the CSS3 specification a developer can define a particular stylesheet based not only on media type but also on device attribues like `max-device-width` which is where the whole "we can serve a mobile-specific stylesheet!" thing comes into play.

Does responsive web design offer an interesting and maybe easier way forward for implementing mobile web sites? Yes. Does that mean it's a good idea? No.

## Fool's Gold

When I talk to developers who are about to embark on their very first mobile design they often want to just use CSS. It seems like the perfect solution. One set of content with multiple look and feels all without the aid of multiple templates or a CMS. A plain old win/win. Ignoring the significant [context issues][4] I've always cautioned these developers on technical grounds because they'll still be throwing most/all the same media down the pipe at the mobile device even if it's ostensibly hidden to the end user. Jason Grigsby ([@grigs][5]) sums up the issue from a technical perspective in his article [*CSS Media Query for Mobile is Fool's Gold*][6]:

> Ferreting out the problems with CSS media queries for mobile devices is easy if you look at what media queries purportedly promise:
> 
> > All you need to do to transform your desktop web design into something optimized for devices with *smaller* screens, *less powerful* CPUs, and *slower network connections* is to *add more code*.
> 
> The idea of adding more code—adding more to download—in order to optimize for mobile should be the first clue that this isn't a good solution.

Jason then does a[ great job of explaining all the technical issues][6] (*in some serious depth too*) that make CSS media query a failure from a mobile development standpoint. It's always something I sort of assumed but it's nice to have numbers to back up my argument for the future.

*Note: *Jason has also offered up follow-up article [*More on CSS Media Queries*][7] that is worth reading. He attempts to take a softer position on them.

## Mobile Context

Jeff Croft ([@jcroft][8]) also does a good job in following up on the original article with his post [*On "Responsive Web Design" and the Mobile Context*][9] which has an obvious focus on [my big theme for mobile][4], ***context***. The real bonus for Jeff's post though are the comments, with Ethan, Jason and Brian Fling all chiming in, so you should definitely [check them out][9].

And to be fair to Ethan he does offer the following note that touches on context towards the end of his original post:

> That's not to say there isn't a business case for separate sites geared toward specific devices; for example, if the user goals for your mobile site are more limited in scope than its desktop equivalent, then serving different content to each might be the best approach.

Proper web design *in general* should have a focus on context and use cases. But context is especially important in mobile. Does that mean mobile is going to be that much more work for you as the developer? Yup. Are you clients and/or users going to get a much better product though? Hell yeah.

Jason  quotes Brian Fling towards the end of his article and I think it sums up context and the reason to do it nicely:

> Create a product, don't re-imagine one for small screens. Great mobile products are created, never ported.

 [1]: http://twitter.com/beep
 [2]: http://www.alistapart.com/
 [3]: http://www.alistapart.com/articles/responsive-web-design/
 [4]: http://www.dmolsen.com/mobile-in-higher-ed/?p=40
 [5]: http://twitter.com/grigs
 [6]: http://www.cloudfour.com/css-media-query-for-mobile-is-fools-gold/
 [7]: http://www.cloudfour.com/more-on-css-media-queries-for-mobile/
 [8]: http://twitter.com/jcroft/
 [9]: http://jeffcroft.com/blog/2010/aug/06/responsive-web-design-and-mobile-context/