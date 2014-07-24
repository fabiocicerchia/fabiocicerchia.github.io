---
layout:     post
title:      "Versioning Numbers, make them meaningful"
date:       2014-07-25 00:00:00
categories: coding-standards
tags:       software semantic versioning
comments:   true
permalink:  versioning-numbers-make-them-meaningful
---

The version number itself, and more generally the way you manage it, is most of
the time underestimated, because it's considered something trivial.  
It is used to give a chronological order to the software releases and it conveys
the useful information about the state and the impact of the release.

I can think only of two major way to assign a version number:

 * `MAJOR.MINOR.PATCH[-STABILITY]`
 * `YEAR.MONTH.DAY` [^1]

Obviously there are several ways of customising those to your own needs, and you
can find everywhere different, non-standard, version numbers every day being
used.
 
But, personally, I prefer the following structure and I'd recommend it to
everyone:

`MAJOR.MINOR.PATCH[-STABILITY]`

The rules are quite straight-forward:

 * increase `MAJOR` when releasing something that is NOT backward compatible
 * increase `MINOR` when releasing something that is backward compatible
 * increase `PATCH` when releasing a bug fix (obvs backward compatible)
 * the stability follows this order:
   1. `alpha`
   2. `beta`
   3. `dev`
   4. `rc`

Usually I never bother to use `alpha` and `beta` because they are so unstable
and so frequently updated that it's not worth the time to create a tag and
release it, I'd rather release a `dev` one.

I also found out that there is even a [manifesto](http://semver.org/) for the
versioning scheme I'm using and promoting.

However, this is not preventing you anyhow to assign to your release a codename.

This could be a solution to avoid problems when deciding which version to use,
recognising at first glance if the release is stable or not, and especially
be aware whether it's backward-compatible.  
Still, do not ever trust blindly an external dependency.

[^1]: [Ubuntu](http://en.wikipedia.org/wiki/List_of_Ubuntu_releases)