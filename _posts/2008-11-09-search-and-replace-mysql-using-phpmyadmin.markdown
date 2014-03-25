---
layout: post
status: publish
published: true
title: Search and Replace MySQL using PHPMyAdmin
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 689
wordpress_url: http://brockangelo.com/?p=689
date: '2008-11-09 14:51:17 -0600'
date_gmt: '2008-11-09 19:51:17 -0600'
categories:
- Ubuntu
- WordPress
- MySQL
tags:
- WordPress
- mysql
- phpmyadmin
- query
- search and replace
comments:
- id: 203
  author: Gosip Artis Terbaru
  author_email: cuprid@gmail.com
  author_url: http://oktavita.com
  date: '2008-12-05 18:21:12 -0600'
  date_gmt: '2008-12-06 02:21:12 -0600'
  content: great, this is what i'm looking for. thanks for sharing
- id: 443
  author: '[n3rve]'
  author_email: ralph@simplemachines.org
  author_url: ''
  date: '2009-07-11 06:10:59 -0500'
  date_gmt: '2009-07-11 11:10:59 -0500'
  content: Thanks for sharing, exactly what I needed :D
- id: 2803
  author: Aussie Punter
  author_email: webmaster@ozepunting.com
  author_url: http://www.ozepunting.com/
  date: '2011-08-16 03:05:06 -0500'
  date_gmt: '2011-08-16 08:05:06 -0500'
  content: "Thanks for this concise method for searching and replacing WordPress tables.
    After upgrading my WordPress structure from a subdirectory to the root domain,
    I had tons of 404's and was dreading updating them by hand. Your code literally
    saved me days of work.\r\n\r\nCheers mate."
- id: 3444
  author: fubourius
  author_email: fubourius@gmail.com
  author_url: ''
  date: '2011-09-21 04:58:27 -0500'
  date_gmt: '2011-09-21 09:58:27 -0500'
  content: Thanks very good explained!
- id: 3470
  author: Matt
  author_email: msmiles@shimadzu.com
  author_url: ''
  date: '2011-09-23 12:51:27 -0500'
  date_gmt: '2011-09-23 17:51:27 -0500'
  content: Thanks a lot for posting this! It saved me quite a bit of time--much appreciated!
- id: 6039
  author: june
  author_email: singaporebiznes@gmail.com
  author_url: http:/sgbizness.com
  date: '2012-03-10 22:00:18 -0600'
  date_gmt: '2012-03-11 03:00:18 -0500'
  content: is there any function or procedure to do this?  i dont know what are the
    affected tables and fields?  i know 1 script in sql server.
- id: 20711
  author: GILES
  author_email: GILES.COLE@YAHOO.CO.UK
  author_url: ''
  date: '2013-01-29 14:31:59 -0600'
  date_gmt: '2013-01-29 19:31:59 -0600'
  content: "Brilliant resource.  Thanks.\r\nWell explained, much clearer than other
    websites."
- id: 20879
  author: Marc
  author_email: marc@marcheatleydesign.com
  author_url: http://marcheatleydesign.com
  date: '2013-10-01 08:41:06 -0500'
  date_gmt: '2013-10-01 13:41:06 -0500'
  content: Thanks for this - this is the 3rd explanation of this I've read The syntax
    has been the same everywhere, but your explanation was definitely the clearest.
- id: 20886
  author: read homepage
  author_email: GenitoOnorati2866@gmail.com
  author_url: http://www.gaptekupdate.com/aroma-parfum-lebih-berbahaya-dibanding-asap-rokok-300/
  date: '2013-12-08 14:21:07 -0600'
  date_gmt: '2013-12-08 19:21:07 -0600'
  content: Usually I do not learn article on blogs, but I would like to say that this
    write-up very compelled me to take a look at and do it! Your writing taste has
    been surprised me. Thanks, quite great article.
---
<p><strong>Search and Replace MySQL using PHPMyAdmin</strong></p>
<p>This is a life-saver: an easy way to search any table inside your database and replace one string of text with another. It works like a charm. But be careful, search first to see the results of your query before you commit the changes, and always backup prior to any database work.</p>
<p>Here is how you test the waters safely:</p>
<blockquote><p><code>SELECT * FROM `wp_posts` WHERE `post_content` LIKE '%oops%'</code></p></blockquote>
<p>Translation:</p>
<blockquote><p><code>SELECT * FROM `table_name` WHERE `field_name` LIKE '%unwanted_text%'</code></p></blockquote>
<p>And here is how you do some damage:</p>
<blockquote><p><code>UPDATE `wp_posts` SET `post_content` = replace(post_content, 'oops', 'much better')</code></p></blockquote>
<p>And translated:</p>
<blockquote><p><code>UPDATE `table_name` SET `field_name` = replace(same_field_name, 'unwanted_text', 'wanted_text')</code></p></blockquote>
