---
title: How to Sync Web Page Events With Embedded YouTube Videos
author: Dave Olsen
layout: post
permalink: /2011/12/19/how-to-sync-web-page-events-with-embedded-youtube-videos
categories:
  - General
tags:
  - gists
  - holidaycard
  - holidaycard2011
  - javascript
  - youtube
  - youtube javascript player api
  - youtubeplayer
---
As noted in the [Creating CSS3 Snowflakes][1] article, for our recent [holiday card project][2] we wanted to create an experience with the website that was closely tied to our centerpiece video. One of the keys to this was making the experience seem as seamless as possible to allow the viewer to immerse themselves in the video. We also wanted to see if we could connect events in the video to events on the web page to further enhance the experience.

## Examples of Syncing Events

To get an idea of what I mean by "*syncing web page events with an embedded YouTube video*" it might be good to check out two examples. The [first example][3] is very simple and it's the one I created as a proof of concept for our holiday card project. The [example page][3] explains what you should see. The [second example][2] is the [holiday card itself][2]. The holiday card example will only work on Safari, Chrome and Firefox because of the CSS3 animations we used.

The main thing we did with the [holiday card][2] project to make the experience seem seamless was to hide the text and other traditional page "chrome" when the video started playing. We did this with a simple opacity transition and then moved those elements far off the screen. Once these elements are removed the viewer is left with the video playing and the background. The background, an overview of our campus, is not a static though. The main character in the holiday card video was a sprite visiting and bringing holiday magic to various locations around campus. As the sprite visits places like our freshman dorms or our football stadium the location of the sprite is highlighted on the page background with those same locations changing color. It's a subtle effect because we didn't want to distract too much from the video itself. My favorite part is the sprite rising into the air from downtown Morgantown (*only viewable in Safari & Chrome because of a specific type of CSS3 animation*).

So how did we do it?

## YouTube's JavaScript Player API

I think many folks are familiar with the [various parameters][4] that one can set on an embedded YouTube video to control how it looks & behaves (*e.g. turn off related links*). If you aren't familiar with them go [check them out now][4]. They can give you a lot of control, especially from a branding perspective. One step beyond that though is the [YouTube JavaScript Player API][5]. It allows developers to control the player itself. It's important to note that the [YouTube JavaScript Player API][5] only works with the older embed code. An API for the iFrame embed is [currently experimental][6].

The YouTube JavaScript Player API allows you to use, you guessed it, JavaScript, to control things like starting a video, stopping a video, changing what video is playing in the player, playback quality, and even the player volume. While those things are useful, the best feature of the YouTube JavaScript Player API, especially when looking at syncing actions between a web page and video, is the event `onStateChange`. It is fired every time the video is started, paused, buffered, or ended. Luckily, there's a simple YouTube JavaScript Player API wrapper, [YouTubePlayer][7] (*originally created by Anurag Mishra*), that makes it easy to quickly embed a video (*via [SWFObject][8]*) and then listen for these `onStateChange` events.

## Using `onStateChange` & YouTubePlayer

Using [YouTubePlayer][7] to listen to these `onStateChange` events is actually quite straightforward. As with any video the first thing you'll want to do is embed it. All you need to know is the ID of the <div> where your video will be embedded and the ID of the YouTube video.

<script src="https://gist.github.com/dmolsen/1494961.js"></script>
<noscript>This gist is available at: [https://gist.github.com/dmolsen/1494961](https://gist.github.com/dmolsen/1494961)</noscript>

Once that's done you can set-up event listeners that do something when the event you want to track is fired. For example, let's listen for when a viewer starts playing a video and then listen for when the video ends. It's important to note that ‘*playing*‘ is fired after a user pauses and then restarts a video. There's no differentiation between starting a video for the first time and after pausing the video.

<script src="https://gist.github.com/dmolsen/1495027.js"></script>
<noscript>This gist is available at: [https://gist.github.com/dmolsen/1495027](https://gist.github.com/dmolsen/1495027)</noscript>

[YouTubePlayer][7] gives really easy access to these events via the `.on()` function. But what about timing events like the fireworks in the [original example][3]?

## Timed Events with YouTubePlayer

I  added the `.at()` alias and expanded the `.on()` functionality for [YouTubePlayer][7] to make it really easy to add timed events. Using the fireworks as a quick example:

<script src="https://gist.github.com/dmolsen/1495049.js"></script>
<noscript>This gist is available at: [https://gist.github.com/dmolsen/1495049](https://gist.github.com/dmolsen/1495049)</noscript>

Essentially the `.at()` function registers events with the browser with a certain name based on the time the event should take place (*e.g. 1100*). These events are then fired by a `setInterval()` function that tracks time once the viewer starts watching the video. Every time the tracked time is incremented (*e.g. from 1000ms to 1100ms*) a corresponding event is fired (*e.g. 1100*). Thanks to `onStateChange`, if the video is paused or buffering the tracked time isn't incremented and no event is fired. If a video is scrubbed the tracked time is updated appropriately and incremented again.

For the most part timed events can be fairly straightforward as shown in [the source for the simple example][9]. It can also get a little complicated as seen in the [source for the holiday card timed events JavaScript][10]. With the latter I was trying to make sure, because buildings stay highlighted after their event is fired, that if a user scrubbed backwards in time that buildings would be hidden again if appropriate.

## A Warning About Timed Events

There is one very important thing to keep in mind when working with timed events. Because the tracked video time is sort of faked by using the `setInterval()` function (*e.g. we're not polling the video directly for the current time in the video. that's just not a good idea nor accurate*) the tracked time can fall behind the real video time. The main culprit for this is heavy JavaScript that gets called by your timed events and then causes the execution of the `setInterval()` to be blocked until the heavy JavaScript finishes running. Keep whatever you launch via the timed events as light as possible. Simple manipulations of the DOM might be best. That way, if you have a longer video, the timed events will play when they're supposed to.

## Conclusion

I always find it difficult to explain something like this without saying "Just look at the code." Hopefully you were able to get a reasonable idea of how easy it is to use timed events to sync web page content with your embedded YouTube videos. I think there are a lot of opportunities to create richer experiences for viewers with this technique.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/2011/12/19/creating-css3-snowflakes/
 [2]: http://happyholidays.wvu.edu/
 [3]: http://dmolsen.com/youtube-player/
 [4]: http://code.google.com/apis/youtube/player_parameters.html
 [5]: http://code.google.com/apis/youtube/js_api_reference.html
 [6]: http://code.google.com/apis/youtube/iframe_api_reference.html
 [7]: https://github.com/dmolsen/YoutubePlayer
 [8]: http://code.google.com/p/swfobject/
 [9]: https://github.com/dmolsen/YoutubePlayer/blob/master/scripts/example.js
 [10]: https://gist.github.com/1495085