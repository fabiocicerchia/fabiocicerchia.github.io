---
layout:     post
title:      "Versioning Numbers: Let 'em be semantic"
date:       2014-07-22 00:00:00
categories: coding-standards
tags:       software semantic versioning
comments:   true
permalink:  versioning-numbers-let-em-be-semantic
---

The version number is most of the time underestimated. It is used to give a
chronological order to the software releases and it conveys the useful
information about the state and the impact of the release.

There are several way to version a release:

 * `MAJOR.MINOR[.BUILD[.REVISION]]`
 * `MAJOR.MINOR.PATCH[-STABILITY]`
 * `CURRENT.REVISION.AGE`
 * `YEAR.MONTH`, see [Ubuntu](http://en.wikipedia.org/wiki/List_of_Ubuntu_releases)
 * `ID`, see [Windows]()
 
Personally I prefer the following structure:

`MAJOR.MINOR.PATCH[-STABILITY]`

And apparently there is even a [manifesto](http://semver.org/) for this
versioning type.

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
and so frequently updated that it's not worth the time to create a tag, I'd
rather release a `dev` one.

This could be a solution to avoid problems when deciding which version to use.
This kind of confusion is on the end-user, and the end-user who cares most about
those version numbers quite often is the developer who needs to use a certain
library.

Still this doesn't mean you can't get confused by your own versioning number
scheme <i class="fa fa-smile-o"></i>

If you use non-sequential numbers make sure it's clear which one come first, the
first example that I can think of could be Windows ME and Windows 2000:
do you know which one is the most recent one?  
A solution could be the versioning system that Canonical is using for Ubuntu:
`YY.MM` (`year.month`)

We can see everything as a courtesy we can do each other to make our lives
easier.