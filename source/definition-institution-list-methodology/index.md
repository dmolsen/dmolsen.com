---
title: 'Definition, Institution List &#038; Methodology'
author: Dave Olsen
layout: page
---
## Definition of a "Mobile Site"

For the purposes of the [Higher Ed Mobile Directory][1] search I'm defining a mobile site simply as:

> A central portal of mobile-optimized information (e.g. campus calendar, campus map, or enrollment information) for an institution.

Any mobile-optimized website for an institution can be listed in the [Higher Ed Mobile Directory][1]. Unfortunately, I'm not in a position to suss out all the possible mobile-optimized sites at an institution during my search.

## Institution List

In order to conduct my search for mobile websites I use a [list of American universities][2] maintained by the [College of Liberal Arts & Sciences][3] at the [University of Florida][4]. The list does not, by default, include community colleges so they tend not to show up in my list.

## Methodology

The following is my methodology for populating the [Higher Ed Mobile Directory][1] based on the list of institutions. This is all done automatically with a PHP script that I've written:

1.  An updated copy of the list of institutions is pulled from the University of Florida website.
2.  The list is parsed for the main web address for each institution.
3.  Each institution domain is then compared against a list of domains already listed in the Higher Ed Mobile Directory. If found that institution is skipped.
4.  For institutions that aren't already listed the following requests are made. All are made with the user agent string of an iPhone. 
    1.  the institutions home page to see if it redirects
    2.  http://m.institution.edu
    3.  http://mobi.institution.edu
    4.  http://mobile.institution.edu
    5.  http://www.institution.edu/m/
    6.  http://www.institution.edu/mobile/
5.  Those requests that come back with either a HTTP response code of 200 or 302 are written out to a log.
6.  I manually review the log to see which ones came back as false positives (e.g. 404 error pages that come back with a 200 response code).
7.  Those institutions that have mobile sites are then added.

Obviously those institutions that host their mobile site at a different URL than the common ones I'm testing will not be found. Also, if a site uses responsive web design for the home page to make it mobile-optimized it will not be found.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/higher-ed-mobile-sites/
 [2]: http://www.clas.ufl.edu/au/
 [3]: http://www.clas.ufl.edu/
 [4]: http://www.ufl.edu/