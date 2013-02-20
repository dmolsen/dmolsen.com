---
title: Results from Higher Ed Mobile Website Technical Survey
author: Dave Olsen
layout: post
permalink: /2011/02/01/results-from-higher-ed-mobile-website-tech-survey/
categories:
  - Statistics
tags:
  - karinejoly
  - markgr
  - neveragain
  - Statistics
---
For some time I've been interested in getting a snapshot of the state of the ***technical*** implementations of mobile websites in higher education. Last week I tried to pull some numbers together on that topic for [my talk on HigherEd Live][1]. If you're interested in more "management"-type questions Karine Joly ([@karinejoly][2]) is currentl[y running a survey][3] to get answers to those. Take some time to help the rest of higher ed out by [answering a few questions][3]. *It doesn't matter if you have a mobile higher ed site or not!*

## The Data

For this survey I reviewed institutional mobile websites for schools listed in my [Higher Ed Mobile Directory][4]. By "*institutional*" I mean that I ruled out purely marketing-focused sites like the [WVU Today Mobile Experience][5] and library mobile sites. Institutional mobile websites are meant to provide services to an entire campus and not just a small segment of the population. To help populate the Higher Ed Mobile Directory I used a [list of US-based schools][6] granting bachelor or advanced degrees and ran an automated check of popular mobile web addresses against it. Because of this my directory is seriously lacking in international schools. So take this survey as a primarily US-centric view of the mobile higher ed world. For the international folks checking this out… sorry.

Time to run through the questions I wanted answered…

## How many  institutional mobile websites are there and how does that number compare to the overall number of higher ed websites?

Based on my initial list of **1,789** schools it looks like only **160** or **9%** of schools have an institutional mobile website. Mark Greenfield ([@markgr][7]) pointed me at the Carnegie Classification which currently tallies a whopping 4,600+ higher ed institutions. Sadly, it doesn't look like I can easily get web addresses for all of them to test against.

<img title="charts.001.fix" src="/wp-content/uploads/2011/02/charts.001.fix_.png" alt=""  />

## What solutions did schools use to develop their mobile websites?

This is a tricky number to come up with because I don't really know what they used. Because of that there is a very large "Homegrown/Unknown" bucket with **71%** of the total. I do think it's fair to say that those schools attempting to get a mobile presence setup are going on their own. Blackboard was the most obvious vendor product and the largest single solution used with **15%** of the total. [Mobile Web OSP][9] was the second most used solution at **8%** and MIT derivatives other than Mobile Web OSP rounded out at **6%**.

One interesting thing to note about Blackboard and the mobile web is that a school like Stanford has a [Blackboard-based mobile site][10] and a [separate, homegrown mobile website][11]. The Stanford home page redirects to the latter so it's not like it's some dead, forgotten website.

<img title="charts.002" src="/wp-content/uploads/2011/01/charts.002.png" alt="" />

## What are the popular types of content?

Looking at the results I can't say I'm too surprised. News (**on 87% if the schools surveyed**), events (**78%**), and directory (**76%**) are probably the easiest sections to get a mobile version up and running for. I'm a little bit disappointed by the showing for maps (**65%**). If you're going to develop a mobile solution a good map is a must. I do understand the difficulty in getting data but mobile is all about location. A few things that I expect to work into our own mobile site based on the results are: a note about our text alert system on our mobile emergency page, higher visibility for links to our email platforms, better search feature, and contact us and request info forms. All are low on the list but I think they do offer real value. This chart shows all sections that showed up on 10 or more higher ed mobile websites.

<img title="charts.004" src="/wp-content/uploads/2011/01/charts.004.png" alt="" />

## What web address should we use?

I would actually suggest to use all of these. At WVU we don't but I'm going to remedy that. Also, a few schools answer to multiple hostnames but I just included the first one I found.

<img title="charts.005" src="/wp-content/uploads/2011/01/charts.005.png" alt="" />

## For design layout which is more popular, grid or list?

There are basically two design layouts at this point in the higher ed world. The grid (**31%**) (*e.g. like the iPhone homescreen*) and the list (**69%**) where items are just stacked on top of one another. I personally prefer the grid layout. Shocker, I know.

<img title="charts.006" src="/wp-content/uploads/2011/01/charts.006.png" alt="" />

## How many device classes do these sites support?

One of the main features of Mobile Web OSP, Molly Project, and the MIT derivative frameworks is support to give custom layouts based on requesting device. In order to organize these layouts we refer to them as device classes (*e.g. iPhone and Android in one device class and the Motorola RAZR and other features phones in another*). I'm a little disappointed that their aren't more schools attempting to support at least two device classes (**31%**) but I guess that's understandable.

<img title="charts.003" src="/wp-content/uploads/2011/01/charts.003.png" alt="" />

By the way, the most obvious single layout was one for the iPhone at 320px. Wish I had a separate question that categorized the designs I saw.

## Do schools redirect mobile home page traffic to their mobile site?

I really think schools should do this. For the casual user trying to find mobile information their first stop is going to be the home page. Make it blindingly obvious where they can get mobile-optimized information by redirecting them. It'll be your biggest form of advertising for your mobile site. Always give them an opt out though.

