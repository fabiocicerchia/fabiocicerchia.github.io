---
layout:     post
title:      "JS Events: how to get all of them"
date:       2013-12-03 11:23:00
categories: programming
tags:       javascript events dom phantomjs nodejs
comments:   true
permalink:  js-events-how-to-get-all-of-them
---

The main problem is because of the way the browser manage the events.

I've developed this plain JS class because I was facing a huge problem while
working on [salmonJS](http://salmonjs.org). I was trying to collect all the
events bound to the DOM elements.

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
are handled internally by the browser and there is no trace in the DOM of those.

This is my personal solution to this problem, overriding the default behaviour
at the beginning of the page load, so nothing else can try to bind an event
before initialise the "interceptor".

There is nothing to be configured to make it working, just include it in your page
before EVERYTHING else.

You can collect at any time the events just calling:

{% highlight js linenos %}
var events = eventContainer.getEvents();
{% endhighlight %}

{% gist fabiocicerchia/7116129 %}
