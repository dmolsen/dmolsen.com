---
title: The State of Mobile Web OSP
author: Dave Olsen
layout: post
permalink: /2010/11/17/the-state-of-mobile-web-osp
categories:
  - Mobile Web OSP
tags:
  - device detection
  - jquery mobile
  - mdb2
  - mobile web osp
  - mssql
  - mysql
  - postgresql
  - sencha
  - sqlite
  - wurfl
---
So with [Mobile Web OSP][1] now (*roughly*) one year old I figured it'd be a good time to review the project. For those who are new to this blog, [Mobile Web OSP][1] is a PHP-based framework that I maintain. It is designed to make it easier for universities and colleges to deliver mobile portals. It has been [open sourced][2] under the MIT license. The code for my project is a fork of v0.9 of MIT's original MIT Mobile Web product. I covered [why I created the fork][3] in an earlier post. I've also have a "[year in review][4]" post so you can see our mobile traffic and another post showing a good [case study][5] for mobile in higher ed.

## Overview

The project has been a greater success than I could have imagined. [Twelve schools (*that I know of*) have launched mobile portals][6] based on version 1 and version 2 of the project. Developers from Colorado College and Miami University have provided great notes on bugs. Southeast Missouri State University even contributed a module for others to use. The project has [35 people following it on GitHub][7] along with some forks and I've given two webinars on the project for [Higher Ed Experts][8] (you can still grab the [on-demand version of the webinar][9]). So overall not a bad run for the first year of the project but now it's time to look forward to the upcoming year…

## The Next Release: v2.5

I'm actively working on the next release which I'm currently marking as Mobile Web OSP v2.5. I go into more depth on each of these issues further down in the post but this release will have:

*   Proper multiple database support including MySQL using MDB2
*   "Where am I?" and "What's near me?" features for the Campus Map on advanced WebKit devices
*   The weather module up-to-date with v2.x templating
*   An easier installation process

If you want to follow along on how this release is going just check out GitHub.

## MDB2 & MySQL Support

When I started my fork of the project I didn't have many options when it came to choosing a database and, most importantly, those options didn't include MySQL. In order to keep things simple and to get the project moving as fast as I possibly could I chose to use SQLite. At the time it made a lot of sense. The feedback that I've gotten from other schools since then, though, is that they would prefer to use a more traditional RDBMS a la MySQL or PostgreSQL. A number of schools have even hacked in this support (or fixed my broken implementation depending on your point of view). In order to make the project more attractive to schools I've decided to add in MySQL support by adding support for [MDB2][10]. Hopefully this means that the project will not only support MySQL but schools will also be able to use PostgreSQL or MSSQL. If you want to keep track of this effort check out the [MDB2 branch][11] of the project. Hopefully it's rolled back into the master branch pretty quickly.

## Location, Location, Location

One feature that I'm having to add for our use (*and one of the main reasons I'm adding proper MySQL support now*) is a way for users to show where they're at on the campus map as well as query what's nearby. Creating a robust campus map module that includes those features as well as easily links to other data (*e.g. looking at a dining hall will give you a link to the dining menu*) is one of my main near-term goals with the project. I also hope to sync some data from foursquare with the campus map as well.

## Ease of Installation

I'm not sure how much of a problem this is for others but as I work on the project this has become a major headache. All the data.copy.inc.php files are great for configuration but a pain to set-up each time. If you check out the [master branch of the project][12] you'll notice that there is now a setup.php file in the root. While it still needs some final testing installation in the future should be as simple as running that script and answering a couple of easy questions. That's the hope at least

So what are the other issues out there that I'm thinking about with Mobile Web OSP?

## Collaboration

I'm open to collaboration. Serious. If you have suggestions, bug fixes, or new modules please let me know and we'll find a way to work together. Probably the easiest way to collaborate is to fork the project on GitHub, makes your changes and request that your changes be merged back into the parent project.

I really don't want or need this to be a one man show.

## Device Detection & Classification

The original MIT mobile framework used WURFL to detect and classify devices. At the time I created my fork it just didn't seem practical to continue to use that method when 1) classification seemed to consist of iOS devices vs everything else and 2) the WURFL code was GPLed and I wanted to release the code under the MIT license. As Android has gained in popularity and BlackBerry has released better/bigger devices it's getting difficult to keep up with properly classifying devices. I also don't have a set of hardware to properly test features. At the moment I'm a little unsure of what solution I'll pursue. In my road map I talk about looking at support for [Device Atlas][13]… but really I'm not sure. If folks have feedback on where the project should go in this department please feel free to drop a line in the comments.

## JavaScript Mobile Framework Support

One of the big features for version 2 of the project was the addition of [jQTouch][14] support for advanced WebKit devices. This is another "it made sense at the time"-features. Unfortunately time has moved on as well as the lead developer for that project. While [jQuery Mobile][15] isn't fully baked yet I would expect that Mobile Web OSP will move to it once it goes gold. Why not [Sencha Touch][16]? The implementation of Sencha Touch would require another deep guts architectural change and that makes me queasy. jQuery Mobile is implemented in much the same way as jQTouch so hopefully it won't be such a big change (*fingers crossed & knock on wood*).

## Conclusion

I'm sure I've left a lot of questions regarding the state of the project unanswered. This post was based on the pressing issues that I've been working to address as well as the few questions I received based on an earlier post. If you have any other questions please submit a comment so I can answer. Maybe others have the same question.

## Updates

Since I originally published this article I have posted a few more articles regarding work that I've been doing to implement some of the changes I talked about above. These articles are:

*   [Proposal: Content Adapters for Mobile Web OSP][17]
*   [Current Status of Mobile Web OSP 2.5][18]
*   [Proposal: Federated Search for Mobile Web OSP][19]
*   [Deep Links for Mobile Web OSP][20]

 [1]: http://mobilewebosp.pbworks.com/
 [2]: http://github.com/dmolsen/MIT-Mobile-Web/
 [3]: http://www.dmolsen.com/mobile-in-higher-ed/?p=63
 [4]: http://www.dmolsen.com/mobile-in-higher-ed/?p=117
 [5]: http://www.dmolsen.com/mobile-in-higher-ed/?p=10
 [6]: http://mobilewebosp.pbworks.com/w/page/27924444/Schools-Using-This-Project
 [7]: https://github.com/dmolsen/MIT-Mobile-Web
 [8]: http://higheredexperts.com/edu/
 [9]: http://higheredexperts.com/edu/webinar/going-mobile/
 [10]: http://pear.php.net/package/MDB2/
 [11]: https://github.com/dmolsen/MIT-Mobile-Web/tree/mdb2
 [12]: https://github.com/dmolsen/MIT-Mobile-Web/tree/master
 [13]: http://deviceatlas.com/
 [14]: http://www.jqtouch.com/
 [15]: http://jquerymobile.com/
 [16]: http://www.sencha.com/products/touch/
 [17]: http://www.dmolsen.com/mobile-in-higher-ed/?p=154
 [18]: http://www.dmolsen.com/mobile-in-higher-ed/?p=157
 [19]: http://www.dmolsen.com/mobile-in-higher-ed/?p=159
 [20]: http://www.dmolsen.com/mobile-in-higher-ed/?p=167