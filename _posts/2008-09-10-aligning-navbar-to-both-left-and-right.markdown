---
layout: post
status: publish
published: true
title: Aligning Navbar to both Left and Right
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 239
wordpress_url: http://brockangelo.com/?p=239
date: '2008-09-10 16:07:08 -0500'
date_gmt: '2008-09-10 21:07:08 -0500'
categories:
- WordPress
- PHP
- HTML
tags:
- php
- html
- tables
- css
- navbar
comments: []
---
<p><strong>Aligning a Navigation Bar to both the Left side and the Right sides</strong>:</p>
<p>I have always thought it would be nice to have a navigation bar that aligns text to both the left and the right, so I finally took the time to get this working. Once I figured it out, it was very simple to setup. </p>
<p>So on the left you'll have this:<br />
<center><br />
<blockquote><img src="http://brockangelo.com/wp-content/uploads/2008/09/left.jpg" alt="" title="left" width="366" height="54" class="aligncenter size-full wp-image-242" /></p></blockquote>
<p></center></p>
<p>And on the right you'll have this:<br />
<center><br />
<blockquote><img src="http://brockangelo.com/wp-content/uploads/2008/09/right.jpg" alt="" title="right" width="281" height="66" class="aligncenter size-full wp-image-241" /></p></blockquote>
<p></center></p>
<p>It is as simple as an html table. Yep. Just think about it. Your navigation bar is a single row, with two columns. I set my left column to 70% and my right column to 30%. Then I can align each table to the left or right. </p>
<p>I set the entire table inside an unordered list, then each page link is just an <code>li</code> or a <em>list item</em>. Your header.php file will probably look similar to mine, but without the table. What you choose to do with your newly-balanced right side is up to you. I am displaying the current time with a greeting depending on the time of day. At my office we are displaying the visitors IP address (very handy on a LAN).</p>
<p>[php]<br />
&lt;div id=&quot;navbar&quot;&gt;<br />
	&lt;ul&gt;<br />
		&lt;table width=&quot;100%&quot;&gt;<br />
			&lt;tr&gt;<br />
		&lt;td width=&quot;80%&quot;&gt;&lt;li&gt;&lt;a href=&quot;&lt;?php echo get_settings('home'); ?&gt;&quot;&gt;Home&lt;/a&gt;&lt;/li&gt;<br />
		&lt;?php wp_list_pages(); ?&gt;<br />
		&lt;?php wp_list_categories(); ?&gt;<br />
		&lt;/td&gt;<br />
		&lt;td width=&quot;20%&quot; align=&quot;right&quot;&gt;&lt;div id=&quot;txt&quot;&gt;&lt;/div&gt;&lt;/td&gt;<br />
			&lt;/tr&gt;<br />
		&lt;/table&gt;<br />
	&lt;/ul&gt;<br />
&lt;/div&gt;<br />
[/php]</p>
