---
title: 'Introducing ua-parser-php: Slicing &#038; Dicing User Agent Strings'
author: Dave Olsen
layout: post
permalink: /2012/01/30/introducing-ua-parser-php-slicing-dicing-user-agent-strings/
categories:
  - General
  - Tools
tags:
  - php
  - ua-parser
  - ua-parser-php
  - user agent
  - user agent parsing
  - yaml
---
**Update on May 2, 2012:** `<a href="https://github.com/dmolsen/ua-parser-php">ua-parser-php</a>` is now included in the [official `ua-parser` repository on GitHub][1].

**Update on February 11, 2012:** `<a href="https://github.com/dmolsen/ua-parser-php">ua-parser-php</a>` was updated to v1.0.0. The list of supported browsers and devices was greatly expanded. A number of bug fixes were also added by Bryan Shelton.

`<a href="https://github.com/dmolsen/ua-parser-php">ua-parser-php</a>` is a PHP-based pseudo-port of the `<a href="http://code.google.com/p/ua-parser/">ua-parser</a>` project. `ua-parser-php` is designed to parse a user agent string and return certain properties like browser name, OS version, and, in some cases, device name. `ua-parser-php` utilizes the user agents regex YAML file from `ua-parser` but otherwise uses its own set of properties to describe a browser, OS, and device. `ua-parser-php` was created as a new browser-detection library for the browser- and feature-detection library [Detector][2].

If you want, you can [test your browser against ua-parser-php][3]. As usual, [the code is available on GitHub][4].

## Usage

Using ua-parser-php is straightforward. Simply include it in your project, make the call to parse the user agent and you'll be returned an object with various properties of the user agent. Examples follow:

<script src="https://gist.github.com/dmolsen/1706269.js"></script><noscript>This GitHub gist is available at: [https://gist.github.com/dmolsen/1706269](https://gist.github.com/dmolsen/1706269)</noscript>

**NOTE:** Using this feature will overwrite a number of changes I've made to the `user_agents_regex.yaml` file included with the `ua-parser-php` distribution.

## Credits

Thanks to the [`ua-parser` team][5] for making the core data available to others so we can build our own solutions.

 [1]: https://github.com/tobie/ua-parser
 [2]: https://github.com/dmolsen/Detector
 [3]: http://uaparser.dmolsen.com/
 [4]: https://github.com/dmolsen/ua-parser-php
 [5]: http://code.google.com/p/ua-parser/people/list