---
layout: post
status: publish
published: true
title: Allowing Uploads via the Media Uploader
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 147
wordpress_url: http://brockangelo.com/?p=147
date: '2008-09-05 16:14:33 -0500'
date_gmt: '2008-09-06 00:14:33 -0500'
categories:
- WordPress
tags:
- linux
- chmod
- permissions
- Ubuntu
comments: []
---
<p><strong>Allowing Users to Upload via the WordPress 2.6 Media Uploader</strong>:<br /> You have to <strong>chmod</strong> <code>wp-content/uploads/</code> to 777 in order for the Media Uploader to allow users to upload files. With the websites that I host, I prefer to not have anything chmod'ed to 777 unless it is extremely inconvenient, so I just create folders every few months and <code>chmod</code> them to 777. I go into <code>/wp-content/uploads/THE_YEAR/</code> and do a <code>mkdir 08</code> (or whatever the current month is) and then <code>chmod 777 08</code> for the month, and I chmod previous months back to 755. The alternative would be to chmod the entire uploads directory, but then all prior uploads would be at risk of tampering.</li>
