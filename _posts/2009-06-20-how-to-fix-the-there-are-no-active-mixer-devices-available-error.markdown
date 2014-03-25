---
layout: post
status: publish
published: true
title: How to Fix the "There are no active mixer devices available" Error
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 963
wordpress_url: http://brockangelo.com/?p=963
date: '2009-06-20 08:36:03 -0500'
date_gmt: '2009-06-20 13:36:03 -0500'
categories:
- Windows
tags:
- Windows
- audio
- hardware
- troubleshooting
- sound
comments:
- id: 8204
  author: Smitha
  author_email: smitha.narendar@wipro.com
  author_url: ''
  date: '2012-05-16 07:50:38 -0500'
  date_gmt: '2012-05-16 12:50:38 -0500'
  content: This was really helpful tip. Thanks
- id: 10375
  author: Hina
  author_email: info@khush-ent.com
  author_url: http://www.khush-ent.com
  date: '2012-07-18 00:34:40 -0500'
  date_gmt: '2012-07-18 05:34:40 -0500'
  content: what should i do coz m still having the same problem...
- id: 10552
  author: Felipe
  author_email: manoblack9@hotmail.com
  author_url: ''
  date: '2012-07-24 08:30:50 -0500'
  date_gmt: '2012-07-24 13:30:50 -0500'
  content: Very helpful. Thx
- id: 14508
  author: A
  author_email: A@a.com
  author_url: ''
  date: '2012-10-28 11:05:54 -0500'
  date_gmt: '2012-10-28 16:05:54 -0500'
  content: Thanks much BrockAngelo :)
- id: 15804
  author: Makeiz
  author_email: murkus@cooltoad.com
  author_url: http://www.murkus@cooltoad.com
  date: '2012-11-15 23:40:53 -0600'
  date_gmt: '2012-11-16 04:40:53 -0600'
  content: It worked thax hey
- id: 17604
  author: Anithu
  author_email: anithasri.mari@talentproindia.com
  author_url: ''
  date: '2012-12-17 05:11:17 -0600'
  date_gmt: '2012-12-17 10:11:17 -0600'
  content: "Hi,\r\n\r\nI tried all these, but still i am having the same problem.
    please help me"
- id: 19652
  author: Venkat Pavan
  author_email: savipavan@gmail.com
  author_url: ''
  date: '2013-01-18 05:33:13 -0600'
  date_gmt: '2013-01-18 10:33:13 -0600'
  content: "Solution is not working for me. I have tested the above options. Still
    it is showing same error messages.\r\n\r\nPlease help me on this......"
- id: 20849
  author: Shan
  author_email: balamurugan.s@shloklabs.com
  author_url: ''
  date: '2013-02-07 00:55:01 -0600'
  date_gmt: '2013-02-07 05:55:01 -0600'
  content: thank you.very helpfull
- id: 20857
  author: venu
  author_email: venu.panta@gmail.com
  author_url: ''
  date: '2013-03-08 20:07:10 -0600'
  date_gmt: '2013-03-09 01:07:10 -0600'
  content: Imy laptop had same issue.After I did the same steps which were mentioned
    in this site ,Its working.Thanks a lot for posting useful stuff.
---
<p>My Windows XP computer stopped playing audio when I was watching YouTube videos this week. When I tried to adjust the audio, it gave me the following error:</p>
<p><center><br />
<a href="http://media.brockangelo.com/wp-content/uploads/2009/06/no_active_mixer_devices.png"><img src="http://media.brockangelo.com/wp-content/uploads/2009/06/no_active_mixer_devices-300x52.png" alt="There are no active mixer devices available." title="There are no active mixer devices available." width="300" height="52" class="aligncenter size-medium wp-image-964" /></a><br />
</center><br /></p>
<blockquote><p>
There are no active mixer devices available. To install mixer devices, go to Control Panel, click Printers and Other Hardware, and then click Add Hardware.<br />
<br />
This program will now close.</p></blockquote>
<p>This happens because the Windows Audio service has stopped. To fix the issue, simply do the following:</p>
<blockquote><ul>
<li>Click the <strong>Start</strong> button, then click <strong>Run</strong></li>
<li>enter <strong>services.msc</strong> and press enter</li>
<li>Scroll down and <strong>right click</strong> on <strong>Windows Audio</strong> and select <strong>Start</strong></li>
<li>You should also go into <strong>Properties</strong> and make sure that the <strong>Startup Type</strong> is set to <strong>Automatic</strong></blockquote>
