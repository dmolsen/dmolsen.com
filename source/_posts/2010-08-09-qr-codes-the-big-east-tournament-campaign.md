---
title: 'QR Codes &#038; the WVU Big East Tournament Campaign'
author: Dave Olsen
layout: post
permalink: /2010/08/09/qr-codes-the-big-east-tournament-campaign
categories:
  - General
tags:
  - big east
  - marketing campaign
  - mobile web
  - qr codes
  - wvu
  - wvutoday
---
Last week there was a [nice post on QR codes][1] on the [Brand Manager's Notebook][2] by Ineke Caycedo. It gives a good introduction for the tech behind QR codes (*there's also a [great video from Google][3] showing their QR code-based "Favorite Places" initiative in action*) so I'm not going to cover that here. The salient points to keep in mind is that they're easy to generate and *free*. What I do want to talk about is how we've used them in a campaign at West Virginia University. We've actually used them twice but I only have examples of the material for one particular campaign. We will be using QR codes on campus this fall to help push users to [WVU's mobile site][4].

## Big East Tournament Campaign

During the 2010 Big East Tournament we had a campaign that had the goal of publicizing our news site, [WVUToday][5], and its redesigned logo to alumni and fans. The campaign centered around words that exemplified what it meant to be a Mountaineer. We had an internal team of about eight people who took the campaign from concept to delivery in about three and a half weeks. That includes print, web, and video.

### The QR Code

<img style="float: right; margin-left: 10px; margin-top: -60px;" src="http://chart.apis.google.com/chart?chs=200x200&cht=qr&chl=http%3A%2F%2Fwvutoday.mobiexp.wvu.edu%2F&choe=UTF-8" alt="wvutoday QR code" />We used the [Google Charts API][6] to create our QR code (*the QR code to the right is generated this way and goes straight to the mobile site for this campaign*). Another, probably easier source is the [Kaywa QR code generator][7]. I use quiQR on my iPhone as my reader of choice but there are other options available as well.

### The Pieces for the Campaign

Their was a business card (*shown, not actual size*) and a nearly identical tent card for display at the event. One thing to keep in mind when testing these kinds of pieces is that devices lacking in a macro mode for their camera (*like the iPhone 3G*) need bigger QR codes to be able to properly read them. Our business card was the smallest version of the QR code my iPhone 3G could read.

<div style="width: 98%;">
	<div style="float: left; width: 48%;">
		<img title="bcard_front" src="/wp-content/uploads/2010/08/bcard_front-e1281293823765.jpg" alt="" />
	</div>
	<div style="float: right; width: 48%;">
		<img title="bcard_back" src="/wp-content/uploads/2010/08/bcard_back-e1281293871190.jpg" alt="" />
	</div>
	<div class="clearfix"></div>
</div>

There were a few t-shirts printed up that had the QR code on it and student volunteers got to wear them around New York City and at the event (*luckily I got a leftover*).

<img class="alignnone size-full wp-image-70" title="1268155512_lg" src="/wp-content/uploads/2010/08/1268155512_lg-e1281293944588.jpg" alt="" />

There was also a video for display at the event though it didn't have a QR code associated with it. That's because we didn't feel that there would be enough time to show a QR code and have users grab a picture of it before the video ended. I just think it's one of the best pieces to come out of our Video Productions group so I'm sharing it anyway. I think it also helps reinforce how tight the campaign was from a look & feel standpoint.



### The Mobile Site

The QR code ended up leading to the [WVUToday mobile experience site][11] as seen here in examples from the iPhone version. There are a lot more examples on the [Tournament Campaign page][12] on the [WVU University Relations site][13]. There was also a generic version of the site for devices that didn't support all the fancy JavaScript and CSS. The point of the site was to expand on five of the words featured in the other pieces by offering a related story from our news site.

<div style="width: 98%;">
	<div style="float: left; width: 48%;">
		<img title="campaignsite_1" src="/wp-content/uploads/2010/08/campaignsite_1-e1281294025406.jpg" alt=""  />
	</div>
	<div style="float: right; width: 48%;">
		<img title="campaignsite_2" src="/wp-content/uploads/2010/08/campaignsite_2-e1281294098816.jpg" alt=""  />
	</div>
	<div class="clearfix"></div>
</div>

The site uses [jQTouch][16] for all the of the dynamic interaction. I think it's pretty cool how you swipe through the "cards" to access more content and then tapping a card will flip to give you a story that's an example of the theme. I did this part of the campaign myself and it took about four days to work through all the issues. This is also the project on which I learned the importance of testing on a real device and not just a simulator. The target areas for the "clicks" were too small because I had used the tiny cursor as opposed to my fat fingers during testing. Luckily we realized that before going into production with it.

*If you're on an iPhone try saving the site to your homescreen. I think it makes for a better experience and offers a cool native app-like feature, a startup screen.*

### Tracking the QR Code Usage

In order to track the usage of the QR code we used [Galvanize][17]. [Galvanize][17] is a PHP class that allows you to track clicks with Google Analytics without using JavaScript. So what we did was encode the unique address `http://wvutoday.wvu.edu/qr/` in the QR code. This address was just a PHP script that used Galvanize to record the pageview and then would redirect the user to the real page for the campaign. It made it very easy for us to track usage via Google Analytics and for everyone on the team to get access to the data.

### The Results

Regarding expected results I tried to be conservative and had only hoped for a minimum of 100 visits via the QR code. We had about 60 total. A few things that I don't know about the QR codes is how prominent any of the pieces were or how many people really got a chance to see them.

### The Future

We will continue to use QR codes. We've already used them for another event and obviously we will use them to advertise our [regular mobile site][4]. I think the most benefit for QR codes will come from advertising services on campus. For example, a QR code to get the dining hall menu or, my tried and true example, a QR code to show the time when the bus will arrive. There are some really good ideas in that [Brand Manager's Notebook][1] post as well. Again, the notion of context will drive adoption and use. Is there  a place for QR codes in marketing campaigns? Definitely. If you're putting a URL on your printed pieces or billboards why not supplement that with a QR code as well? You don't necessarily have to have a mobile-optimized site behind it and it makes it just that much easier for users to access/bookmark content.

Hopefully this gives you some ideas on how you can use QR codes in the future. Are you using them already? Drop me a line in the comments.

 [1]: http://brandmanagersnotebook.wordpress.com/2010/08/05/add-qr-codes-to-your-marketing-mix-to-give-your-campaigns-some-extra-dimension/
 [2]: http://brandmanagersnotebook.wordpress.com/
 [3]: http://www.youtube.com/watch?v=zuVSpG-ZdkU&feature=player_embedded
 [4]: http://m.wvu.edu/
 [5]: http://wvutoday.wvu.edu/
 [6]: http://code.google.com/apis/chart/docs/gallery/qr_codes.html
 [7]: http://qrcode.kaywa.com/
 [8]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/08/bcard_front.jpg
 [9]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/08/bcard_back.jpg
 [10]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/08/1268155512_lg-e1281291716492.jpg
 [11]: http://wvutoday.mobiexp.wvu.edu
 [12]: http://universityrelations.wvu.edu/tournament_campaign
 [13]: http://universityrelations.wvu.edu/
 [14]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/08/campaignsite_1-e1281294025406.jpg
 [15]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/08/campaignsite_2-e1281291629829.jpg
 [16]: http://www.jqtouch.com/
 [17]: http://www.acleon.co.uk/2009/10/galvanize-google-analytics-without-the-javascript/