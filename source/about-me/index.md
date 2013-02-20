---
title: About Me
author: Dave Olsen
layout: page
---
My name is Dave Olsen and I'm a programmer/project manager with [West Virginia University][1]. I specialize in delivering PHP- and Ruby on Rails-based solutions for our [University Relations][2] department. Since July 2009 I've been working on deploying a number of mobile solutions at WVU with the most robust being [WVU Mobile Web][3]. In an effort to help other institutions easily develop their own mobile solutions the code behind that site has been open sourced as [Mobile Web OSP][4].

### My Presentations

These are some of the presentations that I've given over the years. If the slidedeck is public I've listed it:

*   [*Everything You Know is not Quite Right Anymore*][5], HighEdWeb, Sep. 2012
*   *[The Future-Friendly Campus (Workshop Edition)][6]*, [HighEdWeb Arkansas][7], Jul. 2012
*   [*The Future-Friendly Campus*][8], [Penn State Web Conference][9], Jun. 2012
*   *[RESS: The Evolution of Responsive Web Design][10]*, [Refresh Pittsburgh][11], May 2012
*   *[Developing a Progressive Mobile Strategy][12]*, J. Boye Philadelphia 12 Conference, May 2012
*   *[The Future-Friendly Campus][13]*, .eduGuru Summit, Apr. 2012
*   *Higher Ed Mobile Summit*, HigherEdExperts webinar, Mar. 2012
*   *[Developing a Progressive Mobile Strategy][14]*, M3 Conference, Nov. 2011
*   *[Developing a Progressive Mobile Strategy][15], *Breaking Development Conference, Sep. 2011 (*[video][16]*)
*   **[Developing a Progressive Mobile Strategy][17]*, *HighEdWeb Rochester, Jun. 2011
*   *[Leveraging the Social Graph][18]*, Stamats SIMTech, Oct. 2010
*   *Going Mobile*, HigherEdExperts webinar, Nov. 2009 & Aug. 2010
*   **[Beyond the iPhone: Delivering Mobile Content & Services][19]*, *Stamats SIMTech, Nov. 2009

More of my slidedecks, like those given at on-campus events, [can be found on SlideShare][20]. If you're interested in having me speak at your event [drop me a line][21].

### My Published Work

I've written a chapter on optimization for mobile for Smashing Magazine's [The Mobile Book][22].

### My Mobile Projects

As a mobile dev I've completed my fair share of projects. Here are a few of the highlights:

*   [WVU Mobile Web][3] - Based on MIT's open sourced Mobile Web Project  the site was initially developed and launched in in one month. It's is designed to deliver essential information and services to students, faculty, and staff anytime, anywhere and is optimized for their mobile device of choice. It was "upgraded" in April 2010 to support jQTouch, a redesigned map interface, as well as the introduction of HTML5 features like (*now deprecated*) WebSQL.  The site averages over 5,000 page views a day and has served over 2 million pages since launch.
*   [Tournaments Website][23] - I built and deployed the mobile-focused Big East Tournaments site in a week and a half. The project was meant to provide a test bed for a different type of mobile design pattern that what I had done previously as well as stretching my limits with CSS3 and JavaScript. The big features of the site include a CSS3-based move & fade background slideshow, JavaScript & CSS3-based page animation, and integration with Facebook using the Graph API.
*   [Big East Campaign][24] – Launched in March 2010, it was my first attempt at developing a true mobile experience for users using the latest smartphones. Like all of my projects it will  still work on lower-end devices as well. Primary feature of the site is the card-like navigation that uses stills from the video that was also produced as part of this project. A lot more detail about the entire Big East Campaign project [is available in this blog post][25].
*   [2011 Holiday Card][26] - This was the first responsive design that I worked on. After I sketched out the project idea a co-worker did most of the design work. I put together all of the JavaScript that powers the site (*e.g. the [page events synced to the video][27]*) as well as all of the CSS animations (*e.g. [snowflakes][28], sparkles, clouds*). This site was put together in about a week. The design and functionality is meant to reflect the events in the video and was my first tightly-knit web & video project.

