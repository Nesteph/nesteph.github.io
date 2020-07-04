---
layout: post
title: Block OUs From Emailing Certain Groups in Google Apps
date: '2015-03-27T19:18:00.002-05:00'
author: Steve McMillin
category:
- Work
tags:
- Gmail
- Google Apps
- OU
- Restricted Emails
- Google Groups
- Google Admin Console
modified_time: '2015-03-27T19:18:26.111-05:00'
thumbnail: http://2.bp.blogspot.com/-dILab46FRDw/VRXhiRrfZ6I/AAAAAAAAFs8/P3zM8r9mdPs/s72-c/2015-03-27_17-26-27.png
blogger_id: tag:blogger.com,1999:blog-499912413894377040.post-6559443819272437961
blogger_orig_url: http://ai.untitledindustries.net/2015/03/block-ous-from-emailing-certain-groups.html
---

Recently I was tasked with figuring out a way to limit our student accounts from being able to send emails out to a large portion of our mailing lists/groups. The first option, blocking all emails except from owners and managers of the groups worked out great! Except they were the only users that could email those lists. Not a great fit, but do-able.
<!--more-->

<figure style="float:right">
	<img src="{{ site.baseurl }}/images/posts/2015-03-27-block-ous-from-emailing-certain-groups/example_ou_setup.png"/>
	<figcaption>Example OU Layout</figcaption>
</figure>
After some poking around and reading up a bit more on the control panel, I was able to get the settings figured out to allow all of our staff to email all of our mailing lists including the student lists (which were locked down from the first option as a band-aid fix), while blocking the students from emailing lists we specified. 

This guide assumes that you have all your students by themselves in either one OU or an OU with sub-OUs by some grouping scheme and the groups are named by their graduation year, meaning if the OU is "15", then the group is also named that and the email for it is "15@domain.com"

First thing is first, make sure the group is set to allow "Owners of the Group, Managers of the Group and All Organization Members" to post in the Basic Permissions of the group(s) itself. This will allow anyone in the domain to email this group. We are going to limit this elsewhere.

<figure style="float:center">
	<img src="{{ site.baseurl }}/images/posts/2015-03-27-block-ous-from-emailing-certain-groups/basic_posting_perms.png"/>
	<figcaption style="text-align: center">Basic Group Posting Permissions</figcaption>
</figure>

Second, check your Advanced Settings for Gmail for the top level OU (the highest one), in my example, this is the Students OU, you want to block. We are going to be looking at the Compliance section here. In this section, we are going to add a Content Compliance.

<figure style="float:center">
	<img src="{{ site.baseurl }}/images/posts/2015-03-27-block-ous-from-emailing-certain-groups/content_compliance.png"/>
	<figcaption style="text-align: center">Gmail Compliance section of the top level OU</figcaption>
</figure>

We are going to give this a description so we recognize what it is if we ever need to come back and modify it. Something along the lines of "Mailing List Restrictions" should be fine. We are going to have this apply to "Outbound" and "Internal - sending" emails. The reason I would mark both of these is if you use special routing tables, multiple domains, or domain aliases. If you only have one domain, you can still safely mark both options.

<figure style="float:center">
	<img src="{{ site.baseurl }}/images/posts/2015-03-27-block-ous-from-emailing-certain-groups/content_compliance.png"/>
	<figcaption style="text-align: center">Content Compliance Settings</figcaption>
</figure>

Next, we need to add an expression or rule to match off of. The expression we are going to build is an **Advanced content match,** the Location is **Any envelop recipient**, and the Match type is **Matches regex**. Once these options are selected, the logic behind the filter can be filled in and tested. In the Regexp field, enter one of the following styles and then hit Save. Repeat as necessary for your lists.


* `^[0-9][0-9]@domain.com` - All emails in the form of _@domain.com_ trigger the rule.
* `^[0-9][0-9]@domain.(com|org|k12.edu)` - All emails in the form of _@domain.com_, _@domain.org_, or _@domain.k12.edu_ trigger the rule.
* `^[0-9][0-9]@(example|domain).com` - All emails in the form of _@example.com_ or _@domain.com_ trigger the rule.

<figure style="float:center">
	<img src="{{ site.baseurl }}/images/posts/2015-03-27-block-ous-from-emailing-certain-groups/testing_regexp.png"/>
	<figcaption>Testing the Regexp to make sure it works</figcaption>
</figure>

This can be built out to your specific setup easily with the use of **OR** logic by using `(phrase 1|phrase 2|phrase 3)` to substitute multiple items in the same rule. An example Regexp that catches all email to your student lists could be something along the following (this is assuming that you have these groups set up with the appropriate grades as members in them):

* `^(hs|ms|is|es)-students@(domain1.k12.edu|domain2.k12.edu)`

This would trigger on the following addresses on both domain1.k12.edu and domain2.k12.edu:
* hs-students@domains
* ms-students@domains
* is-students@domains
* es-students@domains

Finally, choose whether you want to **Modify**, **Reject**, or **Quarantine** the message. For this guide's purposes, Reject message will be selected and an appropriate rejection notice applied. After that, add the setting using the Add setting button and then Save Changes.

<figure style="float:center">
	<img src="{{ site.baseurl }}/images/posts/2015-03-27-block-ous-from-emailing-certain-groups/compliance_match_options.png"/>
	<figcaption>Compliance rule with a custom rejection notice added</figcaption>
</figure>

Congratulations! All the accounts in the OU (and sub-OUs) that you applied this to, should no longer be able to email the lists you specified. The added bonus of this is that as you add additional OUs/Groups with that numbering scheme, you won't need to modify this rule as they will automatically be restricted from emailing that list.

<span style="font-size: x-small;">**Note:** I still need to test whether the ^ (signifies that the expression must begin with the following phrase) is necessary. I believe it is as [Google's documentation](https://support.google.com/a/answer/1346934?hl=en) states that Any envelope recipient compares against the rule one at a time and you don't want emails sent to roger09@domain.com from someone in the OUs getting rejected. Google's Regexp documentation [here](https://support.google.com/a/answer/1346938?hl=en).</span>