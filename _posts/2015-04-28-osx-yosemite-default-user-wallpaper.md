---
layout: post
title: OSX Yosemite Default User Wallpaper
date: '2015-04-28T19:53:00.000-05:00'
author: Steve McMillin
tags:
- Customization
- OS X
- Branding
- User Experience
- Wallpaper
- Yosemite
modified_time: '2015-04-27T20:05:50.335-05:00'
blogger_id: tag:blogger.com,1999:blog-499912413894377040.post-6463982074223833229
blogger_orig_url: http://ai.untitledindustries.net/2015/04/osx-yosemite-default-user-wallpaper.html
---

Have you wanted to brand your OSX machines for your end user experience, but still let the end user be able to customize their wallpaper? In OSX Yosemite (10.10.*), this is pretty simple to accomplish.
<!--more-->
1.  Get a copy of the image you would like use.
2.  Name it **<u>DefaultDesktop.jpg</u>**
3.  Copy it to **<u>/System/Library/CoreServices</u>**

All new users (or if you wipe accounts at logout), will now use the image you placed here as the default wallpaper when logging in. At least until Apple decides to change the default wallpaper location, or replace your image.

The benefit of using this method rather than MCX/MDM, is that the end user can still customize the wallpaper to their liking, while you still get to put some branding in right out of the box.