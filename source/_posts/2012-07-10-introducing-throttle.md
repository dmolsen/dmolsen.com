---
title: 'Introducing Throttle: Helping You Test Your Websites at Mobile Network Speeds (aka Slooowwww)'
author: Dave Olsen
layout: post
permalink: /2012/07/10/introducing-throttle
categories:
  - Tools
tags:
  - adobe shadow
  - bandwidth
  - device lab
  - guypod
  - latency
  - node
  - shim
  - throttle
---
As I noted at the end of my last post, *[How to Build a Device Lab][1]*, getting devices is only half of the battle when trying to create a robust platform for testing your mobile websites. The other half is finding tools that allow you to test your websites quickly and easily. While reviewing tools the one thing that stuck out to me was that we were running tests from our devices over an, essentially, pristine WiFi connection. In the real world, our users would be stuck on clogged networks with varying levels of quality. Guy Podjarny's ([@guypod][2]) presentation, *[The Mobile Difference In Numbers][3]*, does a good job of showing why we need to take network performance into account when designing our mobile websites. Therefore, modifying network speeds would need to play a larger part in our testing scenarios if we really wanted to know how well our mobile designs were working.

All of the tools that I found related to modifying connection speeds were focused on modifying the requests coming from only one computer. e.g. You'd have the piece of software installed on your computer and any request you made from that computer would be affected. When testing multiple, black-boxed devices (*e.g. an iPhone, a Google Nexus, and a BlackBerry 9800*) this scenario wouldn't work. So doing what I do tend to do I built my own solution. Because of  how [shim][4] and [Adobe Shadow][5] work I decided to use an extra Mac that we had lying around as a WiFi access point. That way we could still use those tools and I could control the network speeds of the requests coming from our devices. Also, if it was set-up correctly, any of our designers could sit at their desks, testing and modifying their code, and update the network speed "on the fly." So with that…

## Introducing Throttle

[Throttle][6], [available on GitHub][6], is a simple [node.js][7] app that allows you to simulate poor network connections (e.g. like a cellular connection) so you can test how your websites will perform. For example, testing a responsive website on a poor 3G connection without actually having to have a poor 3G connection. To use Throttle simply connect your Mac to ethernet, share that network connection via Airport, turn on Throttle, and any device connected to that WiFi access point will then be throttled to the the network speed you specify via a web-frontend. If you don't have node.js on your computer don't fret. It's very easy to install so you can get Throttle up and running quickly.

It's important to note that Throttle was designed to be used in conjunction with a device lab and products like shim or Adobe Shadow where a shared connection is expected. That has definitely influenced its design and test cases.

Throttle has some very simple features:

*   Web-based app so it can be accessed & updated from any connected device or computer
*   Modify download network speeds for connected devices
*   Modify upload network speeds for connected devices
*   Modify the latency, or delay, in the network connection for connected devices
*   Handy presets to quickly switch between network types
*   The machine Throttle is installed on still has a full-speed Internet connection
*   Works nicely with [Adobe Shadow][5]. I want it to get it to work with a stock install of [shim][4].

<div>
  <p>
    <a href="https://github.com/dmolsen/Throttle">Directions for setting up and using Throttle</a> are now available on the project's GitHub repo. You can <a href="http://dmolsen.com/throttle-screen.png">check out a screenshot</a> to <a href="http://dmolsen.com/throttle-screen.png">see what you'll be getting</a> if you install Throttle. Throttle started out as a hack to <a href="https://github.com/marstall/shim/">shim</a> so thanks to that project and the team at Boston Globe for the inspiration. Throttle uses <a href="http://twitter.github.com/bootstrap/">Twitter Bootstrap</a> and <a href="http://glyphicons.com/">Glyphicons</a> for design elements.
  </p>
  
  <p>
    If you have any suggestions, criticisms or thoughts on Throttle please feel free to share them in the comments. I'm hopeful that I can get the current presets updated to appropriately reflect common connection speeds. I'm definitely open to suggestions for making that part of the system better.
  </p>
</div>

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/2012/06/26/how-to-build-a-device-lab-part-1/
 [2]: http://twitter.com/guypod
 [3]: http://www.slideshare.net/guypod/the-mobile-difference-in-numbers
 [4]: https://github.com/marstall/shim/
 [5]: http://labs.adobe.com/technologies/shadow/
 [6]: https://github.com/dmolsen/Throttle
 [7]: http://nodejs.org/