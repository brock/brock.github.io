---
layout: page
status: publish
published: true
title: Google Chart Generator
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 818
wordpress_url: http://brockangelo.com/?page_id=818
date: '2009-05-30 20:17:56 -0500'
date_gmt: '2009-05-31 04:17:56 -0500'
categories:
- Blog
tags: []
comments:
- id: 242
  author: baron
  author_email: turkbaron@ymail.com
  author_url: http://www.turkbaron.net
  date: '2009-06-02 06:33:15 -0500'
  date_gmt: '2009-06-02 14:33:15 -0500'
  content: Works great, thank you
- id: 250
  author: Ella
  author_email: ella.afitzgerald@gmail.com
  author_url: http://www.ohhdear.org
  date: '2009-06-03 21:13:14 -0500'
  date_gmt: '2009-06-04 05:13:14 -0500'
  content: This rocks. You rock. Thank you for sharing and helping people out. I send
    you a virtual beer :)
- id: 293
  author: Malcolm
  author_email: malcolm@malcolmgibb.com
  author_url: ''
  date: '2009-06-14 08:20:00 -0500'
  date_gmt: '2009-06-14 16:20:00 -0500'
  content: Great chart generator. It is easy to enter data and see a preview.  However,
    after selecting and copying the code provided, I can't seem to get it to show
    up on a page or a post.  Any ideas what I might be doing wrong?
- id: 294
  author: brockangelo
  author_email: email@brockangelo.com
  author_url: http://brockangelo.com
  date: '2009-06-14 09:58:41 -0500'
  date_gmt: '2009-06-14 17:58:41 -0500'
  content: If you copy and paste the link in a browser, you should see a chart. If
    it isn't showing up in your post or page, you probably haven't inserted the proper
    html tags. Try inserting the chart using the "img src=" tags and see if that works.
- id: 407
  author: Tracy
  author_email: tracy@tracyandcarol.com
  author_url: http://www.tracyandcarol.com
  date: '2009-07-07 15:01:43 -0500'
  date_gmt: '2009-07-07 20:01:43 -0500'
  content: I just downloaded this plugin.  It seems to be just what I was looking
    for.  My initial chart had data values of 244 and 229.  The line chart I created
    had a straight line connecting the 2 values at 100.  Can I use values that are
    greater than 100?
- id: 408
  author: brockangelo
  author_email: email@brockangelo.com
  author_url: http://brockangelo.com
  date: '2009-07-07 15:48:39 -0500'
  date_gmt: '2009-07-07 20:48:39 -0500'
  content: The current version does not support data above 100, because the Google
    Charts API doesn't support it using the default method of constructing URLs. There
    is another method that I'm working on that will allow values greater than 100,
    and will provide cleaner, shorter URL's for the charts. Keep watching for future
    releases.
- id: 595
  author: ovidiu
  author_email: ovidiu@pacura.ru
  author_url: http://pacura.ru/
  date: '2009-08-13 06:02:14 -0500'
  date_gmt: '2009-08-13 11:02:14 -0500'
  content: any news on the version taht will be able to get data from teh DB for the
    graphs?
- id: 607
  author: brockangelo
  author_email: email@brockangelo.com
  author_url: http://brockangelo.com
  date: '2009-08-19 19:34:57 -0500'
  date_gmt: '2009-08-20 00:34:57 -0500'
  content: Unfortunately not at present. I am starting grad school and am pretty swamped.
    Sorry for the let-down. Though others are welcome to step in. :D
- id: 612
  author: Seth Long
  author_email: slong@soundpublishing.com
  author_url: http://bbjtoday.com
  date: '2009-08-25 11:25:34 -0500'
  date_gmt: '2009-08-25 16:25:34 -0500'
  content: Brock - The plugin currently shows up on the Settings menu, which is only
    available to admin-level users. Is there any way to make it available to editors,
    authors, and contributors?
- id: 669
  author: Google Chart Generator | Blue Orbs
  author_email: ''
  author_url: http://blueorbs.com/2009/blog-add-ons/google-chart-generator/
  date: '2009-10-29 23:54:43 -0500'
  date_gmt: '2009-10-30 04:54:43 -0500'
  content: '[...] the user to create and insert a Google Chart in just a few short
    clicks. Check out the working online demo to see for [...]'
- id: 853
  author: arctosfx
  author_email: arctosfx@gmail.com
  author_url: ''
  date: '2010-10-09 17:20:56 -0500'
  date_gmt: '2010-10-09 22:20:56 -0500'
  content: "hi:\r\n\r\nnice WP plugin, but it doesnt seem to chart negative values.
    Am i not doing something right or it just doesnt recognize negative numbers?\r\n\r\nthanks,"
- id: 2372
  author: void*
  author_email: stoneddea7h@gmail.com
  author_url: ''
  date: '2011-06-14 08:27:25 -0500'
  date_gmt: '2011-06-14 13:27:25 -0500'
  content: "Hi, thanks for writing this tool Brock.\r\nI write here because it raise
    a javascript error: in my case \"Quick-Cache\" plugin create a hidden form, so
    you don't should use document.forms[0] .\r\nI suggest you give an id to the form,
    and use document.forms['form-id'], in this mode: http://dpaste.com/hold/554086/"
---
<p>Version 1.0.4</p>
<hr />
<center><img src="http://chart.apis.google.com/chart?cht=bvs&chd=s:YUVmw1&chco=FF0000&chs=180x150&chtt=Site+visitors+by+month|January+to+July&chbh=22,4" style="border: 4px #000 solid" /></center></p>
<hr />
<p>The GCG Plugin will insert a page called "Google Chart Generator" under your Settings in WordPress 2.7+ that allows you to select from the available charts in the Google Chart API. Knowledge of the API *is not required*. The options page allows you to select from the available charts in the API, add labels, select the size, colors, etc. Once you have designed a chart to your liking, you may either copy & paste the <code><img src></code> tag directly into your post, or you can save your chart for use in the provided widget. You will also have an insert button in the write post box that allows you to insert a saved chart into a post or page.</p>
<p>It will soon be able to do more than static charts: you'll be able to link it to your WordPress database so that your charts update automatically. Some example charts might be: number of comments per month represented as a line chart, average number of days between posts, and a few others.</p>
<p>It was accidentally release to the plugin repository (oops) on 6.1.2009 before development was complete. It got a ton of downloads in one day, so I went ahead and released version 1.0.1 that cleans thinks up a bit and actually links here. I'll be adding more features this week. 1.0.3 is out with things like labels, titles and colors. Download it today!</p>
<p>Download <a href="http://downloads.wordpress.org/plugin/google-chart-generator.zip">google-chart-generator.zip</a></p>
