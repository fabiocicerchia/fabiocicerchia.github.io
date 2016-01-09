---
layout:     post
title:      "Branching Model: clean-up those repos"
date:       2014-08-08 00:00:00
categories: coding-standards
tags:       svn, git, branches, flow, tags, versioning
comments:   true
permalink:  branching-model-clean-up-those-repos
---

Usually most rookie developers don't use a VCS (Versioning Control System), like
[SVN](https://subversion.apache.org/) or [GIT](http://git-scm.com/), in this
post I won't talk about the benefits of using one. This post is dedicated to
who's already using a VCS without using a branching model.

So, what's a branch? A branch is a **separate development line**, where you or
your team can work on to develop a single functionality or even an entire
release.
This line is separated from the rest in order not to mix unfinished
functionalities and avoid to push them to the main line or deploy them in
production.

![](http://nvie.com/img/2009/12/bm002.png)

The solution is having two or more distinct lines (aka branches) so your team
can work on those lines of development without interfering with each other.

![](http://nvie.com/img/2009/12/Screen-shot-2009-12-24-at-11.32.03.png)

The images above are referring to the
[Git Flow](http://nvie.com/posts/a-successful-git-branching-model/).

Generally, the common sense dictate to have the following branches:

 * master / trunk
 * development branches
 * tags

In git the tags are not actually physical branches like in SVN but just
**snapshots**, as what they are supposed to be.

The `master` / `trunk` must have the **stable version**, generally the latest
version.  
It's highly recommended to tag it in order to have an _archive_ of each deployed
version (e.g. useful in case you need to _rollback_).  
As suggestion the master contains only the stable version merged from the
development branches, avoiding to commit direct into it keeps the history tidy
and clean.  
The dev branches contain the **unstable code** which is under development. Quite
often it's possible to have a branch for each version, in case of bug fixing or
maintenance.

[Juan Batiz-Benet](http://juan.benet.ai/) created a
[gist](https://gist.github.com/jbenet/ee6c9ac48068889b0912) in which he's
explaining this simple model, that I'm quite sure it's used by many developers
without even being aware of it.

There are several different branching model, and most of the time you are
already using one.  
At the moment there are mainly two ones:

 * [Git Flow](http://nvie.com/posts/a-successful-git-branching-model/)  
   The general idea is to have several branches, each for a different purpose:
   `master`, `develop`, `feature`, `release`, and `hotfix`.
 * [GitHub Flow](https://guides.github.com/introduction/flow/index.html)  
   The general idea is just to have two branches: `master` and descriptive
   branches for the functionalities you are working on.

I recommend to _start with a simple model_, and then (only if you really need)
move towards a _more complex one_.