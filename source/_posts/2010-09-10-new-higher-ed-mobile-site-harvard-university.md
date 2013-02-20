---
title: 'New Higher Ed Mobile Site: Harvard University'
author: Dave Olsen
layout: post
permalink: /2010/09/10/new-higher-ed-mobile-site-harvard-university
categories:
  - Design Patterns
tags:
  - campus map
  - dining
  - federated search
  - google maps
  - harvard university
  - mit mobile framework
  - modo labs
  - search
---
*I recently added five sites to the *[*Higher Ed Mobile Directory*][1]* bringing the directory to a total of 84 sites. This article is one part of a five part series showing off these new sites. Do you have a mobile site for your school that you want to feature on this blog and/or have listed in the directory? Please *[*drop me a line*][2]*.*

## Harvard University – m.harvard.edu

The folks who brought you the original [MIT Mobile Web project][3] have now spun off there own company, [Modo Labs][4]. Their first client looks to be Harvard University. Version 2 of MIT Mobile Framework (*which I hope to feature once I get the all clear*) now powers the [Harvard University Mobile Internet][5]. There's a [nice post][6] on the Harvard Gazette site detailing the launch. Two screenshots:

<div>
	<div style="float: right; width: 48%;"><img class="alignnone size-full wp-image-103" title="harvard_main" src="/wp-content/uploads/2010/09/harvard_main-e1284111373453.png" border="1" alt="" style="flaat" /></div>
	<div style="float: left; width: 48%;"><img title="harvard_dining" src="/wp-content/uploads/2010/09/harvard_dining-e1284111422161.png" border="1" alt="" /></div>
	<div class="clearfix"></div>
</div>

The main focus of the Harvard mobile site is *search*. The search feature actually searches across multiple data sources and then shows you a nicely organized set of results. This is known as [federated search][9] (*honestly, I had to look it up*). Currently the following sources are searched by the Harvard mobile search feature: campus directory, campus map, events calendar, courses, and news. It really has to be experienced to fully appreciate how cool it is so [try it out][10]. I have to say that this is one of the more intriguing features of the upcoming release of the new version of the MIT Mobile Framework. Originally when I had heard "federated search" I was "meh" because I didn't really get what the data sources would be but seeing it in action… pretty freaking cool and I expect it to be copied in other higher ed mobile sites.

The other section I really like is the dining menus section. We're implementing something similar so it's nice to get a good design pattern. But the section also highlights a problem I have with the MIT Mobile Framework. Their appears to be a serious lack of integration of sections with the campus map. I also think the campus map itself is a bit weak as a section but I'm partial to Google Maps (*though to be fair, the JavaScript to power Google Maps is heavy on a mobile connection*). Not only could the dining menus section benefit from the campus map link but so could the calendar and directory sections (*ed. note: I did limited searches and didn't see any comprehensive links to the campus map but if their are feel free to correct me*).

One of the great challenges facing higher ed in the mobile space is linking our information like calendar events, directory listings, and news articles with locations. While the federated search exhibited in the Harvard site is very cool just imagine one based on GPS that answers the question "*What is near me?*" To me that should be one of the real drivers for us as we further develop our mobile frameworks. It'll take a lot of coordination across an entire campus but I think it's necessary to make our offerings compelling and useful long-term.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/?page_id=43
 [2]: http://www.dmolsen.com/mobile-in-higher-ed/?page_id=3
 [3]: http://sourceforge.net/projects/mitmobileweb/
 [4]: http://modolabs.com/
 [5]: http://m.harvard.edu/
 [6]: http://news.harvard.edu/gazette/story/2010/08/access-harvard-on-mobile-device/
 [7]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/09/harvard_main.png
 [8]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/09/harvard_dining.png
 [9]: http://en.wikipedia.org/wiki/Federated_search
 [10]: http://m.harvard.edu/home/