---
layout: post
status: publish
published: true
title: Search and Replace a Custom Field in WordPress using PHPMyAdmin
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: Here is how to do a search and replace for a specific Custom Field value
  in WordPress. Works for all posts that have that value in a specific Custom Field.
wordpress_id: 706
wordpress_url: http://brockangelo.com/?p=706
date: '2009-03-18 06:32:07 -0500'
date_gmt: '2009-03-18 11:32:07 -0500'
categories:
- Ubuntu
- WordPress
- MySQL
tags:
- WordPress
- mysql
- phpmyadmin
- sql
- custom fields
---

If you've ever used Microsoft Excel, you probably have an idea of just how easy changing hundreds of cells can be. Gone are the days of manually typing line by line any corrections that you need to make. The same is true when you are working with a database like we are in WordPress.

This example performs a search and replace of all custom fields that meet a specified criteria. In this case, I'm looking for all staff member pages that have a custom field for a department phone number that was incorrect. We want to replace that with a new number. Using PHPMyAdmin and running a SQL query, I can select all of them to see the results before I do anything to my databse:

```SELECT * FROM `wp_postmeta` WHERE `meta_key` LIKE 'DeptPhone' AND `meta_value` LIKE '212-555-1212'```

It is worth mentioning, that you can also use wildcards if you want to include more results. The '%' is your wildcard:

```SELECT * FROM `wp_postmeta` WHERE `meta_key` LIKE '%eptPhone' AND `meta_value` LIKE '212-555-%'```

This yields the same results. It is also worth pointing out that the quotation mark around our text values and the tick mark around our table column names are different.

* ``` `meta_key` ``` uses tick marks	(this is usally the top left key on your keyboard, next to the 1)
* `'%DeptPhone'` uses a single quotation mark (this is next to the enter key)

So, to perform the changes, we need to use the UPDATE command instead of select, and actually replace text. Here goes:

```UPDATE `wp_postmeta` SET `meta_value` = replace(meta_value, '212-555-1212', '212-444-1212') WHERE `meta_key` LIKE 'DeptPhone'```
