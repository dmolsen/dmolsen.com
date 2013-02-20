---
title: 'The Cautionary Tale of &#8220;The Expert Has Spoken:&#8221; Jakob Nielsen &#038; the Mobile Site Debate'
author: Dave Olsen
layout: post
permalink: /2012/05/23/the-cautionary-tale-of-the-expert-has-spoken-jakob-nielsen-the-mobile-site-debate
categories:
  - General
tags:
  - content strategy
  - globalmoxie
  - jakob nielsen
  - mobile strategy
  - netmag
  - responsive web design
  - rwd
  - strategy
---
In higher education we really like "best practices." We like solutions that are proven and that we can easily implement as we dip our toes into new technologies. I've watched this happen with social media and I'm now experiencing it with mobile. Part of the reason we try to find and follow "best practices" is our need to get the most bang for the buck. Another part of it is the fact that many of us wear so many hats that we *need* to rely on "experts." Lastly, I think another part of it is that for so long we've seen our industry as behind-the-times that, yet again, we must be behind with this technology and therefore there must be guidelines to follow; things we can follow to "get it right." Here's what I've learned about mobile though…

> **Everyone, in every industry** is figuring this out at the same time, it's fucking messy, and, for the most part, anyone spouting off about any particular solution as being "the right way" is full of it. And the reason they're full of it? One size doesn't fit all (*no matter what it might say on the package*).

This is why I get peeved when people we should all hold in high-esteem drop blog posts with overly pithy summaries that actually end-up muddying the waters that much more.

In early April 2012 usability expert [Jakob Nielsen][1] turned his attention to mobile and penned a piece entitled, *[Mobile Site vs Full Site][2]*. The summary for the article follows:

> Good mobile user experience requires a different design than what's needed to satisfy desktop users. Two designs, two sites, and cross-linking to make it all work.

The very first and, to quote him, "*very clear*" guideline that Jakob lists for mobile-optimized websites is "**Build a separate mobile-optimized site." ***[Jakob's emphasis]* Now the article is essentially correct in highlighting that the rules for mobile design can be different than desktop design and that most of today's websites don't properly address these issues. Josh Clark's ([@globalmoxie][3]) [rebuttal][4] is very much worth reading and others [picked apart the salient points][5] at the time the original article was written so I won't re-hash them. The thing that bothered me then, and does again in light of his equally good and bad article *[Repurposing vs. Optimized Design][6] (another [good overview][7] so I won't re-hash it either)*, is the definitive stance regarding an overall solution that Jakob takes when, in fact, he's really only suggesting this "usability tip" for a particular subset of sites or use cases.

In a follow-up article on .net magazine, "[Nielsen Responds to Mobile Criticism][8]," Nielsen offers clarification on this original article and answers the following question that is based on one of the primary arguments used against his original post:

> **.net: The strategy of forking content for separate sites has been described as "a content strategy nightmare" – it's too hard to maintain and will result in inferior experience for users.**
> 
> JN: I would assume that most *industrial-scale sites* *[emphasis mine]* would be generated from a single back-end product database and content management system, with the different designs represented by templates and rules about what information goes into what version.

Later, in answer to the same question, he says:

> Many companies and government agencies have products and information that don't speak much to the mobile use case, and they can usually get away with having a single website that's optimised for desktop use but with some adaptations to make it reasonably accessible on mobile devices.

So Jakob's first, "*very clear*" guideline is now not so clear. It gets worse:

> **.net: Multiple URLs for a single piece of content is often thought of as a bad idea.**
> 
> JN:There are at least three different ways of implementing different user interfaces for different devices:
> 
> 1.  Each version lives at a different URL.
> 2.  The same URL serves up different versions, depending on the device used to request the page.
> 3.  The same code is transmitted to all devices, and the client side transforms this into the different designs, using responsive design.
> 
> As long as each user sees the appropriate design, the choice between these implementation options should be an engineering decision and not a usability decision.
> 
> **.net: Why have you made no mention of using Responsive Design?**
> 
> JN: Because I was writing about user experience, *not implementation * *[emphasis mine]*. As mentioned above, responsive design is one of the ways to achieve different user interfaces for different devices.

Suggesting "*Build a separate mobile-optimized site,*" again his very first guideline, **screams** implementation. So, based on the .net Magazine clarifications, we should revise his original guideline to be "*If you're a very large, centralized organization with mobile use cases it behooves you to do… something mobile-friendly*."

And the kicker to all that? If you just read Jakob's material and weren't hooked into the people who were involved in the backlash you may never have found the clarification. You may have implemented his suggestions as a "best practice" (*I mean, it's Jakob freakin' Nielsen*), found a vendor, spent some money and… been stuck with a site and a [mobile strategy that didn't fit your content][9], your internal processes, or real use cases as the web on mobile evolves into the ["just in time" internet][10].

Figuring out what mobile will mean to your institution requires time spent thinking critically about goals, technology, and then trying to understand how these new tools can match up to your existing processes and, honestly, the culture you already have at your institution. To succeed with mobile you'll have to be willing to be critical, to fail, to reconfigure, to iterate, to learn and to develop your very own "best practices." Unfortunately, there is no such thing as a turn-key solution or list of tips that will help you easily guide your institution into the new age. No matter what Jakob, or I, might say.

*I understand that this article can and probably will come across as the pot calling the kettle black. I take [strong stances myself][11]. I do hope that I appropriately add caveats to what I write but maybe I don't. When I talk to people about mobile and they question how we've implemented and learned so much I tell them something my father told me a long time ago about what he told students he was teaching in a brand-new math class, "I'm only a chapter ahead of you." Seriously, all of this stuff is a moving target.*

 [1]: http://www.useit.com/jakob/
 [2]: http://www.useit.com/alertbox/mobile-vs-full-sites.html
 [3]: http://twitter.com/globalmoxie
 [4]: http://www.netmagazine.com/opinions/nielsen-wrong-mobile
 [5]: http://www.netmagazine.com/news/designers-respond-nielsen-mobile-121892
 [6]: http://www.useit.com/alertbox/repurposing.html
 [7]: http://boagworld.com/mobile-web/separate-mobile-site-vs-responsive-design/
 [8]: http://www.netmagazine.com/interviews/nielsen-responds-mobile-criticism
 [9]: http://www.dmolsen.com/mobile-in-higher-ed/2011/11/22/mobile-strategy-is-dead-long-live-content-strategy/
 [10]: http://www.slideshare.net/yiibu/reset-the-web
 [11]: http://www.dmolsen.com/mobile-in-higher-ed/2012/02/21/ress-and-the-evolution-of-responsive-web-design/