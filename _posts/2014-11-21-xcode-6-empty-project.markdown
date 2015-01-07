---
layout: post
title:  "Create an Empty iOS Project in Xcode 6"
date:   2014-11-21 17:35:00
categories: news update xcode ios
---

Every major release of Xcode or iOS Apple may take something away. This time they have taken the empty project template away. They seem to be pushing storyboards a little harder on us. No worries, if you use nibs like I do then we'll have to set up our own empty project.

Start off by launching Xcode 6 and select "Single View Application" then hit next and fill in your details.

![Single View Application]({{ site.url }}/assets/posts/2014-11-21-xcode-6-empty-project-0.png)

Find `Main.storyboard`, right-click it, delete and press the "Move to Trash" option.

![Delete Main.storyboard]({{ site.url }}/assets/posts/2014-11-21-xcode-6-empty-project-1.png)

Now look for `Info.plist` and look for the key `Main storyboard file base name`. Delete that row (key/value).

![Delete key value]({{ site.url }}/assets/posts/2014-11-21-xcode-6-empty-project-2.png)

Now to make it all work we'll be adding some code you're probably already familiar with. Locate `AppDelegate.swift` (`AppDelegate.m`) and add the following code:

{% highlight swift linenos %}
func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool {
    self.window = UIWindow(frame: UIScreen.mainScreen().bounds)

    // do your thing

    self.window?.backgroundColor = UIColor.whiteColor()
    self.window?.makeKeyAndVisible()
    return true
}
{% endhighlight %}

Run your project and you should be good to go. Hope that helps.
