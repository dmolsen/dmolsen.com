---
title: 'Proposal: Content Adapters for Mobile Web OSP'
author: Dave Olsen
layout: post
permalink: /2010/12/15/proposal-content-adapters-for-mobile-web-osp
categories:
  - Mobile Web OSP
tags:
  - content adapters
  - mobile web osp
  - proposal
---
One of the interesting things to come out of my [State of Mobile Web OSP post][1] was some comments related to how content sources can be more easily integrated into the system. For example, our set-up of [Mobile Web OSP][2] uses Google Calendar to power our calendar module. Others may have institutional systems that they'd like to access directly or through some other software's API set-up. At the moment you'd have to rip out the guts of the calendar module to implement your own calendar source. Then, as new features are released, you might be stuck not being able to easily upgrade. With that in mind I offer here a sketch for Content Adapters.

## Defining Content Adapters

Content Adapters are a set of standard functions that can be called from a specific module. These functions then talk to the appropriate data source and then return the data from this source in an agreed upon format to be used by the templates for the module. I hope that each school will be able to develop their own Content Adapters. This should allow the core of modules as well as the templates to stay relatively intact without needing much modification.

## How Content Adapters Work

Below is a graphic showing how Content Adapters work. It's a bit pared down filesystem-wise so don't worry about that part. Note that in Mobile Web OSP 2.5 there will now be an info.yml file to manage minor configuration options as well as identify the name and version of modules for the "easy setup" process.

<img title="content adapter layout" src="/wp-content/uploads/2010/12/adapter.png" alt="" />

## Example Code

Here are some gists for the code behind various parts of the set-up. Hopefully it's fairly straightforward.

*   [category.php example][4]
*   [info.yml example][5]
*   [adapter.php example][6] (*google calendar focused*)

I won't show the template only because it's really fugly and it should be pretty self-explanatory at this point what it'd look like.

And for the actual directory layout it looks like this:

*   calendar/ 
    *   adapters/ 
        *   google_calendar/ 
            *   adapter.php
    *   category.php
    *   info.yml
    *   templates/ 
        *   basic/
        *   touch/
        *   webkit/

## What Do You Think?

So I'm curious what people think. Seem like a workable solution? Would it make your lives easier? Having implemented the example I really like it but I'm sure their are still some issues to work out. It definitely forced me to DRY my code a little bit.

**Update as of December 20, 2010:** I've had zero feedback on this idea. As such I'm going to go with it and if it needs to be tweaked later hopefully I can do so.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/?p=149
 [2]: http://mobilewebosp.pbworks.com/
 [3]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/12/adapter.png
 [4]: https://gist.github.com/742389
 [5]: https://gist.github.com/742392
 [6]: https://gist.github.com/742403