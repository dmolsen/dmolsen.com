---
title: QR Codes vs Text Messaging for Sharing Web Links
author: Dave Olsen
layout: post
permalink: /2011/04/29/qr-codes-vs-text-messaging-for-sharing-web-links
categories:
  - General
tags:
  - grigs
  - qr
  - qr codes
  - sms
  - text messages
  - text messaging
  - wvu
---
Over the last year or so we at West Virginia University have used [QR codes][1] in several projects ([*one example*][2]). After pulling in some numbers and comparing them against a similar tool I think I've finally come to a conclusion on them. **QR codes are probably not worth implementing**. They are, in retrospect, a bit like putting a round peg in a square hole. They look cool, they're the latest and have buzz but there is always that niggling feeling they're not right for our audience. If part of rolling out a project includes directions on how to download software then we're probably doing it wrong.

## So what's the similar tool? Text Messaging (aka SMS)

The only thing we've done with QR codes so far is share links to mobile-optimized websites. We're not sharing complex data like business cards or the like. Which might be a good thing since Google, as part of their Charts API, [suggests using version 4 of QR codes][3]. The version number of  a QR code determines how much data can be encoded in it based on the overall number of columns & rows in the code. For version 4 that's 33 rows x 33 columns which means a maximum possible encoding of 114 alphanumeric characters. That's well within the 160 alphanumeric character limit of text messages. So from a data storage/transfer standpoint QR codes and text messaging are on equal footing and, for us, can do a very similar job.

## The Numbers

Below are the number of uses of each technique for two recent projects. I'll be very upfront by noting that neither project allowed either technique equal advertising so the numbers could be skewed a bit because of this. I've noted in each project description what the differences were.

<img class="alignnone size-full wp-image-210" title="qr_code_vs_txt_msg" src="http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/04/qr_code_vs_txt_msg1.png" alt="" />

### Tournaments Project

Our [Tournaments project][5] was designed to allow us to engage fans of West Virginia University around the Big East & NCAA tournaments. QR codes were featured on the website, on our digital signage throughout campus, as well as in [two][6] [videos][7] that helped hype the project. We only listed the text message information on the website itself. Both techniques simply shared the web address for the site. Because of the lack of advertising for the text messaging I was shocked that they performed at almost double the rate of the QR codes (**65% vs 35%**). As for content performance… it looks to be pretty even so I'm not sure their is any real difference between either technique.

One anecdotal story about both techniques for this project… When my boss was showing her son how to get a QR code reader onto his iPhone and then how to take the picture to get to the website she happened to mention the text message option and he asked why she just didn't tell him that easier option earlier.

If you want to try it out for yourself simply **text WVUTOURNEY to 41411**.

### Fan Shirt Contest

The other recent project was a [contest where users could vote][8] for next year's official fan shirt for West Virginia University. Initially we were only going to use the text messaging and QR codes to test the efficacy of using only digital signage for these sort of projects. Basically, which one of these techniques best paired with our very robust digital signage system. As it turns out the text messaging information made it onto some printed material as well. How much that threw off the numbers I'm not sure.

While voting from the web dominated text messaging accounted for a respectable **6.1% (701)** of the votes. QR codes only accounted for **0.3% (38)** of the votes.

## How We Did It: TextMarks

We've  been creating text message-based services for a while. The most important is probably our application status check. For all of these we have used [TextMarks][9]. It's a dead-simple service with [lots of options][10] and, by paying a small fee, can be ad free. They're currently offering a 14-day free trial. It can be used to shoot mass messages to groups, targeted messages to individuals, or respond to a query with a very simple message a la our Tournaments project. The best feature to me as a developer though, and how we implemented the voting, is the [REST-based SMS API][11]. Basically you can use SMS as an interface into your web applications.

## Conclusion

This is not to say that QR codes should be completely avoided. I suspect we'll continue to use them. It's just that if you really want folks to get your web address easily onto their phones then look into using text messaging with a service like [TextMarks][12] as a powerful "back-up" to QR codes . Echoing something similar that Jason Grigsby ([@grigs][13]) said about native apps versus browsers ,

> *Not every phone will have a QR code reader on it but they will all support text messaging.*

Well, that and the notion that sometimes old tech is the best tech. I definitely encourage you to play around with text messaging and see if it fits into your mobile and/or communication strategy.

And after thinking on this a bit more I think the following observation is also worthy of mentioning:

> *Users have shown they're willing to use their mobile device to access content or take an action… just probably not from a QR code.*

### Addendum: Tracking QR Code Usage

Back in the day I wrote a post about using bit.ly to track QR code usage. For these projects we used [Galvanize][14]. [Galvanize][14] is a PHP class that allows you to track clicks with Google Analytics without using JavaScript. So what we did was encode the unique address `http://tournaments.wvu.edu/qr/` in the QR code. This address was just a PHP script that used Galvanize to record the pageview and then would redirect the user to the real page for the campaign. It made it very easy for us to track usage via Google Analytics and for everyone on the team to get access to the data.

 [1]: http://en.wikipedia.org/wiki/QR_codes
 [2]: http://www.dmolsen.com/mobile-in-higher-ed/?p=13
 [3]: http://code.google.com/apis/chart/docs/gallery/qr_codes.html#details
 [4]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2011/04/qr_code_vs_txt_msg1.png
 [5]: http://tournaments.wvu.edu/
 [6]: http://www.youtube.com/watch?v=4hTHrUcmscs
 [7]: http://www.youtube.com/watch?v=HVn3XEe93eU
 [8]: http://fanshirt.wvu.edu/
 [9]: http://textmarks.com/
 [10]: https://www.textmarks.com/front/tour/
 [11]: https://www.textmarks.com/front/dev/
 [12]: http://textmarks.com
 [13]: http://twitter.com/grigs
 [14]: http://sourceforge.net/projects/galvanize/