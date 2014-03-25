---
layout: post
status: publish
published: true
title: How to Install your Android APK with One Click
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: How to install Android APK files to your Android device in one click.
wordpress_id: 1405
wordpress_url: http://brockangelo.com/?p=1405
date: '2011-06-28 20:51:11 -0500'
date_gmt: '2011-06-29 01:51:11 -0500'
categories:
- Windows
- Android
tags: []
comments: []
---
<p>I've been learning <a href="http://www.anscamobile.com/">Corona</a> lately, a tool for building mobile apps. Overall there is a lot of good stuff, though rough around some of the edges especially if you are building "business apps" - you know, anything that isn't a game. :) But one thing that I really miss from building Android in Eclipse is the auto-install to my Android phone. Here is a way to get 1-click install to your Android device, in Windows.</p>
<ol>
<li>You'll need to have the Android SDK installed on your PC. More about that <a href="http://developer.android.com/sdk/installing.html">here</a>.</li>
<li>You'll need to have your Android device plugged in.</li>
<li>You'll also need to install a freeware app called <a href="http://www.lopesoft.com/en/fmtools/info.html">FileMenuTools</a> - a fabulous tool that I've used for years.</li>
<li>Open FileMenuTools and in the top left, click "Add Command".</li>
<li>In the Properties pane on the lower left, select "<strong>Run Program</strong>" for your action, for Menu Text I chose "<strong>Install on Android</strong>", for icon browse to the <strong>SDK Manager.exe</strong> because it is an easy Android icon, for Element Types I chose "<strong>Only Files</strong>", for Folders I chose "<strong>No</strong>", for Files I chose <strong>Yes</strong>, and for Extensions I typed <strong>apk</strong>, then for Program you need to browse and find <strong>adb.exe</strong> in your SDK\program-tools\ directory, and for arguments enter <strong>install %FILENAMES%</strong>.</li>
</ol>
<p>Now, if you right click on an APK file that the Corona SDK provides after a build, this should briefly pop up a command window while it copies and installs it to your device.</p>
<p>It will bypass the Install prompts and should show up directly in your Applications folder.</p>
