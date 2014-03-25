---
layout: post
status: publish
published: true
title: Delete Comment Spam using a Cron Job
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: Delete all the comments marked as spam automatically using cron.
wordpress_id: 751
wordpress_url: http://brockangelo.com/?p=751
date: '2009-05-23 12:46:12 -0500'
date_gmt: '2009-05-23 17:46:12 -0500'
categories:
- Ubuntu
- WordPress
- Bash
- MySQL
tags:
- Ubuntu
- WordPress
- mysql
- spam
- akismet
- cron
- delete-spam-daily
comments: []
---
<p><strong>Delete Comment Spam using a Cron Job</strong></p>
<p>WordPress catches all of the comment spam, but it doesn't seem to delete it often enough. If you have a high traffic site, this can become megabytes in your database. Bleh. I don't have a high traffic site, but I sync my databases off-site everyday and spam wastes my bandwidth. So I delete all the comments marked as spam automatically each day using a scheduled cron job so that I never even have to see it. Could I possibly delete a real comment? Yes. Does the convenience of never even knowing about comment spam outweigh the risk? You bet.</p>
<p>Create a bash script in your scripts folder by typing this at the command prompt:</p>
<blockquote><p><code>sudo pico /home/brockangelo/scripts/del_spam.sh</code></p></blockquote>
<blockquote><p><strong>sudo:</strong>  elevate privileges<br />
<strong>pico:</strong>   use your editor of choice<br />
<strong>/home.../scripts/:</strong>   wherever you keep all your bash scripts<br />
<strong>del_spam.sh:  </strong>name it something obvious</p></blockquote>
<p>By the way, bash scripts are as easily made as windows batch files. You just put in the code and put a .sh at the end. Inside "del_spam.sh" add the following:</p>
<blockquote><p><code>mysql -u username -ppassword -e "delete from wp_comments where comment_approved='spam';" brockangelo</code></p></blockquote>
<p>Where "brockangelo" is the name of the database. Repeat this line for each WordPress site you host. Then you need to set this up as a cron job and schedule it for once a night. Or, you can download my plugin that deletes spam daily. <a href="http://brockangelo.com/wordpress/plugins/delete-spam-daily/">Delete Spam Daily</a> plugin.</p>
<p>By the way, the username and password format in that command you see above looks wrong, but it is typed correctly. You put "-u (space) username" then you squish the "-p" and "password" together like this "-u username -ppassword".</p>
