---
title: Developing a Progressive Mobile Strategy
author: Dave Olsen
layout: post
permalink: /2010/10/05/developing-a-progressive-mobile-strategy
categories:
  - General
tags:
  - d4m2010
  - globalmoxie
  - grigs
  - lukew
  - mobile web
  - native
  - progressive
  - strategy
---
***Editor's note: **I [presented a talk][1] on June 27, 2011 at HighEdWeb Rochester which covers this topic in more depth and is based on some of my more recent thinking on this topic… though the content below is still very much relevant.*

*Two weeks ago  I attended the [Design for Mobile][2] conference in Chicago. My brain is still recovering from so much great content in so little time. This article is based on one of the big ideas I took away from the conference.*

To me, the mobile web versus native app debate is **dead**. I think that should be the case for most large, established organizations trying to deliver mobile services to users<sup><a href="#bestbuy">1</a></sup>. The question is no longer "*Which, between mobile web or native, do we develop for?*" The question now is "*How do we develop an architecture to handle <span style="text-decoration: underline;">both</span> mobile web and native now and then the mobile devices of the future?*" With the latter question in mind let me suggest a progressive mobile strategy.

## What I Mean by "Progressive Mobile Strategy"

A progressive mobile strategy, much like [progressive enhancement][3] on which it is based, is **a strategy focused on offering very basic interfaces to information from which other services can pull and then progressively create more complex interactions based on device type and device reach**. The mobile market (*both OS and device*) is moving too fast to pick a winner to focus your energies on so the best you can do is try to prepare for all eventualities and develop "broadest reach" solutions.

I feel a proper progressive mobile strategy would see the following implementation path:

<img title="progressive_mobile" src="/wp-content/uploads/2010/10/progressive_mobile-e1286301645803.png" alt="" />

Within the mobile web and native categories you'd also want to implement progressive solutions. What's the point of focusing on mobile web if you're only going to create the yummy HTML5 & CSS3 experience that only works on the absolutely bleeding edge devices? Also, you don't necessarily *need* to have the APIs in place before executing your mobile solutions. You just have to realize that, to be able to properly extend and make your life easier in the future, APIs are going to have to be created at some point. Trust me, it's awkward if you have to go back and retrofit.

## **APIs: Create Once, Publish Everywhere**

The most important element in creating an architecture that will handle the future of mobile is to **create as many APIs into your data as possible**. Many of the web applications that we're currently developing in [University Relations – Web][5] at [West Virginia University][6] utilize an API as the data source for all the various views be they desktop web, mobile web, or our native iOS app. The notion of **strongly separating logic from presentation** has been around for a long while now so I'm not proposing anything revolutionary here (*XML-RPC/SOAP anyone?*). For us, this separation has been of little interest as we weren't integrating systems or offering any other views other than desktop web. As we've moved into mobile we've realized it's going to become more and more important to implement this clear separation.

A good example of this type of separation is NPR's content management pipeline. Focus on the "presentation layer" to get an idea of all the various things they're attempting to support.

<img title="npr_architecture_diagram" src="/wp-content/uploads/2010/09/npr_architecture_diagram-e1285643694938.jpg" border="1" alt=""  />

From APIs I think mobile web is the next logical step in implementing a progressive mobile strategy…

## **Why Mobile Web Before Native?**

To paraphrase Jason Grigsby<sup><a href="#grigs">2</a></sup> ([@grigs][8]):

> *Not every mobile device will have your app on it but every mobile device will have a browser.*

This, to me, is the biggest selling point for going mobile web first. From the latest smartphones to several-years-old feature phones most devices are now internet-capable. Do all types of devices use the mobile web equally? No, but that doesn't mean you shouldn't provide for them or ignore the reach of the mobile web. It's this long reach of mobile web that makes it the obvious first step in deploying a mobile solution. Mobile web allows you to **write once for many devices**.

But, while I maintain a [mobile web-focused framework][9], mobile web is not the be all and end all for mobile development. Native offers an institution the possibility of building a better, more focused experience for a user compared to mobile web (*not to mention the small issue of *[*mobile web and discoverability*][10]). I do think native apps take a whole different skill set from web and mobile web development. That is why I'm not sure they're the best fit for institutions unless you're pretty positive you'll be holding onto the talent you'll need to continue to build and develop these solutions. Native does offer some interesting possibilities.

## Future Proof?

Hopefully by implementing a progressive mobile strategy you're future proofing your mobile development efforts. As new technology comes online you should be able to react more quickly. This strategy is not only for mobile but should allow you to easily develop for other outlets like **digital signage or upcoming TV-based interfaces**. But we'll see. A lot can change in six months.

### Addendum: API First

I didn't realize that Josh Clark ([@globalmoxie][11]) touched on this in a recent presentation entitled, [Going Native: The Anthropology of Mobile Apps][12]. Just skip to slide #44 and make sure you check out the notes below the slides. API First is a play on Mobile First which is championed by Luke Wroblewski ([@lukew][13]). The cross-pollination of ideas out of [Design for Mobile][2] is pretty cool to see. I'll have to try to make it back next year.

<sup><a name="best-buy"></a>1</sup> – there is a great example of a company using a progressive mobile strategy in the [*Why Best Loves Mobile* video][14].

<sup><a name="grigs"></a>2</sup> – check out Jason's Design for Mobile 2010 presentation, "[*Get me a Mobile Strategy or You're FIRED!*][15]" too.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/2011/06/27/presentation-developing-a-progressive-mobile-strategy/
 [2]: http://www.design4mobile.com/
 [3]: http://en.wikipedia.org/wiki/Progressive_enhancement
 [4]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/10/progressive_mobile.png
 [5]: http://universityrelations.wvu.edu/
 [6]: http://www.wvu.edu/
 [7]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/09/npr_architecture_diagram.jpg
 [8]: http://twitter.com/grigs/
 [9]: http://mobilewebosp.pbworks.com/
 [10]: http://www.dmolsen.com/mobile-in-higher-ed/?p=14
 [11]: http://twitter.com/globalmoxie
 [12]: http://www.slideshare.net/joshclark/going-native-the-anthropology-of-native-apps
 [13]: http://twitter.com/lukew
 [14]: http://www.dmolsen.com/mobile-in-higher-ed/?p=125
 [15]: http://www.slideshare.net/grigs/get-me-a-mobile-strategy-or-youre-fired