---
layout:     post
title:      "Browser Fingerprinting: There's no place where you can hide"
date:       2013-10-01 09:41:00
categories: privacy
tags:       javascript browser privacy fingerprint
comments:   true
permalink:  browser-fingerprinting-there-s-no-place-where-you-can-hide
---

[EFF](https://www.eff.org/), The Electronic Frontier Foundation, did a research
about the users' privacy and how it is possible to identify the user in a quite
unique way.  
The concept is based on gathering as much information as possible, like user
agent (browser and version), resolution, plugins installed, timezone, language,
and so on to create a message digest to identify the user / user's device in an
accurate way.

This means that disabling the cookies is not enough to avoid this kind of
identification.
So you can still be a target of web tracking, mainly for marketing and
commercial purposes.

The full article is available at "[A Primer on Information Theory and Privacy](https://www.eff.org/deeplinks/2010/01/primer-information-theory-and-privacy)".

So fascinated by this experiment I've tried to create just for fun something
similar to generate a "unique" fingerprint.

You can test my version on [<i class="fa fa-jsfiddle"></i> JSFiddle](http://jsfiddle.net/fabiocicerchia/P9Rd9/).

You can check the code here below:

{% gist fabiocicerchia/6775541 %}

But if you only think all the information the Google has got during the years
based on what you have done on Internet, it's enough to track and predict your
behaviour without too many problems.