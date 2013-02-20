---
title: Tracking foursquare Usage on Your Campus
author: Dave Olsen
layout: post
permalink: /2010/10/29/tracking-foursquare-usage-on-your-campus
categories:
  - Tools
tags:
  - foursquare
  - git
  - php
  - Statistics
  - wvu
---
*I've also posted a related entry on *[*how I think foursquare will make a difference on your campus*][1]*.*

*This project & this related post were updated on **May 24, 2011**. I've updated the "requirements," "what you'll get," and "how to use it" sections of this post.*

As we roll out WVU's [official presence on foursquare][2] I was curious how we could track general usage statistics. foursquare provides a nice dashboard on a per venue basis but I wanted a quick & dirty way of finding out total numbers across all of the venues we have added (*105 of them!*). I spent a few hours putting together a foursquare statistics report generator. I've made it [available on GitHub][3] since I figured other schools might be interested in learning general usage numbers as well.

### Requirements

The requirements for using the package are:

*   PHP (*like most everything quick & dirty that I develop*)
*   A list of all the venue IDs saved as venues.txt. An example is included in the release. This will require legwork but if you're not already a part of the official foursquare set-up you'll need this list if you want to be.
*   A client ID and client secret from foursquare's OAuth service.

### What You'll Get

The package will generate a text file (*[check out the example][4]*) with the following information:

*   Total venues
*   Total check-ins
*   Total venues *without* a check-in
*   Total tips
*   Total photos
*   How many different mayors there are
*   Top five venues by check-in
*   Top five venues by tip
*   Top five venues by photo
*   All venues sorted by venue name with their number of check-ins, number of tips, and number of photos
*   All venues sorted by total check-ins with their number of check-ins, number of tips, and number of photos

### Caveats

Always some caveats:

*   If you have more than 200 venues that you're tracking this script will not give you details past number 200. This is because foursquare rate limits unauthenticated API calls to 200 calls per hour per IP.* **Note:** I don't believe this is the case any longer with version 2 of the API but I'll leave it here just in case.*
*   This should only give you numbers for your official venues. Anyone who creates some special check-in that's basically for them (*e.g. an office*) I suggest you skip tracking. But, hey, some numbers are better than no numbers, right?

### To Use

Usage of this should be pretty simple. Simply:

1.  [Download the source][3].
2.  Go to <https://foursquare.com/oauth/> & login with your foursquare username & password
3.  Register a new consumer (*click the big, green button*). You **do not** need to supply a valid URL or callback URL.
4.  Enter in the generated client ID & client secret in the authentication credentials section of `statistics.php`.
5.  Create your own version of the venues.txt file and, again, you can use the example there. *This is annoying and time-consuming*.
6.  Run the script from the command line by navigating to the appropriate directory & typing: php statistics.php
7.  Check out the reports directory for the report you just generated.

### Command Line?!

It's easier than you think. If you're on Mac OS X this should help you. Let's assume you've saved the Foursquare-Statistics directory that you downloaded from GitHub on your Desktop and you've added your venues. Then do the following:

1.  In the Finder go into the Applications folder and then the Utilities folder.
2.  Double-click Terminal
3.  A text window should have opened up with a blinking cursor.
4.  Type: cd Desktop/Foursquare-Statistics
5.  Hit return
6.  Assuming no error just type: php statistics.php
7.  Your report should have been generated.

Hopefully it's pretty simple and you find the information useful.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/?p=144
 [2]: http://foursquare.com/westvirginiau
 [3]: http://github.com/dmolsen/Foursquare-Statistics
 [4]: https://github.com/dmolsen/Foursquare-Statistics/blob/master/reports/example_report.txt