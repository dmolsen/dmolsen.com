---
layout: page
title: "My Projects"
date: 2013-02-15 14:52
---

In the interest of giving back I have open sourced some of the code I've worked on over the years. My primary languages for these projects has been PHP and JavaScript.

## My Active Open Source Projects

The following projects are under active development. While a few may not have commits recently I'm definitely thinking about them a lot:

*   **Detector** - [Detector][29] is a simple, PHP- and JavaScript-based feature- and browser-detection library. Detector gives server-side developers information about what type of device may be requesting their content as well as the HTML5 & CSS3 features a requesting browser may or may not support. With Detector a developer can serve the appropriate markup, stylesheets, and JavaScript to a requesting browser without being completely dependent on a browser-detection library being up-to-date nor completely dependent on a front-end-only script loader. The [code is available on GitHub][30].
*   **ua-parser-php** - ua-parser-php is a PHP-based pseudo-port of the [ua-parser][31] project. It is now included as a library inside the [official ua-parser repository on GitHub][32]. ua-parser-php utilizes the user agents regex YAML file from ua-parser but otherwise creates it's own properties for use in projects. ua-parser-php was created as a new browser-detection library for the browser- and feature-detection library [Detector][30]. If you want, you can [test ua-parser-php][33] with your browser.
*   **lazyBlock** – a [proof-of-concept][34] to show how developers/designers can conditionally load content in their responsive designs without relying on AJAX to do so. Content is included in the mark-up but is commented on. Based on user action or media queries the content is then uncommented and injected into the DOM. lazyBlock is designed to overcome some of the inherent problems with the inclusion of media in elements that have been hidden with `display: none`. There's also a [small demo][35].

## My Archived Open Source Projects

The following projects are still available but are no longer actively being worked on:

*   **Mobile Web OSP** - The [Mobile Web Open Source Project][4] (OSP) was initially developed during the summer of 2009 and is a fork of the [original v0.9 release][36] of the MIT Mobile Web project that can still be found on SourceForge. The project was updated in May 2010 with the [release of version 2.0][37]. It is a product designed to make it easier for higher education institutions to deliver mobile-optimized information and services. It helps deliver task-based content like maps, events, and directory information optimized for device "families."
*   **YouTubePlayer** – My [forked version][38] of the [original][39] by Anurag Mishra allows developers to easily access the [YouTube JavaScript Player API][40]. The focus of my fork was to add support for timed events. With this feature a developer can time events on a web page to  occur at certain parts of an embedded YouTube video. It was written for WVU's 2011 Holiday Card website.
*   **CSS3 Snowflakes** – A very simple combination of CSS3 & JavaScript to create snowflakes. It was written for WVU's 2011 Holiday Card website. There is a [simple demo][42] and the code is [available on GitHub][28].
*   **MQSugr** - [MQSugr][43] is a wrapper for [Modernizr.load][44] that provides some syntactic sugar for loading CSS and JavaScript files using media queries and browser features. MQSugr was created to help me learn more about JavaScript, media queries, file loading and Modernizr. There is no real world problem that it's meant to solve.
*   **Foursquare Statistics** - [This simple tool][45] was designed help higher ed institutions gauge interest/usage of foursquare on their campus. Simply provide a text file with a list of venues and the script will tell you total check-ins, top five venues, check-ins per venue, & total mayors for each venue.
*   **Popular Queries for GSA** - [Popular Queries for GSA][46] offers administrators of stand-alone Google Search Appliance boxes the ability to include in their layout, via a JavaScript include, a list of the previous days top queries. Administrators can also have reports of the top queries emailed to them. To prevent users from including inappropriate queries in the list, ‘Popular Queries for GSA' also includes the ability to censor queries. *Now deprecated because it only worked with version 4 of the GSA.*
*   **Textile Editor Helper **- My first open sourced project, Textile Editor Helper, no longer exists at it's original location but it does live on as a [fork on GitHub][47]. It serves as a WYSIWYM (*What You See Is What You Mark-up*) for textareas in CMSs that support Textile mark-up. It was developed to allow users with little technical knowledge to use our internal CMS, [slate][48].

## My Mobile-related Projects For West Virginia University

As a mobile dev I've completed my fair share of projects. Here are a few of the highlights:

*   [WVU Mobile Web][3] - Based on MIT's open sourced Mobile Web Project  the site was initially developed and launched in in one month. It's is designed to deliver essential information and services to students, faculty, and staff anytime, anywhere and is optimized for their mobile device of choice. It was "upgraded" in April 2010 to support jQTouch, a redesigned map interface, as well as the introduction of HTML5 features like (*now deprecated*) WebSQL.  The site averages over 5,000 page views a day and has served over 2 million pages since launch.
*   [Tournaments Website][23] - I built and deployed the mobile-focused Big East Tournaments site in a week and a half. The project was meant to provide a test bed for a different type of mobile design pattern that what I had done previously as well as stretching my limits with CSS3 and JavaScript. The big features of the site include a CSS3-based move & fade background slideshow, JavaScript & CSS3-based page animation, and integration with Facebook using the Graph API.
*   [Big East Campaign][24] – Launched in March 2010, it was my first attempt at developing a true mobile experience for users using the latest smartphones. Like all of my projects it will  still work on lower-end devices as well. Primary feature of the site is the card-like navigation that uses stills from the video that was also produced as part of this project. A lot more detail about the entire Big East Campaign project [is available in this blog post][25].
*   **2011 Holiday Card** *(no longer online)* - This was the first responsive design that I worked on. After I sketched out the project idea a co-worker did most of the design work. I put together all of the JavaScript that powers the site (*e.g. the [page events synced to the video][27]*) as well as all of the CSS animations (*e.g. [snowflakes][28], sparkles, clouds*). This site was put together in about a week. The design and functionality is meant to reflect the events in the video and was my first tightly-knit web & video project.

[3]: http://m.wvu.edu/
[4]: http://mobilewebosp.pbworks.com/
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