### My Open Sourced Code

In the interest of giving back I have open sourced some of the code (*mainly PHP & JavaScript*) I've worked on over the years. Here is a sample:

*   **Detector** - [Detector][29] is a simple, PHP- and JavaScript-based feature- and browser-detection library. Detector gives server-side developers information about what type of device may be requesting their content as well as the HTML5 & CSS3 features a requesting browser may or may not support. With Detector a developer can serve the appropriate markup, stylesheets, and JavaScript to a requesting browser without being completely dependent on a browser-detection library being up-to-date nor completely dependent on a front-end-only script loader. The [code is available on GitHub][30].
*   **ua-parser-php** - ua-parser-php is a PHP-based pseudo-port of the [ua-parser][31] project. It is now included as a library inside the [official ua-parser repository on GitHub][32]. ua-parser-php utilizes the user agents regex YAML file from ua-parser but otherwise creates it's own properties for use in projects. ua-parser-php was created as a new browser-detection library for the browser- and feature-detection library [Detector][30]. If you want, you can [test ua-parser-php][33] with your browser.
*   **lazyBlock** – a [proof-of-concept][34] to show how developers/designers can conditionally load content in their responsive designs without relying on AJAX to do so. Content is included in the mark-up but is commented on. Based on user action or media queries the content is then uncommented and injected into the DOM. lazyBlock is designed to overcome some of the inherent problems with the inclusion of media in elements that have been hidden with `display: none`. There's also a [small demo][35].
*   **Mobile Web OSP** - The [Mobile Web Open Source Project][4] (OSP) was initially developed during the summer of 2009 and is a fork of the [original v0.9 release][36] of the MIT Mobile Web project that can still be found on SourceForge. The project was updated in May 2010 with the [release of version 2.0][37]. It is a product designed to make it easier for higher education institutions to deliver mobile-optimized information and services. It helps deliver task-based content like maps, events, and directory information optimized for device "families."
*   **YouTubePlayer** – My [forked version][38] of the [original][39] by Anurag Mishra allows developers to easily access the [YouTube JavaScript Player API][40]. The focus of my fork was to add support for timed events. With this feature a developer can time events on a web page to  occur at certain parts of an embedded YouTube video. It was written for [WVU's 2011 Holiday Card website][41].
*   **CSS3 Snowflakes** – A very simple combination of CSS3 & JavaScript to create snowflakes. It was written for [WVU's 2011 Holiday Card website][41]. There is a [simple demo][42] and the code is [available on GitHub][28].
*   **MQSugr** - [MQSugr][43] is a wrapper for [Modernizr.load][44] that provides some syntactic sugar for loading CSS and JavaScript files using media queries and browser features. MQSugr was created to help me learn more about JavaScript, media queries, file loading and Modernizr. There is no real world problem that it's meant to solve.
*   **Foursquare Statistics** - [This simple tool][45] was designed help higher ed institutions gauge interest/usage of foursquare on their campus. Simply provide a text file with a list of venues and the script will tell you total check-ins, top five venues, check-ins per venue, & total mayors for each venue.
*   **Popular Queries for GSA** - ‘[Popular Queries for GSA][46]' offers administrators of stand-alone Google Search Appliance boxes the ability to include in their layout, via a JavaScript include, a list of the previous days top queries. Administrators can also have reports of the top queries emailed to them. To prevent users from including inappropriate queries in the list, ‘Popular Queries for GSA' also includes the ability to censor queries. *Now deprecated because it only worked with version 4 of the GSA.*
*   **Textile Editor Helper **- My first open sourced project, Textile Editor Helper, no longer exists at it's original location but it does live on as a [fork on GitHub][47]. It serves as a WYSIWYM (*What You See Is What You Mark-up*) for textareas in CMSs that support Textile mark-up. It was developed to allow users with little technical knowledge to use our internal CMS, [slate][48].

### My Social Networks

You can find me online in a lot of places:

*   [Facebook][49]
*   [Flickr][50]
*   [GitHub][51]
*   [Google+][52]
*   [LinkedIn][53]
*   [SlideShare][20]
*   [Speaker Deck][54]
*   [Twitter][55]

### Contact Me

Got a question for me or some feedback? Hit up the [contact form][56] or [mention me][55] on Twitter.

 [1]: http://www.wvu.edu/
 [2]: http://universityrelations.wvu.edu
 [3]: http://m.wvu.edu/
 [4]: http://mobilewebosp.pbworks.com/
 [5]: http://www.slideshare.net/dmolsenwvu/everything-you-know-is-not-quite-right-anymore-rethinking-best-practices-to-respond-to-the-future
 [6]: http://www.slideshare.net/dmolsenwvu/the-future-friendly-campus-workshop-edition
 [7]: http://hewebar.org/
 [8]: http://www.slideshare.net/dmolsenwvu/the-future-friendly-campus-12514902
 [9]: http://webconference.psu.edu/
 [10]: http://www.slideshare.net/dmolsenwvu/ress-an-evolution-of-responsive-web-design
 [11]: http://www.refreshpittsburgh.org/
 [12]: http://www.slideshare.net/dmolsenwvu/developing-a-progressive-mobile-strategy-j-boye-edition
 [13]: http://speakerdeck.com/u/dmolsen/p/the-future-friendly-campus
 [14]: http://www.slideshare.net/dmolsenwvu/developing-a-progressive-mobile-strategy-m3-conf-version
 [15]: http://www.slideshare.net/dmolsenwvu/developing-a-progressive-mobile-strategy-bdconf-version
 [16]: http://t.co/2jqND3hH
 [17]: http://www.slideshare.net/dmolsenwvu/developing-a-progressive-mobile-strategy
 [18]: http://www.slideshare.net/dmolsenwvu/how-to-leverage-the-social-graph-with-facebook-platform
 [19]: http://www.slideshare.net/dmolsenwvu/beyond-the-iphone-delivering-mobile-content-services
 [20]: http://www.slideshare.net/dmolsenwvu/
 [21]: http://www.dmolsen.com/mobile-in-higher-ed/contact/
 [22]: http://www.the-mobile-book.com
 [23]: http://tournaments.wvu.edu/
 [24]: http://wvutoday.mobiexp.wvu.edu/
 [25]: http://www.dmolsen.com/mobile-in-higher-ed/2010/08/09/qr-codes-the-big-east-tournament-campaign/
 [26]: http://happyholidays.wvu.edu/
 [27]: http://www.dmolsen.com/mobile-in-higher-ed/2011/12/19/how-to-sync-web-page-events-with-embedded-youtube-videos/
 [28]: https://github.com/dmolsen/CSS3-Snowflakes
 [29]: http://detector.dmolsen.com
 [30]: https://github.com/dmolsen/Detector
 [31]: http://code.google.com/p/ua-parser/
 [32]: https://github.com/tobie/ua-parser
 [33]: http://uaparser.dmolsen.com/
 [34]: https://github.com/dmolsen/lazyBlock
 [35]: http://lazyblock.dmolsen.com
 [36]: http://sourceforge.net/projects/mitmobileweb/
 [37]: http://mobilewebosp.pbworks.com/Version-2-Release-Notes
 [38]: https://github.com/dmolsen/YoutubePlayer
 [39]: https://github.com/AnuragMishra/YoutubePlayer
 [40]: http://code.google.com/apis/youtube/js_api_reference.html
 [41]: http://happyholidays.wvu.edu
 [42]: http://dmolsen.com/css3-snowflakes/
 [43]: https://github.com/dmolsen/MQSugr
 [44]: http://www.modernizr.com/docs/#load
 [45]: https://github.com/dmolsen/Foursquare-Statistics
 [46]: https://github.com/dmolsen/popular-queries-for-gsa
 [47]: https://github.com/ryanfelton/textile-editor-helper
 [48]: http://slatecms.wvu.edu/

 [56]: http://www.dmolsen.com/mobile-in-higher-ed/?page_id=3