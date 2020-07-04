---
layout: post
title: OSX Yosemite Login Wallpaper
date: '2015-04-29T20:02:00.000-05:00'
author: Steve McMillin
tags:
- Customization
- OS X
- Branding
- User Experience
- Wallpaper
- Yosemite
modified_time: '2017-01-10T18:19:25.611-06:00'
blogger_id: tag:blogger.com,1999:blog-499912413894377040.post-9151477339238412425
blogger_orig_url: http://ai.untitledindustries.net/2015/04/osx-yosemite-login-wallpaper.html
---

Want to customize the login background of your Mac? Maybe you want to brand it with your company wallpaper or have it match the wallpaper that the user sees when they log in. Well, Apple has made this really simple to do in Yosemite with a single file change.
<!--more-->
1.  Get a copy of the image you would like use.
2.  Name it **com.apple.desktop.admin.png**
3.  Copy it to **/Library/Caches**
4.  You should probably backup the original in here if you ever want to revert to it.
5.  Logout or reboot the machine.
6.  All done!

I've made an utility that can be installed on machines to point them to a specific image saved on a web accessible method to set them all to that same image on the login window. This is still a work in progress, so be careful which machines you install it on.
https://github.com/Nesteph/LW-Changer