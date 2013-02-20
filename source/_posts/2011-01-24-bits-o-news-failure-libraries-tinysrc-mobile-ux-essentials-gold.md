---
title: 'Bits o&#8217; News: Failure, Libraries, tinySrc, Mobile UX Essentials &#038; Gold'
author: Dave Olsen
layout: post
permalink: /2011/01/24/bits-o-news-failure-libraries-tinysrc-mobile-ux-essentials-gold
categories:
  - General
  - Presentations
  - Tools
tags:
  - award
  - chronicle of higher ed
  - edupunk
  - failure
  - hinman
  - karinejoly
  - libraries
  - library
  - presentation
  - tinysrc
  - user interface
  - ux
  - wvu mobile web
---
So a quick round-up of some interesting articles and tools I've seen recently.

## The Chronicle of Higher Ed: As the Web Goes Mobile, Colleges Fail to Keep Up

This article from The Chronicle of Higher Ed, [As the Web Goes Mobile, Colleges Fail to Keep Up][1], has been making the rounds today on Twitter. My initial reaction to the story was that it was very negative. On re-reading it maybe the author did a good job capturing what's currently the norm in higher education. Obviously, I think there's cause for a bit of hope and I'm definitely excited about what's possible for higher ed in this space. The one thing that really struck me is that "mobile" can mean so much. To me it's about delivering central services like a calendar and campus map. To one commenter they're really focused on the academics and yet another commenter is focused on it's use for marketing. No wonder colleges are "failing" when there's such a diverse set of goals to achieve! Suffice it to say, there's a lot of space for us to evolve and their's nothing wrong starting small. Another, older article that's in a similar vein to this one is [Websites Gone Mobile][2] by Karine Joly ([@karinejoly][3]).

## Edupunk goes mobile: Mobile library sites with zero budget

One area (*see, lots to do in higher ed!*) that I'm interested in is how mobile usage picks up with respect to libraries. At West Virginia University our libraries department has their own [mobile website][4] (*I wasn't involved at all*). The article "[Edupunk goes mobile: Mobile library sites with zero budget][5]" does a nice job covering the current state of mobile in libraries and some of the issues they face. It also offers some solutions. I'm not sure how well they'll work because I don't think they tie directly back into real use cases (*e.g. mobile front-end for the the catalog*) but they're good things to keep in mind. As much as I sometimes struggle with it third parties offer some really interesting tools to get up and running quickly.

## tinySrc: Quick Way to Re-size Images for Mobile

Speaking of quality third party tools, if you have a need to resize images based on requesting device you should think about checking out [tinySrc][6]. It's free and works auto-magically. Basically, in your image tag being served to a mobile device you include tinySrc as the source for the image and reference the final image you want resized. For example:

> `<strong>http://i.tinysrc.mobi/</strong>http://mysite.com/myimage.png`

Then, based on the requesting device the image will be modified accordingly. If you want to push out mobile-friendly images with your press releases this might be a good way of accomplishing that.

## Presentation: Mobile UX Essentials

This is definitely one presentation you should check out if you're into designing mobile interfaces. It was given by Rachel Hinman ([@hinman][7]) recently and it absolutely rocks.

<div class="slideshare-container">
<div class="slideshare-embed">
<iframe src="http://www.slideshare.net/slideshow/embed_code/6643654?rel=0" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC;border-width:1px 1px 0;margin-bottom:5px" allowfullscreen webkitallowfullscreen mozallowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="http://www.slideshare.net/Rachel_Hinman/mobile-ux-essentials-6643654" title="Mobile UX Essentials - Silicon Valley IxDA/BayChi" target="_blank">Mobile UX Essentials - Silicon Valley IxDA/BayChi</a> </strong> from <strong><a href="http://www.slideshare.net/Rachel_Hinman" target="_blank">Rachel Hinman</a></strong> </div>
</div>
</div>

## WVU University Relations/Web takes CASE honors for mobile website

I do have to take a moment to brag a little bit. Recently [WVU Mobile Web][8], which I work on, was recognized by the Council for Advancement and Support of Education (CASE) District II by receiving the 2011 Accolades gold award for Best Practices in Communications. The [article from wvutoday][9] does a good job of giving background on the site and award.

 [1]: http://chronicle.com/article/Colleges-Search-for-Their/126016/
 [2]: http://universitybusiness.com/viewarticle.aspx?articleid=1515
 [3]: http://twitter.com/karinejoly/
 [4]: http://m.lib.wvu.edu/
 [5]: http://tiffinianne.wordpress.com/2011/01/22/8/
 [6]: http://tinysrc.net/
 [7]: http://twitter.com/Hinman
 [8]: http://m.wvu.edu/
 [9]: http://wvutoday.wvu.edu/n/2011/01/20/wvu-university-relations-web-takes-case-honors-for-mobile-website