---
layout: post
status: publish
published: true
title: How to Remove Non-Empty Directories in Linux
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 669
wordpress_url: http://brockangelo.com/?p=669
date: '2008-11-02 11:46:10 -0600'
date_gmt: '2008-11-02 19:46:10 -0600'
categories:
- Ubuntu
tags:
- Ubuntu
- command shell
- bash
- command line
comments:
- id: 5857
  author: vaishnavi
  author_email: vaishu.dhamnikar@gmail.com
  author_url: ''
  date: '2012-02-22 23:57:07 -0600'
  date_gmt: '2012-02-23 04:57:07 -0600'
  content: hey thanks  it worked!
- id: 10422
  author: Move, Rename, Copy, Create, Delete &amp; Manage Files/Directories in Linux
  author_email: ''
  author_url: http://www.intechgrity.com/common-directory-and-file-management-commands-in-linux/
  date: '2012-07-19 12:54:55 -0500'
  date_gmt: '2012-07-19 17:54:55 -0500'
  content: '[...] to copy entire directory in Linux5 Practical Examples To Delete
    / Remove Directory in LinuxHow to remove non-empty directories in LinuxSeries
    Navigation« System, Network &amp; Disk management Linux commands you should know
    to manage [...]'
- id: 21187
  author: us?ugi seo
  author_email: uta.parkman@hotmail.de
  author_url: http://www.good.is/members/mahit
  date: '2014-02-26 14:51:47 -0600'
  date_gmt: '2014-02-26 19:51:47 -0600'
  content: "?owiu. Wagner u?miechn?? si? Agencja Interaktywna oraz drgn??, jak \r\nus?ysza?
    <a href=\"http://www.good.is/members/mahit\" rel=\"nofollow\">us?ugi seo</a>\r\r\ncichy
    g?osowanie;\r\r\n- Owe o jak na przyk?ad nie znaczy.\r\r\nNie ca?kiem upu?ci?
    bro?, widz?c kpi?ce rzut oka nizio?ka.\r\n\r\n- W rzeczy samej porz?dnie - doda?\r\r\nFrodo,
    przedtem serio, - Skrupulatnie dysponujesz porcj?, \r\nowe oni ??dali zorganizowa?
    K?dziora,\r\r\nPrecyzuje na owo bro?, w tej okolicy o hecklera \r\ntrudno, prawdopodobnie
    na terytorium polski.\r\r\nUrwa?, przygryz? wargi.\r\r\n- Do?wiadczaj - przemówi?,
    - Pojmuj, jako ?."
---
<p><strong>How to Remove Non-Empty Directories in Linux</strong></p>
<p>Here is one that I am using all the time: deleting directories or an entire directory in Ubuntu (linux). It's very easy (and dangerous) as it will delete everything without asking for confirmation. But very handy when you know you just want to delete it all quickly.</p>
<blockquote><h2>This is dangerous! Use with caution!</h2>
<p><code>sudo rm -r *</code></p></blockquote>
<p>That deletes everything inside the current directory. But if you want to delete an entire directory that is inside your current directory, you do this:</p>
<blockquote><p><code>rm -r directoryname</code></p></blockquote>
<p>Be careful, and good luck! :)</p>
