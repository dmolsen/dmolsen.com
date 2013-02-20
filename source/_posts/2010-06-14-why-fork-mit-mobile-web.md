---
title: Why Fork MIT Mobile Web?
author: Dave Olsen
layout: post
permalink: /2010/06/14/why-fork-mit-mobile-web
categories:
  - Mobile Web OSP
tags:
  - fork
  - knife
  - mit mobile web
  - mobile web osp
  - spoon
  - spork
---
Late last week I received two questions relating to MIT Mobile Web and my fork of it, [Mobile Web OSP][1]. I figured it'd be good to address them publicly since my response may be of interest to others as well.

## Why Did You Fork MIT Mobile Web?

I forked [v0.9 of MIT Mobile Web][2] for a few reasons:

*   it was an absolute bear to set-up & configure,
*   it was obviously written with only one institution in mind (*which is fine*) and had no real thought to customization, &
*   it had zero documentation

The original version of MIT Mobile Web (they've now released [MIT Mobile Web v2.0][3] with some documentation) felt more like a code dump than an organized project that other higher education institutions could take advantage of. The original project didn't even have a list of requirements. I spent a fair bit of time adding a global configuration, working to use resources like Google Maps to make the project more generic, and mucking with the module set-up so other schools might have a better base to work from. I then spent a lot of time [writing up documentation][1] so users might have a better understanding of what was going on. So what I thought I had at that point was a cleaned up, documented "upgrade" of MIT Mobile Web. I don't think I really changed a lot of the core structure.

As we moved internally towards version 2 of Mobile Web OSP, especially with our addition of [jQTouch][4] and themes, I realized that I had moved from an "upgraded" version of MIT Mobile Web to a true fork of the project. It's not exactly what I wanted but that's what happened.

## Are You Going to Merge Your Changes Back to the Original Project?

I don't know. That's the honest answer. There has been interest from myself and the maintainers of the MIT project to discuss the differences and how we can move forward together but that discussion hasn't happened yet. As time moves on we keep moving further away from each other especially in how we're implementing themes and templates. So there's interest… I'm just not sure if we haven't already moved past where we can easily merge back into one project. We've both already moved onto version 2 of our respective codebases.

## More Forks…

One interesting thing that I've found with this project is that any school using a framework, be it MIT's code or Mobile Web OSP, will essentially create a fork. Each school, their needs, and access to content is so unique that I have a feeling that a lot of schools will go crazy customizing a framework. At least their are two good ones to start from.

 [1]: http://mobiweb.pbworks.com/
 [2]: http://sourceforge.net/projects/mitmobileweb/
 [3]: http://github.com/zootsuitbrian/MIT-Mobile-Framework
 [4]: http://www.jqtouch.com/