---
layout: post
status: publish
published: true
title: Displaying JPG files over a Mapped Drive
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 163
wordpress_url: http://brockangelo.com/?p=163
date: '2008-09-09 17:27:36 -0500'
date_gmt: '2008-09-10 01:27:36 -0500'
categories:
- Ubuntu
tags:
- novell
- networking
- mapped drive
- linux
- Ubuntu
- apache
comments: []
---

I don't think that most people would have guessed this, but if the images you are going to display on your website are located on a mapped network drive, Apache needs to be modified in order for the image to display. If you mapped a network drive but it only displays the text of the image in the browser, you need to change the following inside of your Apache Directives:

<blockquote><p><code>&lt;Directory "/path-to-mapped-drive"&gt;<br />
EnableSendfile Off<br />
&lt;/Directory&gt;<br />
</code></p></blockquote>
<p>So, this may not make a lot of sense unless you have experienced the problem firsthand; but if you open the browser window, expecting to see a jpg, and instead you see something like this:</p>
<blockquote><p>http://media.brockangelo.com/wp-content/uploads/mnt/2008/08/sample.jpg</p></blockquote>
<p>Then you need to set <code>EnableSendfile</code> to "Off" inside your Apache Directives.</p>
