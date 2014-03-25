---
layout: post
status: publish
published: true
title: Display the Contents of a File Using PHP
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 873
wordpress_url: http://brockangelo.com/?p=873
date: '2009-06-07 04:00:00 -0500'
date_gmt: '2009-06-07 12:00:00 -0500'
categories:
- PHP
tags:
- php
- server
- file contents
- file_get_contents
- text file
- echo
comments:
- id: 2243
  author: rubul
  author_email: rubulhaloi20@gmail.com
  author_url: http://--
  date: '2011-05-18 05:19:57 -0500'
  date_gmt: '2011-05-18 10:19:57 -0500'
  content: "i guess either of the functions  fread; file_get_contents has limit on
    the number of bytes on the file;;;that it works well for small files but fails
    for large files--(executes the die statement(if it is added));;;;\r\n\r\n\r\nso
    what i wanted to know is that if there is a way to copy large file contents into
    a string????\r\nas fread fgets or get_file_contents fails what is the alternative???????"
- id: 2619
  author: Chad Buie
  author_email: chadbuie@gmail.com
  author_url: http://www.discount-cctv-equipment.com
  date: '2011-07-30 07:27:38 -0500'
  date_gmt: '2011-07-30 12:27:38 -0500'
  content: "That is a good question. I know Wordpress had a loop function like that.
    I am trying to create and emulate the same technology with a built-in function.
    I read some on fgets here ::\r\n\r\nhttp://www.php.net/manual/en/function.fgets.php"
- id: 2620
  author: Chad Buie
  author_email: chadbuie@gmail.com
  author_url: http://www.discount-cctv-equipment.com
  date: '2011-07-30 07:29:59 -0500'
  date_gmt: '2011-07-30 12:29:59 -0500'
  content: Actually you could probably hold more data in an array....then just write
    a command to pull a limited amount of data and then a link to the rest of the
    article. That could work. It is what I am doing for my website.
---
<p><strong>How to Display the Contents of a File Using PHP</strong></p>
<p>PHP has a built in function to display the <em>contents</em> of a file. This is helpful if you want to update a webpage to reflect some data that is regularly updated or output to a file. It is also helpful if you have access to the web server and it is easier for you to update a text file than it is to edit html. Simply point your webpage to the text file and the contents of the webpage get updated automatically.</p>
<p>Here's how it works:</p>
<p>[php]&lt;?php<br />
echo file_get_contents('http://brockangelo.com/uptime.txt');<br />
?&gt;[/php]</p>
<p>Easy enough. I used to have a message in the footer of this webpage that said "This server has been up for 14 days, 7 hours, 22 minutes." All that was doing was reading the contents of the text file that got updated every hour.</p>
