---
layout: post
title: Windows 7 Guest In Parallels 12 Not Using Host VPN DNS Servers
date: '2017-01-10T18:25:00.005-06:00'
author: Steve McMillin
tags: 
modified_time: '2017-01-11T08:02:18.391-06:00'
thumbnail: https://3.bp.blogspot.com/-qWW8O1548Z4/WHV3GS4C_8I/AAAAAAAAfiA/hBzsEJVlrhY1OzhxtgXgyd78atpQtVtegCEw/s72-c/step%2B2.png
blogger_id: tag:blogger.com,1999:blog-499912413894377040.post-364265120618483237
blogger_orig_url: http://ai.untitledindustries.net/2017/01/windows-7-guest-in-parallels-12-not.html
---

There seems to be a glitch with the virtual machine not getting the proper settings from the network even when all of the settings are configured on the host and in Parallels. If you follow these steps below it should get you up and running.<!--more-->

1.  Log in to the virtual machine.
2.  Click the **Windows** button in the lower left of the screen.

    <div class="separator" style="clear: both;">[![](https://3.bp.blogspot.com/-qWW8O1548Z4/WHV3GS4C_8I/AAAAAAAAfiA/hBzsEJVlrhY1OzhxtgXgyd78atpQtVtegCEw/s1600/step%2B2.png)](https://3.bp.blogspot.com/-qWW8O1548Z4/WHV3GS4C_8I/AAAAAAAAfiA/hBzsEJVlrhY1OzhxtgXgyd78atpQtVtegCEw/s1600/step%2B2.png)</div>

3.  Click **Control Panel** in the Start Menu.

    <div class="separator" style="clear: both;">[![](https://4.bp.blogspot.com/-CbtSV7x0-SM/WHV3yQ7B6pI/AAAAAAAAfiI/eRbi8hgB6qsaz5apu-0XoTiUUoxp1RtsgCEw/s320/step%2B3.png)](https://4.bp.blogspot.com/-CbtSV7x0-SM/WHV3yQ7B6pI/AAAAAAAAfiI/eRbi8hgB6qsaz5apu-0XoTiUUoxp1RtsgCEw/s1600/step%2B3.png)</div>

4.  Click **View network status and tasks** located under the **Network and Internet** section.

    <div class="separator" style="clear: both;">[![](https://3.bp.blogspot.com/-UTsXd2nL5aw/WHV3ypevMJI/AAAAAAAAfiI/BkHSATfLZ18cA_4_3pqZUuvGMfMBoHlbQCEw/s320/step%2B4.png)](https://3.bp.blogspot.com/-UTsXd2nL5aw/WHV3ypevMJI/AAAAAAAAfiI/BkHSATfLZ18cA_4_3pqZUuvGMfMBoHlbQCEw/s1600/step%2B4.png)</div>

5.  Click **Change adapter settings** in the sidebar.

    <div class="separator" style="clear: both;">[![](https://4.bp.blogspot.com/-4JaBjT2zteM/WHV3yookVUI/AAAAAAAAfiI/8d6p3dwyTqsnJwIHhbS1_VZw__k3z14dACEw/s320/step%2B5.png)](https://4.bp.blogspot.com/-4JaBjT2zteM/WHV3yookVUI/AAAAAAAAfiI/8d6p3dwyTqsnJwIHhbS1_VZw__k3z14dACEw/s1600/step%2B5.png)</div>

6.  Right click on the **Local Area Network** adapter and choose **Properties**.

    <div class="separator" style="clear: both;">[![](https://2.bp.blogspot.com/-2k5XAzhoAUs/WHV3zt6B6xI/AAAAAAAAfiI/WGtETSXWJUMpAoHFaptsdKLStqrcT0x-QCEw/s320/step%2B6.png)](https://2.bp.blogspot.com/-2k5XAzhoAUs/WHV3zt6B6xI/AAAAAAAAfiI/WGtETSXWJUMpAoHFaptsdKLStqrcT0x-QCEw/s1600/step%2B6.png)</div>

7.  Select the **Internet Protocol Version 4 (TCP/IPv4)** item and then click the **Properties** button.

    <div class="separator" style="clear: both;">[![](https://3.bp.blogspot.com/-wnRSgU54iuY/WHV3zqGoYuI/AAAAAAAAfiI/opub7QHkbZgd1uObQ2r5v5w2YLKw8yadgCEw/s320/step%2B7.png)](https://3.bp.blogspot.com/-wnRSgU54iuY/WHV3zqGoYuI/AAAAAAAAfiI/opub7QHkbZgd1uObQ2r5v5w2YLKw8yadgCEw/s1600/step%2B7.png)</div>

8.  Select **Use the following DNS server addresses** and enter the IP addresses of your desired DNS servers here.

    <div class="separator" style="clear: both;">[![](https://2.bp.blogspot.com/-Erx21vX0PCo/WHV3zzSx2II/AAAAAAAAfiI/TPddxVwjcSwRDmyovwpdmvpD7TPABzOKQCEw/s320/step%2B8.png)](https://2.bp.blogspot.com/-Erx21vX0PCo/WHV3zzSx2II/AAAAAAAAfiI/TPddxVwjcSwRDmyovwpdmvpD7TPABzOKQCEw/s1600/step%2B8.png)</div>

9.  You shouldn't need to, but you can restart the VM for safe measure.