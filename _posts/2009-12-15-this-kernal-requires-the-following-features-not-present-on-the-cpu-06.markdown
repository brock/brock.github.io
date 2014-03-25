---
layout: post
status: publish
published: true
title: 'This Kernal Requires the Following Features Not Present on the CPU: 0:6'
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: 'Solution to Virtualbox error: "This kernel requires the following features
  not present on the CPU: 0:6"'
wordpress_id: 1304
wordpress_url: http://brockangelo.com/?p=1304
date: '2009-12-15 11:33:15 -0600'
date_gmt: '2009-12-15 16:33:15 -0600'
categories:
- Ubuntu
tags:
- Ubuntu
- virtualbox
- pae/nx
- processor
- error
comments:
- id: 4290
  author: noa
  author_email: nooneanother@yandex.ru
  author_url: ''
  date: '2011-11-23 02:14:48 -0600'
  date_gmt: '2011-11-23 07:14:48 -0600'
  content: thanks a lot, it helps
---
<p>If you get the following error when installing Ubuntu on VirtualBox:</p>
<blockquote><p>This kernel requires the following features not present on the CPU: 0:6</p></blockquote>
<p>...don't fret. You simply need to check the "Enable PAE/NX" found under Settings --> System --> Processor.</p>
