---
title: 'Google Maps JavaScript API v3 &#038; jQTouch'
author: Dave Olsen
layout: post
permalink: /2010/06/15/google-maps-v3-jqtouch
categories:
  - Mobile Web OSP
  - Tools
tags:
  - campus map
  - github
  - google maps
  - jqtouch
  - map
  - mobile web osp
  - wvu
---
One of the toughest features to implement in the latest version of [WVU Mobile Web][1] was the maps feature for the [jQTouch][2]-enabled views for iPhone and Android. It [looks good][3] but it was a several week bear and the single most annoying thing I've put together related to jQTouch. With that in mind I'm trying to share my experience and code so others can more easily implement a similar feature.


On <a href="http://github.com/">GitHub</a> I now have a <a href="http://github.com/dmolsen/Google-Maps-v3-for-jQTouch">Google Maps v3 for jQTouch repository</a>. It contains a very simple project that is an example of using <a href="http://code.google.com/apis/maps/documentation/javascript/">Google Maps JavaScript API v3</a> with <em>revision 133 </em>of <a href="http://jqtouch.com/">jQTouch</a> and <a href="http://jquery.com/">jQuery 1.4</a>. I do not currently have this demo working with <em>revision 148</em> of jQTouch. r148 is the absolute bleeding edge at the time of this writing. Some points to keep in mind:


*   r133 is <strong><em>not</em></strong> the beta version linked from the main jQTouch site. It was the edge release when i started on my project. If you've been working off the beta the only change I think you'll have to make is to add a div with the ID of `jqt` around your divs. Refer to the project to see an example.
*   the project appears to handle rotation of the device after the map is loaded just fine. It does go a little wobbly if the device is rotated before the map is loaded. I still need to troubleshoot that.
*   the project assumes map "pages" will be loaded via AJAX. Our system dynamically generates many maps so that's just how we're dealing with it.
*   any "page" that will link to a map page needs to have the class `clear-map-detail` so the DOM is properly cleaned up after closing out the map. This reduces a "white flash" you could see as well as making future maps load properly.
*   the `notransform` class in jqtouch.css is actually from r143 of jQTouch. I had had something similar but went with David's implementation from a later revision instead. This class makes the map draggable.
  
To see a demo of this all working check out <a href="http://m.wvu.edu/">WVU Mobile Web</a> on your iPhone or Android device.

Some helpful links:

*   <a href="http://jqtouch.com/">jQTouch</a>
*   <a href="http://code.google.com/apis/maps/documentation/javascript/">Google Maps JavaScript API v3</a>
*   <a href="http://mobiwebosp.pbworks.com/">Mobile Web OSP</a>

 [1]: http://m.wvu.edu/
 [2]: http://jqtouch.com/
 [3]: http://www.flickr.com/photos/dmolsen/4535301785/in/set-72157623766895109/