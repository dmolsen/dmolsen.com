---
title: Creating CSS3 Snowflakes
author: Dave Olsen
layout: post
permalink: /2011/12/19/creating-css3-snowflakes
categories:
  - General
tags:
  - animations
  - css
  - css3
  - estellevw
  - holidaycard
  - holidaycard2011
  - javascript
  - snow
  - snowflakes
---
For our recent [holiday card project][1] we wanted to create an experience with the website that mimicked the video that was the centerpiece of the project. While it was straightforward enough to use the same graphic style as the video we also wanted to include some of the same atmospheric effects as well like twinkling stars, moving fog, sparkles and, most importantly, snow. To create these we used CSS3 animations and transitions.

## Making it Snow

In order to make it snow in our project I modified some CSS created by Estelle Weyl ([@estellevw][2]) for [a SXSW talk she gave][3]. [The talk][3] does a great job explaining the ins-and-outs of the CSS that gets used (*e.g. animations, border-radius, timing*) so I won't repeat that here. The main contribution I made, beyond tweaking the CSS some to have the snowflakes look the way I wanted, was to create an easy way with JavaScript to:

*   randomly places N amount of snow across the web page
*   randomly assign classes to each snowflake to randomize their look (*e.g. size, speed, delay, opacity*)
*   properly detect the height of a web page when snowflakes are created and update the animation keyframe so they fall an appropriate distance instead of a "one size fits all"-style. Unfortunately, `window.onresize` is not accounted for.

You can[ view a demo of the CSS3 snowflakes in action][4]. If you think it's interesting you can [grab the code (CSS & JavaScript) on GitHub][5] to use on your own site. [Directions][5] on how to get it snowing are in the [README][5].

## Dependencies & Browser Support

There aren't any real dependencies for this project other than [browsers that support animations][6]. This means this project can be used with Safari, Chrome, and FireFox. If the appropriate -ms- extensions were added it would probably work with Internet Explorer 10 as well. In the demo I use [domReady][7] to include the JavaScript in the `<head>` but that's not necessary if you instead put the code before the `</body>` tag.

 [1]: http://happyholidays.wvu.edu/
 [2]: http://twitter.com/estellevw/
 [3]: http://www.standardista.com/sxsw/
 [4]: http://dmolsen.com/css3-snowflakes
 [5]: https://github.com/dmolsen/CSS3-Snowflakes
 [6]: http://caniuse.com/#feat=css-animation
 [7]: https://github.com/ded/domready