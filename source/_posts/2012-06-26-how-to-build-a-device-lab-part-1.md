---
published: false
title: 'How to Build a Device Lab [Part 1]'
author: Dave Olsen
layout: post
permalink: /2012/06/26/how-to-build-a-device-lab-part-1
categories:
  - Tools
tags:
  - adobe shadow
  - android
  - blackberry
  - browserstack
  - device testing
  - ios
  - ipfw
  - mobilekarma
  - ryanseddon
  - shim
  - stephanierieger
  - webos
  - wp7
---
Recently, we were lucky enough to be given the opportunity to build a device lab for our department. Stephanie Rieger ([@stephanierieger][1]) [covers the many reasons][2] why organizations need to get their hands on *real* devices for testing. As mobile becomes an increasingly important outlet for our content it behooves us to make sure that content actually works on them. Over the years we had picked up a few devices but this was a chance to "*do it right*" and we jumped at it.

## Deciding Which Devices to Get

We took a fairly pragmatic stance when deciding what devices we should get for our device lab. We evaluated devices based on the following criteria:

*   **Rank: **where was the device ranked in our stats for wvu.edu. this can be found in Google Analytics under the "Mobile" category.
*   **OS & OS Version:** we wanted a good cross-section of OSes
*   **Screen Dimensions:** again, we wanted a good cross-section of screen dimensions
*   **WiFi-Capable: **the device *had* to be WiFi-capable so we could use the device without a cellphone plan. this was a critical feature of any device we considered.
*   **Availability & Cost: **and, finally, the device had to be available for purchase and not overly expensive. this ruled out the latest and greatest.

I think we ended up meeting our goals on OS and screen dimensions. Our lab now includes devices running Windows Phone 7, webOS, BlackBerry 5, 6 & 7, Nokia Series 40 as well as various flavors of iOS and Android. If you're just starting your device lab I would rank devices as so:

1.  **iPod Touch:** as long as you aren't doing anything with GPS this could be a cost-effective choice for iOS & small screen testing. <del>no retina display though</del>. *it does have a retina display*. if someone knows of a reason why this wouldn't work please let me know.
2.  **Mid-level Android:** target something like the Samsung Fascinate that can only run 2.x of Android
3.  **High-end Android:** an HTC Thunderbolt (*maybe not so high-end anymore*) or another device capable of running Android 4.0. make sure to get a different screen pixel width/height than your mid-level device.
4.  **iPad/Android/Kindle Tablet: **i'm sort of loathe to add a tablet to the list but it could matter if you're into that kind of thing. an iPad will probably be your most expensive device though you can get a refurbished iPad 2 if you don't care about retina.
5.  **High-end BlackBerry:** any BlackBerry that can run 7.0 (*e.g. BlackBerry 9900*)
6.  **Windows Phone 7: **if only to experience something really different when it comes to a mobile OS. can be older model since none of the current hardware will support the next edition of Windows Phone anyway.

I think you can fill in as necessary after that based on your audience. Depending on where you are in the world you may want a Symbian-based or Bada-based device. If you know you have a number of important administrators with older BlackBerries pick up a 6.0 device. Android devices offer a lot of options for testing responsive designs with their varied screen widths and heights. Obviously, you might want to pick up an iPhone for testing <del>its Retina Display </del>(*can do this on the iPod Touch*). More is better but you don't have to kill yourself getting the perfect combo of devices. Especially if that's what's keeping you from jumping in.

And, **remember**, you can always check out [emulators for any of the devices][3] you can't get your hands on or you can look at web-based device testings services like [BrowserStack][4]. Ryan Seddon ([@ryanseddon][5]) put together a [good post that covers some of the options][6] in the latter category.

## Where To Get Devices

Once you've decided what type of devices you want then the obvious next step is getting your hands on some. I think their are four ways to go about this:

*   **Hand-me-downs: **this is probably the most common method to pick up devices. Someone in your department is due for a refresh on their phone and they give you their old device. Makes the device free to you but takes time to build up a significant library and, if your department is like ours, most folks tend to get the same device so when the refresh happens you're stuck with multiples of the same device.
*   **Cellphone Store Leftovers:** you should be able to go into your local cellphone dealers and ask if they have older devices that you can purchase at a discount. This will usually range from 25-50% off. The problem is, if you're in a smaller market like us, the leftovers may provide very slim pickings.
*   **eBay:** every device you might ever want for your lab is [on eBay][7]. This could be a good way to get some devices on the cheap.
*   **Mobile Karma: **[Mobile Karma][8] buys and then re-sells used devices. They don't have the widest selection and their list of devices is definitely US-centric but, that said, I think it's a more than good enough resource for building a starter device lab. Also, if you see a device one day don't expect it to be there the next. All the devices they provide come in very good condition and include chargers and extra batteries. Do compare the prices they show against those you can find on eBay.

