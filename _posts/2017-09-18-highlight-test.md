---
layout: post
title: Highlighting Ruby Code
date: '2017-09-18T14:46:00.000-05:00'
author: Steve McMillin
tags: 
modified_time: '2017-09-18T14:46:53.812-05:00'
blogger_id: tag:blogger.com,1999:blog-499912413894377040.post-3127034549186106330
blogger_orig_url: http://ai.untitledindustries.net/2017/09/configure-ondemand-vpn-connection-for.html
---

Testing out ruby syntax highlighting
<!--more-->
{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}