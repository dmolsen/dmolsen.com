---
title: 'ua-parser-php v1.4.0 Released: Easier to Cron, Quick &#8220;redirect&#8221; Example, and UA updates'
author: Dave Olsen
layout: post
permalink:  /2012/05/21/ua-parser-php-v1-4-0-released-easier-to-cron-quick-redirect-example-and-ua-updates
categories:
  - Tools
tags:
  - browser detection
  - cron
  - ua-parser
  - ua-parser-php
---
I've pushed out [v1.4.0 of `ua-parser-php`][1]. `ua-parser-php` is the PHP library for the [official `ua-parser` project][2]. Why use `ua-parser`? If you need a simple library to slice & dice user agent strings into understandable components (*e.g. browser, OS, device*) then it's the project for you. `ua-parser-php` goes a step further by also attempting to categorize browsers as mobile, tablet, computer, or spider.

## Setting Up ua-parser-php With Cron

As the `ua-parser` team updates the [YAML file and its regular expressions][3] you will want to update your local copy of `regexes.yaml`. The easiest way to do this on a *nix system is to use [`cron`][4]. I've added some simple flags, `-silent` and `-nobackup`, to make it easier to set-up an intelligent `cron` job. `-silent` is very important and I highly encourage you to use the flag if you use `ua-parser-php` with `cron`. By default, `ua-parser-php` writes out process updates to the command line as it fetches the `regexes.yaml` file. When using `cron` this will end up as an email and will either fill the spool on the machine or your inbox.

So here are some examples of commands you can use with `cron`:

<div class="gist">
	<script src="https://gist.github.com/dmolsen/2762715.js"></script>
</div>

## Quick "redirect" Example

Because the PHP version of `ua-parser` supports extra browser categorizations like `isMobile` you can use `ua-parser-php` as the basis for a simple redirect script. The following should show just how easy it can be:

<div class="gist">
	<script src="https://gist.github.com/dmolsen/2762726.js"></script>
</div>

## Recent User-Agent Updates

Obviously, the big feature of `ua-parser` is matching user-agent strings and giving you usable data. The following user-agents have been added and tested:

*   Google Chrome Frame
*   Google Earth browser
*   Firefox Alpha builds
*   Raven for Mac browser (*aka Robin*)
*   Sogou Explorer
*   Tizen Browser (*aka SLP Browser*) from Samsung
*   WebKit Nightly builds (*though slightly pointless*)
*   better support for Firefox Mobile
*   better support for the Pale Moon browser
*   better support for Polaris 8.0
*   better support for Epiphany

Have you [tried out `ua-parser-php`][5] and found an incorrect match? Drop a note in the [`ua-parser` issue list on GitHub][6].

*Editor's note: I have no idea if ‘cron' can be used as a verb but, hey, what the hell. *

 [1]: https://github.com/tobie/ua-parser/tree/master/php
 [2]: https://github.com/tobie/ua-parser
 [3]: https://github.com/tobie/ua-parser/blob/master/regexes.yaml
 [4]: http://en.wikipedia.org/wiki/Cron
 [5]: http://uaparser.dmolsen.com/
 [6]: https://github.com/tobie/ua-parser/issues