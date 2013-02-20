---
title: 'YAMJF: jQuery Mobile'
author: Dave Olsen
layout: post
permalink: /2010/08/16/yamjf-jquery-mobile
categories:
  - Mobile Web OSP
  - Tools
tags:
  - jqtouch
  - jquery
  - jquery mobile
  - mobile web osp
  - sencha
---
For a while it has seemed like [jQuery][1] was missing the boat on a mobile-optimized version of their framework. I went so far as to try to build out my own custom version of jQuery to limit its footprint to only those features I really needed (*that didn't work out too well*). I always figured that the jQuery team would just release a smaller, nimbler version of the framework. Boy, was I wrong.

Last week the jQuery team announced the [jQuery Mobile framework][2]. The good news? [The strategy][3] is for the framework to do all the heavy lifting for the developer in terms of optimizing look & feel for a long-list of [A-class devices][4]. The bad news? There's no actual product yet.

So far jQuery Mobile is basically a manifesto and [some pretty design concepts][5]. I'm hopeful that they can really deliver on this product towards the end of 2010 like they're claiming. Frankly, I'd be happy if they released a product which didn't support everything but they were able to slowly upgrade behind the scenes if it meant I could get my hands on it faster. I really want to see if the code will work for me.

Currently [Mobile Web OSP][6] is using [jQTouch][7] for its fun device interactions on iPhone and Android. jQTouch is a nice plug-in for jQuery but it hasn't seen much movement this year. The original developer for it went off to do mobile development for ExtJS which then ended up releasing [Sencha Touc][8]h. Unfortunately Sencha Touch is a non-starter as far as Mobile Web OSP is concerned because of how it builds content layouts. The inclusion of jQTouch was enough of a architecture change that I'm not sure the benefits of a second, even bigger architecture change really makes sense.

But even if you're not using Mobile Web OSP it looks like there's another mobile JavaScript framework on the way to help you deliver your Web 2.0 inspired mobile web app.

 [1]: http://jquery.com/
 [2]: http://jquerymobile.com/
 [3]: http://jquerymobile.com/strategy/
 [4]: http://jquerymobile.com/gbs/
 [5]: http://jquerymobile.com/designs/
 [6]: http://mobilewebosp.pbworks.com/
 [7]: http://www.jqtouch.com/
 [8]: http://www.sencha.com/products/touch/