Trolling [eBay][7] and [Mobile Karma][8] should show that you **don't have to break the bank to start building a device lab**. Especially if you limit yourself to devices 1-3 from my list above. An iPod Touch (*refurbished*) from the Apple Store and a Fascinate and Thunderbolt from [Mobile Karma][8] are, combined, only $438. And there are no contract costs with those Android phones!

## Dealing with Activation Issues

Using your new devices won't be as simple as turning them on, connecting to a WiFi network, and firing up the browser. All of them would/should have been reset to their factory defaults meaning you're going to have to activate them but without a cellphone plan. Not every device likes this. For example, with the Palm Pre 2 you'll have to get it to run in dev mode via [entering a code in the emergency number screen][9]. Other devices will have other ways to skip activation (*e.g. using the volume keys*). You'll also want to come up with one central account (*most likely Gmail-based*) that can be used to create accounts across all of the various app stores.

Activation issues can be overcome… just don't be surprised by this step.

And, please note, you don't have to provide a credit card when creating a centralized iTunes account. You can download free apps without one on record so you can skip that step if that's an issue. Then you can use that account for all of your iOS testing devices.

## Managing Your Devices

When I asked on Twitter, "*Got any questions about setting a device lab?*," the number one question was related to how to share purchased devices with other departments. To be honest, we haven't gotten that far yet. We're currently working on how to make sharing within the department easy. After that we can look outwards. I have a feeling we won't be loaning out devices. Does that sound mean? Sure. Is it more practical for us? Yes. This doesn't mean that folks couldn't visit us to test of course. The bonus of that is that they then have some experts to help them troubleshoot any problems.

Another question was "*When should we retire a particular device?*" At this point I think their is something to be learned from testing even if it's on an older device (*e.g. BlackBerry 5.0*). If a design is completely screwed up on an OS like that and your stats show almost no visits from that operating system/browser then it's OK to ignore but, otherwise, the more you can cover the better. And, again, their is always something to be learned from older platforms.

## Other Things to Buy

Unfortunately, devices are only part of the cost in setting up a lab. This is especially true if, like us, you want to set-up a *mobile* device lab. Where "mobile" means allowing the device lab to easily move around to different cubes or offices. You should think about picking up the following:

*   **Power strips:** you'll need to plug-in the devices somewhere. you don't need an outlet for every device but you'll most likely need to expand on the outlets you already have.
*   **Stands:** you'll want something to place your devices on so they can sit at an angle and be easily viewable by the designer/developer as they're testing. testing, courtesy of something like [Adobe Shadow][10], can be as simple as "*refresh a desktop browser & all of your mobile devices (based on WebKit) refresh with it automagically.*" serious.
*   **Cart:** you'll need something to put the devices on to move ‘em around.
*   **Source of WiFi:** can be an access point or, if using [SHIM][11], you'll want an extra computer that maybe has been sitting around collecting dust

We're still in the process of fleshing this part out so I don't have numbers but it shouldn't be overwhelming budget-wise.

## Getting Devices Is Only Half the Battle: Browser Testing

Getting devices into the hands of your developers and designers is only the first step in integrating device testing into your website design routine. In order to get folks to buy-in it has to be easy. Very, very easy. This is one of the reasons we want the cart. We hope that, by using the devices in their familiar environments (*e.g. their own cubes*), it will encourage them to test more. The other point is that what we're really interested in on these devices are the *browsers*. In my next article I'll talk about what browsers you might want to target and how you can use a combination of [Adobe Shadow][10], [SHIM][11], and ipfw to make it dead-simple for developers to robustly test and tweak their mobile designs in those browsers.

Have your own tips for setting up a device lab? Any other questions I can answer? Please submit a comment!

 [1]: http://twitter.com/stephanierieger
 [2]: http://stephanierieger.com/on-designing-content-out-a-response-to-zeldman-and-others/
 [3]: http://www.mobilexweb.com/emulators
 [4]: http://www.browserstack.com/
 [5]: http://twitter.com/ryanseddon
 [6]: http://www.thecssninja.com/mobile/testing-devices
 [7]: http://www.ebay.com/sch/Cell-Phones-Smartphones-/9355/i.html
 [8]: http://mobilekarma.com
 [9]: https://developer.palm.com/distribution/viewtopic.php?f=91&t=10495
 [10]: http://labs.adobe.com/technologies/shadow/
 [11]: https://github.com/marstall/shim