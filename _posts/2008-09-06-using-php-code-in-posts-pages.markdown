---
layout: post
status: publish
published: true
title: Using PHP code in Posts & Pages
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 134
wordpress_url: http://brockangelo.com/?p=134
date: '2008-09-06 19:03:12 -0500'
date_gmt: '2008-09-07 00:03:12 -0500'
categories:
- WordPress
- PHP
tags:
- php
- WordPress
- html
- wp-syntax
- exec-php
comments: []
---
<p>There really is no other way around it: you need to be able to add php code to Posts & Pages if you are going to mod your WP install. I use so much PHP & custom SQL queries on the company intranet that WordPress is almost an aside to the main event.</p>
<p>But in order to use PHP code inside posts, pages &amp; widgets, you need to get the <a href="http://bluesome.net/post/2005/08/18/50/">Exec-PHP plugin</a>. It is truly amazing. Once it is installed, just turn off your Rich Text Editor and start coding away. But what do you do when you want to <em>display PHP code</em> inside of one of your posts? There are times that you'll want to show off your PHP code without executing it. That can be done too. Taken from the exec-php homepage:<br />
<em>If you just want to print out code and don’t want to execute it, e.g. like it is done here on this page, you have to make sure to convert your code to the correct XHTML representation.<br />
</em></p>
<blockquote><p><center></p>
<table>
<tr>
<td width="33%">
<h4>&lt;</h4>
</td>
<td width="33%">type</td>
<td width="33%">
<h4><code><</code></h4>
</td>
</tr>
<tr>
<td width="33%">
<h4>&gt;</h4>
</td>
<td width="33%">type</td>
<td width="33%">
<h4><code>></code></h4>
</td>
</tr>
<tr>
<td width="33%">
<h4>&amp;</h4>
</td>
<td width="33%">type</td>
<td width="33%">
<h4><code>&</code></h4>
</td>
</tr>
</table>
<p></center></p></blockquote>
<p>This is, however, very tedious if you think you'll put PHP in your code more than once. You can do this conversion much more intelligently by using the <a href="http://wordpress.org/extend/plugins/wp-syntax/">WP-Syntax</a> plugin. It creates nice colorful code boxes and formats them to any code format (PHP, Java, HTML, C+, Ruby, etc). It looks like this:</p>

```php
<div id="navbar">
    <ul>
    <table width="100%">
        <tr>
            <td width="80%">
                <li><a href="<?php echo get_settings('home'); ?>">Home</a></li>
                <?php wp_list_pages('title_li=&depth=1&include=38'); ?>
                <li><a href="http://brockangelo.com/category/ubuntu/">Ubuntu</a></li>
                <li><a href="http://brockangelo.com/category/wordpress/">WordPress</a></li>
                <li><a href="<?php bloginfo('rss2_url'); ?>">RSS</a></li>
            </td>
            <td width="20%" align="right">
                <li><a><?php echo (date("g:i a")); ?></a></li>
            </td>
        </tr>
    </table>
    </ul>
</div>
```