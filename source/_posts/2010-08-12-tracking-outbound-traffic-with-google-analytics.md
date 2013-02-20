---
title: Tracking Outbound Traffic with Google Analytics
author: Dave Olsen
layout: post
permalink: /2010/08/12/tracking-outbound-traffic-with-google-analytics
categories:
  - General
tags:
  - google analytics
  - jquery
  - nickdenardis
  - non-mobile
  - paulprewitt
  - Statistics
  - xkcd
---
*This post isn't really related to mobile. I will be updating my code in *[*Mobile Web OSP*][1]* to use a modified version of the following code to track outbound traffic though. My current code tracks outbound clicks as pageviews rather than the preferred events.*

So the fallout from the [XKCD][2] cartoon *[University Website][3]* continues with a post from Inside Higher Ed entitled *[Web Re(design)][4]*. Fun quotes, insights, and comments abound but the following paragraph really struck me:

> One problem with using nationwide data or broad-based best practices is that just as many institutions are different, the audiences of different institutions may want different things. And parsing those demographics effectively requires self-study more than adhering to broad principles, say several consultants who take contracts for such work. Still, even professionals sometimes struggle to figure out the percentages of how home page audiences divide up so they can probe their desires, says Stephanie Geyer, associate vice president for Web strategy at Noel-Levitz. "I suspect that would be hard data to come by reliably," Geyer says. "You could set up a survey on the site, but you're not necessarily going to get a reliable sample at any given time."

I think you can get a start on gathering that audience data by tracking outbound traffic. While I don't think tracking outbound traffic is the be all and end all to figuring out the "desires of your audiences" ([*@paulprewitt*][5] *kindly set me straight on this point*) I do think it will give you interesting insight into what users are actually using on your site and, again, will give you some data to back that insight up. How do you do it? Just use the Google Analytics [Event Tracking feature][6]. It's unobtrusive and it'll capture data on every user that uses the page and not just those select folks you can push a survey too.

I've [posted some code][7] that should allow you to easily take advantage of the Event Tracking feature. Feel free to copy it, fork it or contribute back if you want. All you need to do is copy and paste it into the `head` portion of your pages. Just make sure to update the account number. *It may not be perfect though.* It works in my testing but triple-check it before adding it to your production site.

Some more details regarding the code:

*   It's using the latest, greatest Google Analytics set-up so no guarantee it will work with older versions. If you're interested in tracking outbound traffic but you're stuck with an older version of Google Analytics check out Nick DeNardis' ([@nickdenardis][8]) post on [EduGuru][9], *[Tracking outgoing clicks with Google Analytics][10]*. It tracks outbound links as pageviews though so be aware of that. Nick does provide a good workaround though.
*   It requires jQuery. If you're already using jQuery then great. If not… think long and hard about if you want to include jQuery just for this feature. I'm sure this code could be rewritten to remove the jQuery requirement. Unfortunately for you I'm lazy and I don't feel like doing it as this code serves my needs just fine.
*   It'll track all links that have http or https in them auto-magically. It will ignore links though that have an http in them but link to the same hostname. So if you need to track those types of links (*for example, you have a link to a sub-site on the same hostname*) you can add the attribute `data-ga` to your link. For example, to link to our example sub-site you'd do the following: `<a href="http://www.dmolsen.edu/subsite/" data-ga="outgoing">Visit Sub-site</a>`
*   Your HTML will most likely no longer validate because of the extra attributes in your `href` tags.

But the whole point of the XKCD comic and the Inside Higher Ed post was about audiences and gathering data related to them, right? How does tracking outbound traffic clearly give you information on use by audience? There's an option available in my code (*not required!*) that allows you to track the audience as well as the location of a link. To do so you'll need to add the attribute `data-aud` with a consistent value for your audiences to your outbound `href` tags that you want to tag by audience. For example, this link:

> `<a href="http://apply.dmolsen.edu/" data-aud="Prospects">Apply Now!</a>`

will record in the Event Tracker as "Outbound Traffic – Prospects" with the link `http://apply.dmolsen.edu/`. That way you can see which audience the outbound link was for and where they went. You can also mix audiences if you like. For example the audience could be "Prospects & Current Students" so you can see what outbound links are related to both. This creates a separate category in the Events listing though as opposed to adding an event to two separate categories. I wouldn't go too crazy  coming up with very specific audiences or mixing audiences as I think you'll dilute the results a bit.

Hopefully this gives you a chance to get some data on how your home page is being used as a portal and who might be using it.

 [1]: http://mobilewebosp.pbworks.com/
 [2]: http://www.xkcd.com/
 [3]: http://xkcd.com/773/
 [4]: http://www.insidehighered.com/news/2010/08/11/websitesredux
 [5]: http://twitter.com/paulprewitt
 [6]: http://code.google.com/apis/analytics/docs/tracking/eventTrackerGuide.html
 [7]: http://gist.github.com/520170
 [8]: http://twitter.com/nickdenardis
 [9]: http://doteduguru.com/
 [10]: http://doteduguru.com/id1496-tracking-outgoing-clicks-with-google-analytics.html