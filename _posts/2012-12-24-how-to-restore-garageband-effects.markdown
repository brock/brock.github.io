---
layout: post
status: publish
published: true
title: How to Restore Garageband Effects
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: I was missing the default Garageband effects in Garageband 11, and since
  I downloaded this from the App Store, I didn't have a restore disc to use. This
  tip restored the default effects.
wordpress_id: 1524
wordpress_url: http://brockangelo.com/?p=1524
date: '2012-12-24 23:22:19 -0600'
date_gmt: '2012-12-25 04:22:19 -0600'
categories:
- Apple
tags:
- garageband
- effects
comments: []
---
<p>I've had Garageband 11 installed since I got my MacBook, but have never had the default Effects (like Bass Amp, Overdrive, and Phaser). I re-installed the app from the App Store, but this was the only thing that fixed it for me. If this doesn't work for you, I'm afraid I can't be of much help, but I hope this fixes it for you.</p>
<p>For starters, <a href="https://discussions.apple.com/message/15530119#15530119" title="Apple Support">this article</a> pointed me in the right direction.</p>
<ol>
<li>First, check to see if you have folders in this directory: /Library/Audio/Plug-Ins/Components  I had many folders.</li>
<li>Second, copy all of these folders to this directory (I overwrote the few that were in there, but you may want to back up what you have): ~/Library/Application Support/GarageBand/Instrument Library/Plug-In Settings</li>
</ol>
<p>If you want to do all of this from the command line, this command should do the trick:<br />
<code>sudo cp -R /Library/Audio/Plug-Ins/Components/* ~/Library/Application\ Support/GarageBand/Instrument\ Library/Plug-In\ Settings</code></p>