<img title="charts.007" src="/wp-content/uploads/2011/01/charts.007.png" alt="" />

## Do schools provide a link *to* the mobile page on the home page?

We don't do this but I think it may be time to change that up. I was surprised by how many did.

<img title="charts.008" src="/wp-content/uploads/2011/01/charts.008.png" alt="" />

## Do schools provide a link *from* their mobile page to the home page?

This is a no brainer to do though it's surprising only **63%** do so…

<img title="charts.009" src="/wp-content/uploads/2011/01/charts.009.png" alt="" />

## How "heavy" are higher ed mobile websites?

I was curious to see what how well schools had optimized the main landing page of their mobile sites. With JavaScript mobile-focused libraries on the way (*e.g. jQuery Mobile*) I would expect the weight of these sites to increase substantially over the next year. For example, WVU's mobile website weight with jQuery and jQTouch is ~334K. Pretty hefty. The largest higher ed mobile site I came across was **1.9MB**. The smallest was **4K**. For those schools that had multiple device classes I used the heavier number. Also, you guys with Blackboard mobile websites may want to ask why jQuery is used. **89%** of a typical Blackboard mobile website's weight is simply jQuery. Those sites aren't terribly heavy as it stands but it seems an odd inclusion.

<img title="charts.010" src="/wp-content/uploads/2011/01/charts.010.png" alt="" />

By the way, weight isn't the only issue when thinking about optimizing performance of a mobile website. You also have to think about how many requests are being made back to the server. If you can merge stylesheets and javascript files into bigger files you should think about it. [Minify][21] is a good project for this kind of feature. You can also embed images in CSS using [data URIs][22] instead of linking to them. Unfortunately when I did the survey I didn't think about measuring the number of GET requests…

## Use a JavaScript library? If so, which one?

This is a bit of a moving target with jQuery Mobile pushing towards a stable release but interesting to me nonetheless. Yes, a JavaScript library is sort of the antithesis of a lean, mean mobile site but they'll be used more and more.

<img title="charts.011" src="/wp-content/uploads/2011/01/charts.011.png" alt="" />

## Which map solution is most popular?

I'm totally focused on the campus map. If you asked me which mobile content you should be developing I'd list campus map as #1 and trail it with a few exclamation points. Everything mobile comes back to location. I know I'm repeating myself but I figure no one has actually *read* this far by now.

<img title="charts.012" src="/wp-content/uploads/2011/01/charts.012.png" alt="" />]

## What do schools used for mobile analytics?

With, what I expect to be, a strong usage of Google Analytics in higher education I was curious if schools went with the mobile version or regular version of the analytics tracker. I was also curious if schools used another service. It appears that more schools don't use a 3rd party to track their analytics for their mobile site than do use a 3rd party service. And the regular JavaScript version of Google Analytics absolutely crushes the mobile-specific version. Most of the uses of the mobile-specific version come from folks running more than one device class.

<img title="charts.013" src="/wp-content/uploads/2011/01/charts.013.png" alt="" />

One thing to note about mobile stats, we rely on both internal stats recorded in our database for the site as well as Google Analytics. Internal stats are most accurate but don't come with the depth of Google Analytics.

## Are any schools using advanced features like geolocation?

Last on my list of questions are the serious technical issues like support for the HTML [Geolocation API][26]. While geolocation has been addressed by a couple of schools things like the local database or local/session storage are schools running Mobile Web OSP 2.0. I only checked media queries for the mobile sites and not home pages. I just didn't have the stomach to review 1,789 pages by hand though I could have spent some time and figured out an automated way to look at it.

<img title="charts.014" src="/wp-content/uploads/2011/01/charts.014.png" alt="" />

## Conclusion

Hopefully these numbers shed some light on the current state of the technical implementations of mobile websites in higher ed. It was a really tough slog to get all the data together and I don't relish the idea of doing it again but it definitely helped me understand what might be useful to push in the future. I hope it helps you too.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/?p=177
 [2]: http://twitter.com/karinejoly/
 [3]: http://higheredanalytics.com/mobile
 [4]: http://www.dmolsen.com/mobile-in-higher-ed/?page_id=43
 [5]: http://wvutoday.mobiexp.wvu.edu/
 [6]: http://www.clas.ufl.edu/au/
 [7]: http://twitter.com/markgr/
 [8]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/02/charts.001.fix_.png
 [9]: http://mobilewebosp.pbworks.com/
 [10]: http://m.stanford.edu/
 [11]: http://stanford.edu/m/
 [12]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.002.png
 [13]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.004.png
 [14]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.005.png
 [15]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.006.png
 [16]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.003.png
 [17]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.007.png
 [18]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.008.png
 [19]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.009.png
 [20]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.010.png
 [21]: http://code.google.com/p/minify/
 [22]: http://css-tricks.com/data-uris/
 [23]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.011.png
 [24]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.012.png
 [25]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.013.png
 [26]: http://dev.w3.org/geo/api/spec-source.html
 [27]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/01/charts.014.png