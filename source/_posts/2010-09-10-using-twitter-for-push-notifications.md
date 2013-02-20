---
title: Using Twitter for Push Notifications
author: Dave Olsen
layout: post
permalink: /2010/09/10/using-twitter-for-push-notifications
categories:
  - Tools
tags:
  - notifications
  - oauth
  - Twitter
---
Recently we've been dealing with a temperamental system. We set-up a few monitoring tools to let us know when the system was throwing a tantrum but emails from the system never seemed fast enough. In order to make sure that we got notifications as fast as possible we decided to have them also post to Twitter so Twitter could send SMS messages to our mobile devices. While we've only had it fire off once so far (*knock on wood*)* *it was great to be able to troubleshoot within seconds of an issue being found. We also rolled this feature out for notifications for an on-campus transportation system.

So how can you set-up Twitter to send you notifications for your system? Well, if you feel comfortable with PHP here's how:

## 1. Set-up a New Twitter Account

This should be pretty self-explanatory. Go to [http://twitter.com/][1] and click the big "sign-up" button.

## 2. Register Your App

Go to <http://dev.twitter.com/> while you're logged into your new Twitter account. Click on the "Register an App" link.

<img title="register_app" src="/wp-content/uploads/2010/09/register_app.png" alt="" />

Then just fill out the form you're shown. Some tips:

*   Your "Application Website" can just be your school's home page. Since no one other than you is going to use the app you don't have to provide anything real here.
*   You can leave "Callback URL" blank since your app won't need to authenticate users.
*   For my app I chose "Read & Write" but I have no idea if "write" is really needed. Doesn't hurt to set that.

## 3. Copy the OAuth Settings

As of August 31, 2010 Twitter is no longer allowing basic authentication. All apps are now required to use OAuth. You will need to copy down the consumer key and consumer secret to use in your app.

<img title="oauth_settings" src="/wp-content/uploads/2010/09/oauth_settings.png" alt="" />

## 4. Copy the OAuth Access Tokens

This part caused me confusion at first. I had a tough time finding them. You'll need to click the "My Access Token" link in the menu bar on the right. Then you will need to copy down the access token and access token secret.

<img title="oath_tokens" src="/wp-content/uploads/2010/09/oath_tokens.png" alt="" />

## 5. Download the Twitter with OAuth PHP class

Since Twitter is now OAuth-only you'll need to make sure you have a PHP class that supports OAuth. In my recent project I used Tijs Verkoyen's [Twitter with OAuth PHP class][5]. I found it really easy to implement and well-documented.

**Special note:** if your install of PHP is pre-5.2 you'll have to download the [PEAR JSON library][6] and [jsonwrapper][7]. Twitter returns data in JSON and the Twitter with OAuth PHP class uses PHP 5.2+'s built-in `json_decode()` function. Having the PEAR JSON library & jsonwrapper will keep the Twitter with OAuth PHP class from blowing up. *It will not allow you to access the data from Twitter though.* Since we're only posting to and not reading from Twitter this shouldn't be a problem.

## 6. Set-up Your PHP Script to Update Your Status

Here is the code you can include in your app to update the Twitter status of the user you created earlier in the process.

> `# require the Twitter with OAuth PHP Class<br />
require("twitter.php");`
> 
> ` `
> 
> `# replace as appropriate based on what you copied down earlier<br />
$consumer_key = '';<br />
$consumer_secret = '';<br />
$oauth_token = '';<br />
$oauth_token_secret = '';`
> 
> ` `
> 
> `# update the Twitter status with $your_message<br />
$twitter = new Twitter($consumer_key, $consumer_secret);<br />
$twitter->setOAuthToken($oauth_token);<br />
$twitter->setOAuthTokenSecret($oauth_token_secret);<br />
$twitter->statusesUpdate($your_message);`

If, like us, your message could be the same many times in a row you'll need to add something unique, like a date, to each message to make sure that Twitter doesn't see it as a duplicate and reject the message. For our campus transportation notifications system Twitter refused to update the status even if the message only happened to match one message posted in the last few hours.

## 7. Make sure Twitter is Sending the Updates to Your Mobile Device

And last, but definitely not least, make sure that Twitter is sending the updates that your new Twitter user posts to your mobile device. There is a handy icon on the new Twitter users account you'll have to click.

<img  title="mobile_post" src="/wp-content/uploads/2010/09/mobile_post.png" alt="" />

So with that you should have enabled your PHP application to post to Twitter so you can get notifications of important changes via SMS.

 [1]: http://twitter.com
 [2]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/09/register_app.png
 [3]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/09/oauth_settings.png
 [4]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/09/oath_tokens.png
 [5]: http://classes.verkoyen.eu/twitter_oauth
 [6]: http://pear.php.net/pepr/pepr-proposal-show.php?id=198
 [7]: http://www.boutell.com/scripts/jsonwrapper.html
 [8]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/09/mobile_post.png