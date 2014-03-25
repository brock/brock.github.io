---
layout: post
status: publish
published: true
title: Mounting Ubuntu Server to a Novell Server
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 129
wordpress_url: http://brockangelo.com/?p=129
date: '2008-09-05 15:20:25 -0500'
date_gmt: '2008-09-05 23:20:25 -0500'
categories:
- Ubuntu
tags:
- novell
- networking
- mapped drive
comments: []
---
<p>This is very similar to mapping a network drive in Windows. But I like to point out that this is not the same as accessing a share over Samba or Windows File Sharing. You do not have to <em>share</em> a file or directory in Novell to use this tool. It lets you map any Novell directory to your Linux box. I also like to point out that this tool needs to know your Novell username & your Linux username, and these two should both have sufficient permissions to be doing this. Here's how you do it:</p>
<ol>
<li>Make sure you have <strong>ncpmount</strong> installed by typing:<br />
<blockquote><p><code>sudo apt-get install ncpmount</code></p></blockquote>
</li>
<li>Map & Mount the Novell Drive by typing:<br />
<blockquote><p><code>ncpmount<br />-S servername<br />-A fully.qualified.domain.name<br />-U Novell_Username.Context<br />-v Novell/path/to/source/of/mapping<br />-u Linux_username<br />-g Linux_group<br /> /path/to/mount/location</code></p></blockquote>
</li>
<p>I broke that all onto their own lines just so that it would be easier to read, but you should enter it all on one line. I found a really great ncpmount resource <a href="http://tldp.org/LDP/nag2/x-087-2-ipx.ncpfs.client.html">here</a>.
</ol>
