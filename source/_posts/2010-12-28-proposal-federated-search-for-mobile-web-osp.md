---
title: 'Proposal: Federated Search for Mobile Web OSP'
author: Dave Olsen
layout: post
permalink: /2010/12/28/proposal-federated-search-for-mobile-web-osp
categories:
  - Mobile Web OSP
tags:
  - federated search
  - mobile web osp
  - search
---
This post is similar to my [proposal for content adapters][1]. It's an attempt to get some feedback on a big-ish change to the system from interested parties. One of the features that I really like in the [Harvard mobile site][2] is the search box on the main page that allows you to quickly search across the multiple sources of data that are found on their mobile site. With the addition of the Content Adapters I think I have the basic building blocks for deploying a similar feature.

## Defining Federated Search

Wikipedia does a great job defining [federated search][3]:

> *Federated search* is an [information retrieval][4] technology that allows the simultaneous search of multiple searchable resources. A user makes a single query request which is distributed to the [search engines][5] participating in the federation. The federated search then aggregates the results that are received from the [search engines][5] for presentation to the user.

At the end of the day it's a pretty straightforward concept with, what I think is, an ugly name.

## How Federated Search Works

Below is a graphic showing how federated search is currently working in my local copy of [Mobile Web OSP][6]. It's a bit pared down filesystem-wise so don't worry about that part. Note that in Mobile Web OSP 2.5 there will now be an info.yml file to manage minor configuration options as well as identify the name and version of modules for the "easy setup" process.

<img  title="federatedsearch" src="/wp-content/uploads/2010/12/federatedsearch.jpg" alt="" />

Why all the checking of info.yml files? I'd like to make this set-up "turn-key" as much as possible. So basically if you create a module that supports federated search via federated.php all you have to do is add one flag to the info.yml file and you're all set. I'm really trying to avoid a lot of cross-module configuration whenever possible. I think the performance issue of checking the file system on each request is offset by the very low usage most sites get. At some point this feature could also be updated to use a cache system.

## Example Code

Here are some gists for the code behind various parts of the set-up. Hopefully it's fairly straightforward.

*   [The main search file][8] (*step #1 above*)
*   [The map module federated search script][9] (*step #3 above*)
*   [The map module federated search template][10] (*step #4 above*)

And for the actual directory layout it looks like this:

*   map/ 
    *   adapters/
    *   federated.php
    *   info.yml
    *   templates/ 
        *   basic/ 
            *   federated.html
        *   touch/
        *   webkit/
*   search/ 
    *   index.php
    *   templates 
        *   basic/
        *   touch/
        *   webkit/

## What Do You Think?

So I'm curious what people think. Seem like a workable solution? Would it make your lives easier? Having implemented the example I really like it but I'm sure their are still some issues to work out.

**Updated January 2, 2011: **The [initial commits][11] for this feature have been made. Calendar and map are the only modules supported at the moment. Quite a bit of work related to tweaking the look & feel for the set-up are still required. From the above example the `info.yml` file requirement has been removed and a cache mechanism for performance issues has been added.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/?p=154
 [2]: http://m.harvard.edu/about/
 [3]: http://en.wikipedia.org/wiki/Federated_search
 [4]: http://en.wikipedia.org/wiki/Information_retrieval "Information retrieval"
 [5]: http://en.wikipedia.org/wiki/Search_engine "Search engine"
 [6]: http://mobilewebosp.pbworks.com/
 [7]: http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/12/federatedsearch.jpg
 [8]: https://gist.github.com/757673
 [9]: https://gist.github.com/757676
 [10]: https://gist.github.com/757677
 [11]: https://github.com/dmolsen/MIT-Mobile-Web/compare/ca1464bcc6...8358e7bd74