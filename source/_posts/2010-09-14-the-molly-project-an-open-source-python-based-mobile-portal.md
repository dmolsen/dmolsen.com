---
title: 'The Molly Project: An Open Source, Python-based Mobile Portal'
author: Dave Olsen
layout: post
permalink: /2010/09/14/the-molly-project-an-open-source-python-based-mobile-portal/
categories:
  - Tools
tags:
  - framework
  - molly project
  - oxford
  - python
  - sakai
---
Interested in using an open source framework to develop your school's mobile presence but not thrilled about using PHP? Feel more comfortable with [Python][1]? Then the [Molly Project][2] might be right for you.

## The Molly Project

The Molly Project, developed by [University of Oxford][3] for [Mobile Oxford][4] and and now joined by [Oxford Brookes University][5], is open sourced under the terms of the [Academic Free License v3.0][6]. It's built on-top of [Django][7]. I'm not much of a Python guy so I can't get too much into the technical programming details but the list of available features is definitely compelling:

*   LDAP Support for directory searches
*   Z39.50 protocol support so it can interface with library information systems
*   OPML feeds for serving up podcasts
*   OpenStreetMap support for creating a mobile campus map
*   RSS support for displaying news & events
*   Google Search Appliance search
*   WebAuth and OAuth consumer authentication

The one feature that really interests me, though we don't have it here at West Virginia University, is the integration with [Sakai][8]. It currently supports access to the sign-up, evaluations and polls tools.

<img title="mobile_oxford" src="http://www.dmolsen.com/mobile-in-higher-ed/wp-content/uploads/2010/09/mobile_oxford.png" alt="" />

Like [Mobile Web OSP][9] Molly uses device detection to adapt the look & feel of the page to match a phone's capabilities. This means that you can deliver your information to the largest audience possible.

If you're interested in the project definitely visit [The Molly Project site][2] or their [mailing lists][10].

 [1]: http://www.python.org/
 [2]: http://mollyproject.org/
 [3]: http://www.ox.ac.uk/
 [4]: http://m.ox.ac.uk/
 [5]: http://www.brookes.ac.uk/
 [6]: http://www.opensource.org/licenses/afl-3.0.php
 [7]: http://www.djangoproject.com/
 [8]: http://sakaiproject.org/
 [9]: http://mobilewebosp.pbworks.com/
 [10]: http://sourceforge.net/mail/?group_id=309230