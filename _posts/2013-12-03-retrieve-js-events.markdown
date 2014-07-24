---
layout:     post
title:      "Retrieve JS Events: how to get all of them"
date:       2013-12-03 11:23:00
categories: programming
tags:       javascript events dom phantomjs nodejs
comments:   true
permalink:  retrieve-js-events-how-to-get-all-of-them
---

I was trying face an apparently huge problem, collect all the events bound to
the DOM elements.  
Then I realised that the main obstacle was the browser, yes the browser.  
Because of the way the browser manage the events.

So I started my research about it, nothing came from Google or StackOverflow.

This answer made me think and for a second I was about to give up on that:

> Event handlers attached using DOM Level 2 Events addEventListener methods and
> IE's attachEvent cannot currently be retrieved from script at all. DOM Level 3
> once proposed element.eventListenerList to get all listeners, but it is
> unclear whether this will make it to the final specification. There is no
> implementation in any browser today.
>
> -- <cite>[bobince](http://stackoverflow.com/a/2623352/888162)</cite>

There are few ways to bind an event we should focus on:

 * [`on*`](http://www.w3.org/TR/html401/interact/scripts.html#h-18.2.3) HTML attribute
 * [`element.addEventListener`](https://developer.mozilla.org/en/docs/Web/API/EventTarget.addEventListener)
 * [`element.attachEvent`](http://msdn.microsoft.com/en-us/library/ie/ms536343(v=vs.85).aspx)

The last 2 are not possible to be retrieved without some workounds because they
are handled internally by the browser and they don't leave any trace in the DOM.

So I've developed a plain JS class because I was facing this problem while
working on [salmonJS](http://salmonjs.org), a js-compatible web spider.
I was working with PhantomJS (and I believe it works fine with CasperJS as
well) and I came with this solution which seems to be the most appropriate one.

My personal approach to that was overriding the default behaviour at the
beginning of the page load, so nothing else can try to bind an event before
initialise the "interceptor".


There is nothing that needs to be configured to make it working, just include it
in your page before EVERYTHING else.

You can collect at any time the events just calling:

{% highlight js linenos %}
var events = eventContainer.getEvents();
{% endhighlight %}

{% gist fabiocicerchia/7116129 %}
