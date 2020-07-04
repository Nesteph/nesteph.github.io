---
layout: post
title: Configure An OnDemand VPN Connection For OSX or iOS
date: '2017-09-18T14:46:00.000-05:00'
author: Steve McMillin
tags: 
modified_time: '2017-09-18T14:46:53.812-05:00'
blogger_id: tag:blogger.com,1999:blog-499912413894377040.post-3127034549186106330
blogger_orig_url: http://ai.untitledindustries.net/2017/09/configure-ondemand-vpn-connection-for.html
---

Basically this config profile configures your device such that whenever a domain specified in the list (starting at line 67) is contacted, it will attempt a lookup using the DNS servers specified. If the DNS servers specified aren't reachable, it will attempt to establish the connection. You <i>could</i> use DNS servers that don't exist to get a permanent always on connection, but I would not recommend that as you can't troubleshoot easily and the non-existent servers could be created at some point by another party.

<!--more-->
Save this xml as a .mobileconfig and replace the parts with $TEXT with the relevant info.
{% gist nesteph/4ad1806cd05539b83272bf1dda796ce6 %}