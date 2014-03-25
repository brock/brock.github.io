---
layout: post
status: publish
published: true
title: How to Change Attributes for all Files and Folders
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 671
wordpress_url: http://brockangelo.com/?p=671
date: '2008-11-02 11:56:44 -0600'
date_gmt: '2008-11-02 19:56:44 -0600'
categories:
- Ubuntu
- WordPress
tags: []
comments:
- id: 208
  author: QB
  author_email: qb605@yahoo.com
  author_url: http://www.opticalmailorder.co.uk
  date: '2009-03-09 17:34:53 -0500'
  date_gmt: '2009-03-10 01:34:53 -0500'
  content: That's fantastic - I have been struggling with a similar problem myself
    and I was really not sure as to how to protect my folders properly at the same
    time as allowing proper access to the content - thanks Ubuntu
---
<p><strong>How to Change Attributes for all Files and Folders in Linux</strong></p>
<p>I am regularly working with WordPress and need to change the attributes of my files and folders so that it is locked down and secure. This is a two step process. I first change the attributes of all files to 644. Then I change the attributes of all folders to 755. However, you should decide what is best for you by reading the article on the Codex called <a href="http://codex.wordpress.org/Changing_File_Permissions">Changing File Permissions</a> if you are new to this topic.</p>
<p>This can be done from anywhere, since I always type out the full path to the location so I know I'm not making any mistakes. I enter the following to change all files:</p>

`sudo find [enter path here. ex: /var/www/wordpress] -type f -exec chmod 644 {} \;`

<p>And I follow that up by entering the following for folders:</p>

`sudo find [enter path here. ex: /var/www/wordpress] -type d -exec chmod 755 {} \;`

<p>And you're done. </p>
