---
layout: post
status: publish
published: true
title: Display Novell Servers Connected to Your Server
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 132
wordpress_url: http://brockangelo.com/?p=132
date: '2008-09-13 05:38:56 -0500'
date_gmt: '2008-09-13 13:38:56 -0500'
categories:
- Ubuntu
tags:
- novell
- networking
- linux
- Windows
- ncpfs
comments: []
---
<p>I found an easy way to find out what Novell Netware servers you are connected to and can access. This requires that you have <strong>ncpfs</strong> installed in Linux and <em>I'm guessing</em> Novell's Netware client for IPX in Windows. If you do, just type:</p>
<blockquote><p><code>slist</code></p></blockquote>
<p>And you'll see a quick list of all the Novell machines on your network. If you don't have <strong>ncpfs</strong>, Ubuntu will prompt you to install ncpfs by running:</p>
<blockquote><p><code>sudo apt-get install ncpfs</code></p></blockquote>
<p>If you do have it, you'll see a similar list in Windows and Linux:</p>
<p><img src="http://brockangelo.com/wp-content/uploads/2008/09/slist.png" alt="" title="slist" width="500" height="183" class="aligncenter size-full wp-image-274" /></p>
<p>If you have <strong>ncpfs</strong> installed, but are not attached to any Novell servers, you'll see the following:</p>
<p><img src="http://brockangelo.com/wp-content/uploads/2008/09/slist_linux.png" alt="" title="slist_linux" width="500" height="115" class="aligncenter size-full wp-image-273" /></p>
