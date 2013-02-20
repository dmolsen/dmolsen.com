---
title: 'Displaying Facebook Fan &#038; Twitter Follower Counts on a Web Page'
author: Dave Olsen
layout: post
permalink: /2010/09/29/displaying-facebook-fan-twitter-follower-counts-on-a-web-page
categories:
  - Tools
tags:
  - facebook
  - javascript
  - jquery
  - Twitter
---
We have an upcoming project ([now launched][1]) where we wanted to show the latest, greatest Facebook fan and Twitter follower counts for our official presences on those services. I put together some really simple JavaScript that does just that and I'm sure others could use it as well. As always the code requires [jQuery][2]. You should be able to copy the [example code][3] into an empty text file, swap in your the usernames of your official accounts, and go from there. If you have any questions about the code please drop me a line in the comments. By the way, there is no error handling on the JSONP requests simply because I guess jQuery has decided JSONP requests won't generate any.

So [check out the code][3] on gist.github. Feel free to fork it, comment on it, modify it, or whatever. You can also see the code in action on the [Connect with WVU website][1].

**Updated October 6, 2010: **Added support to automatically insert commas. The counts now look a lot better.

**Updated November 16, 2010: **A user posted a simple implementation of this concept [written in PHP][4].

**Updated December 29, 2010:** Fixed a bug in the Facebook fan count because Facebook changed the name of the count element from ‘fan_count' to ‘likes'. [Latest, greatest code][3].

 [1]: http://connect.wvu.edu/
 [2]: http://jquery.com/
 [3]: http://gist.github.com/599243
 [4]: http://dev.firsttube.com/fans-followers.php