---
layout: post
status: publish
published: true
title: How to Display Your "Uptime" using Bash
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: 'Bash is a powerful scripting tool and comes in handy on more than one occasion.
  Here is a fun one: Write your server uptime to a text file so that you can display
  it on a webpage.'
wordpress_id: 879
wordpress_url: http://brockangelo.com/?p=879
date: '2009-06-05 03:30:39 -0500'
date_gmt: '2009-06-05 11:30:39 -0500'
categories:
- Ubuntu
- Bash
tags:
- bash
- uptime
- scripts
comments:
- id: 2519
  author: Zev Eisenberg
  author_email: igeek1@gmail.com
  author_url: http://www.ZevEisenberg.com
  date: '2011-07-15 10:54:09 -0500'
  date_gmt: '2011-07-15 15:54:09 -0500'
  content: Finally! I've been looking for a way to do this for months! I modified
    this a bit and put it in a GeekTool geeklet. It's perfect!
- id: 21048
  author: google.com
  author_email: aliza_baylis@gmail.com
  author_url: http://www.google.com
  date: '2014-01-17 17:57:35 -0600'
  date_gmt: '2014-01-17 22:57:35 -0600'
  content: "This type of coat tends to thicken withh temprature changes, \r\nor regular
    clipping, and itt will also shed out minimally, but regularly, as well.\r\nIn
    olderr dogs it is probably one of the leading causes of death.\r\nWell, everyone
    with dogs wants to be like Amtrak."
---
<p>Bash is a powerful scripting tool and comes in handy on more than one occasion. Here is a fun one: Write your server uptime to a text file so that you can display it on a webpage.</p>
<p>[bash]<br />
#!/bin/sh</p>
<p># get the uptime data<br />
days=$(uptime | awk '{print $3}' | sed 's/,//g')<br />
hours=$(uptime | awk '{print $5}' | sed 's/,//g')<br />
label=$(uptime | awk '{print $4}')</p>
<p>if [ &quot;$days&quot; = 1 ]; then<br />
day_label='day'<br />
else<br />
day_label='days'<br />
fi</p>
<p>#format labels<br />
if [ $hours = 1 ]; then<br />
hour_label='hour'<br />
else<br />
hour_label='hours'<br />
fi</p>
<p>#format output<br />
if [ &quot;$label&quot; = 'mins,' ]; then<br />
echo 'This server has been on for '$days minutes'' &gt; /var/www/uptime.txt<br />
elif [[ &quot;$label&quot; = 'day,' || &quot;$label&quot; = 'days,' ]]; then<br />
echo 'This server has been on for '$days $day_label, $hours $hour_label'' &gt; /var/www/uptime.txt<br />
elif [ &quot;$label&quot; = '2' ]; then<br />
echo 'This server has been on for '$days hours'' &gt; /var/www/uptime.txt<br />
fi<br />
[/bash]</p>
