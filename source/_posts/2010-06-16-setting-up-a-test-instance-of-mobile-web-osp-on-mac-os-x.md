---
title: Setting Up a Test Instance of Mobile Web OSP with a Custom Hostname on Mac OS X
author: Dave Olsen
layout: post
permalink: /2010/06/16/setting-up-a-test-instance-of-mobile-web-osp-on-mac-os-x
categories:
  - Mobile Web OSP
tags:
  - apache
  - hostname
  - install
  - mac
  - mobile web osp
  - pico
  - terminal
---
Another user email prompted this post so if you have a question feel free to [drop me a line][1].

The following directions mirror how I have [Mobile Web OSP][2] set-up on my own Mac. It's pretty straightforward to set-up.

**Special Note:** The default install of PHP on Mac OS X may not support short tags (e.g. `<? ?>`) wrapping PHP code and rather expect `<?php ?>`. Short tags are used quite a bit so you will want to turn short tags on. This is something I need to address in a future update to the system.

## Downloading Mobile Web OSP

I'm not going to go into too much depth with this. [Use the solution][3] that best suits you. Just make sure you know where you installed it. You should also finish configuring the project at this time as well.

## Setting Up m.test.edu

I like to set-up custom hostnames on my machine for my projects. It's just easier for me to remember. Also, since all of our projects are delivered on their own subdomains I know all the paths and what not will work correctly. To add a custom hostname for your project do the following:

1.  Open "Terminal" (it's in Applications > Utilities)
2.  Type: `sudo pico /etc/hosts`
3.  When prompted type in the password you log into your Mac with
4.  Add the following to the end of the file: `127.0.0.1 m.test.edu`
5.  Type: `control+x`
6.  Type `y` to save the changes

You've just added the hostname m.test.edu to point at your local machine.

## Configuring Apache

Now that you have a custom hostname you have to make sure that Apache will answer to the added hostname on your machine. To do so do the following:

1.  Open "Terminal"
2.  Type: `sudo pico /etc/apache2/extra/httpd-vhosts.conf`
3.  If prompted type in the password you log into your Mac with
4.  Add [this gist][4] to the end of the file. *Make sure the path to the project for DocumentRoot and the Directory directive are correct.*
5.  Type: `control+x`
6.  Type `y` to save the changes
7.  Type `sudo apachectl restart` to restart Apache
8.  Go to http://m.test.edu in your browser

So now you should be all set with a test instance of Mobile Web OSP answering to it's own hostname on your Mac.

 [1]: http://www.dmolsen.com/mobile-in-higher-ed/?page_id=3
 [2]: http://mobiweb.pbworks.com/
 [3]: http://mobiweb.pbworks.com/Downloading-and-Installing
 [4]: http://gist.github.com/436747