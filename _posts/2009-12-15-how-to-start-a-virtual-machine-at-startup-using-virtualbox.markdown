---
layout: post
status: publish
published: true
title: How to Start a Virtual Machine at Startup Using VirtualBox
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: 'How to start a Virtual Machine at startup, (aka: start at VM at boot) if
  you are using VirtualBox.'
wordpress_id: 1309
wordpress_url: http://brockangelo.com/?p=1309
date: '2009-12-15 17:25:22 -0600'
date_gmt: '2009-12-15 22:25:22 -0600'
categories:
- Batch
tags:
- virtualbox
- vm
- startup
- boot
- tweakui
comments:
- id: 5754
  author: root
  author_email: techsupport@shgov.tk
  author_url: ''
  date: '2012-02-14 12:54:07 -0600'
  date_gmt: '2012-02-14 17:54:07 -0600'
  content: Thanks, helped alot
- id: 10482
  author: user
  author_email: user@mailinator.com
  author_url: ''
  date: '2012-07-21 12:30:21 -0500'
  date_gmt: '2012-07-21 17:30:21 -0500'
  content: "The path name for VBoxManage.exe is now:\r\n\r\n C:\\Program Files\\Oracle\\VirtualBox\\VBoxManage.exe"
- id: 11851
  author: Patrick Lupien
  author_email: junk@lupiens.com
  author_url: http://www.lupiens.com
  date: '2012-09-06 09:41:17 -0500'
  date_gmt: '2012-09-06 14:41:17 -0500'
  content: Thank you. That just made my home proxy a lot more seamless.
- id: 13852
  author: Como iniciar una maquina de VirtualBox al arrancar Windows | El Blog de
    Malagana
  author_email: ''
  author_url: http://www.malagana.net/como-iniciar-una-maquina-de-virtualbox-al-arrancar-windows/
  date: '2012-10-19 18:51:12 -0500'
  date_gmt: '2012-10-19 23:51:12 -0500'
  content: '[...] blockangelo.com y VirtualBox Comparte en tus redes sociales.           Tweet   Esta
    entrada fu&eacute; escrita por [...]'
- id: 18705
  author: Jura
  author_email: jurasono@gmail.com
  author_url: ''
  date: '2013-01-04 21:13:31 -0600'
  date_gmt: '2013-01-05 02:13:31 -0600'
  content: "Here's my code:\r\n@echo off\r\ncls\r\n\"C:\\Program Files\\Oracle\\VirtualBox\\VirtualBox.exe\"
    startvm  ClearOSfinal.vbox\r\n@exit\r\n\r\nits only running Virtual Box, not the
    vm"
- id: 20882
  author: L.A.
  author_email: laa@jimac-inc.com
  author_url: ''
  date: '2013-11-12 20:44:55 -0600'
  date_gmt: '2013-11-13 01:44:55 -0600'
  content: "Here’s mine and it woked:\r\n@echo off\r\ncls\r\n“C:\\Program Files\\Oracle\\VirtualBox\\VirtualBox.exe”
    startvm \"Full path where the .vbox file extension is located\"\r\n@exit"
- id: 20885
  author: Lin Rongxiang
  author_email: linrx@outlook.sg
  author_url: http://l-rex.tk
  date: '2013-12-04 12:56:39 -0600'
  date_gmt: '2013-12-04 17:56:39 -0600'
  content: "Have a user who has been rather kind and patient thus far so to speak,
    therefore working a little more on how her experience with migrating from Windows
    7 onto Windows 8 can be streamlined -- Windows 8 is fine thus far as far as I
    am concerned, there is a slight learning curve, and when I am at a juncture when
    I can recommend it to others I am alright in assisting a user embrace the newer
    OS edition as well -- she has got a variety of applications that has been running
    on Windows 7 and its prior versions, and these applications seem out of place
    when I introduce them onto Windows 8, thought VirtualBox may be a worst solution
    yet how else am I going to have a user using Windows 8 and 7 concurrently?\r\n\r\nThis
    link was useful <code>https://forums.virtualbox.org/viewtopic.php?f=1&amp;t=24907</code>.."
---
<p>This did not seem obvious to me, so I hope it is valuable to someone else. If you are using VirtualBox to host your newly created Virtual Servers, one of the questions you will find yourself asking is: "What if my machine reboots?" VirtualBox does not (yet) have a built in way to indicate that you want to start a VM when your Host machine boots, so you need to add this to your startup.</p>
<p>If you are on Windows, create a batch file with the following content:</p>
<p><code lang="batch"><br />
@echo off<br />
cls<br />
"C:\Program Files\Sun\VirtualBox\VBoxManage.exe" startvm vm-name<br />
@exit<br />
</code></p>
<p>You should replace "vm-name" with the name of the Virtual Machine you want to start. If you are on XP, make sure you are using TweakUI to auto-login to XP.</p>
<p>Enjoy!</p>
