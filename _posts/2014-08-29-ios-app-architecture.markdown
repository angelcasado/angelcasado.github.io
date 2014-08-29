---
layout: post
title:  "iOS App Architecture"
date:   2014-08-29 14:05:00
categories: ios apps mobile architecture
---

There has been a lot of talk in the past few weeks about how Apple isn’t doing enough to lead app architecture. Many point to Apples sample projects being a bad example for the community. I would argue that the point of these examples is to be just that, an example. Brief and to the point to get the concept across.

If you’re a reader of [objc.io](http://www.objc.io/) it was been addressed since the very [first issue](http://www.objc.io/issue-1/) and again in the [thirteenth issue](http://www.objc.io/issue-13/). They discuss topics on keeping your view controller light, subclassing, separating code in to their own classes, and a lot more.

Even after reading all of this information and diving deeper in to the topic, it still felt like something was missing. My search for more information led me to [this blog post](http://oleb.net/blog/2014/06/apples-take-on-app-architecture/) by Ole Begemann. In it he summarizes WWDC 2014 Session 232 called [Advanced User Interfaces with Collection Views](https://developer.apple.com/videos/wwdc/2014/) by Apple engineer Jeff Watkins. At first, reading the title would make it seem like this session has nothing to do with architecture and I was wrong. I couldn’t believe I had overlooked such an important session.

The entire session dives into the process and thinking behind displaying complex data in collection views. Jeff uses the iTunes Connect app as an example. By creating separate reusable data source classes, the team solved the bloated view controller problem while making the app modular. For example data that was displayed by segmented control was put in to its own "segmented data source class" composed of child data source classes. These classes were also responsible for fetching their own data, handling errors, and displaying a spinner while loading.

While I could go in to greater detail, the Jeff and Ole do a way better job at explaining it. There is an hour worth of content, which I highly recommend you watch. It even comes with [sample code](https://developer.apple.com/wwdc/resources/sample-code/) to dissect and implement in your projects today.
