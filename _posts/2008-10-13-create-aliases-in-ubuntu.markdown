---
layout: post
status: publish
published: true
title: Create Aliases in Ubuntu
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 372
wordpress_url: http://brockangelo.com/?p=372
date: '2008-10-13 13:35:55 -0500'
date_gmt: '2008-10-13 18:35:55 -0500'
categories:
- Ubuntu
- Bash
tags:
- linux
- Ubuntu
- command shell
- alias
- shortcuts
- aliases
- top 10
comments:
- id: 850
  author: ander
  author_email: ander5151@yahoo.com
  author_url: ''
  date: '2010-09-16 11:16:48 -0500'
  date_gmt: '2010-09-16 16:16:48 -0500'
  content: I tried this with Linux Mint 9, but it had no effect.
- id: 2093
  author: Hailon
  author_email: realkankan@gmail.com
  author_url: ''
  date: '2011-03-30 09:26:58 -0500'
  date_gmt: '2011-03-30 14:26:58 -0500'
  content: "<a href=\"#comment-850\" rel=\"nofollow\">@ander </a> \r\nTry .bashrc"
- id: 2161
  author: hippie
  author_email: kindofabuzz@gmail.com
  author_url: ''
  date: '2011-04-25 21:49:45 -0500'
  date_gmt: '2011-04-26 02:49:45 -0500'
  content: <a href="#comment-850" rel="nofollow">@ander </a> you did it wrong then.
    instead of pico, use nano. Pico is not installed by default.
- id: 2239
  author: Zac
  author_email: zachman1094@yahoo.com
  author_url: http://writingconfederation.wordpress.com
  date: '2011-05-17 15:14:39 -0500'
  date_gmt: '2011-05-17 20:14:39 -0500'
  content: "Nice article--I could't remember the syntax for this command, so this
    we helpful!\r\n\r\nJust a quick tip: You can also type the \"alias la=\"ls -alh\"
    directly into the terminal to create an alias. For example, entering the following
    command (minus the \"user:~$\" part) would allow me to enter \"la\" in place of
    \"ls -alh\":\r\nuser:~$ alias la=\"ls -alh\""
- id: 2504
  author: grimfiend
  author_email: davidwyoungblood@yahoo.com
  author_url: ''
  date: '2011-07-13 13:05:25 -0500'
  date_gmt: '2011-07-13 18:05:25 -0500'
  content: I want to set up an alias that uses multiple commands.  Can this be done?  If
    so, how does one go about doing it using the alias command only?
- id: 2505
  author: grimfiend
  author_email: davidwyoungblood@yahoo.com
  author_url: ''
  date: '2011-07-13 13:09:20 -0500'
  date_gmt: '2011-07-13 18:09:20 -0500'
  content: Disregard, just found my answer....thx
- id: 2720
  author: matlix
  author_email: mtf4554@gmail.com
  author_url: ''
  date: '2011-08-11 13:52:57 -0500'
  date_gmt: '2011-08-11 18:52:57 -0500'
  content: "Another way is to create the file ~/.bash_aliases and add your alias command
    there. .bashrc should check to see if the file exists with the lines\r\nif [ -f
    ~/.bash_aliases ]; then\r\n    . ~/.bash_aliases\r\nfi \r\nthen just type source
    .bashrc. Slightly tidier."
- id: 2721
  author: brockangelo
  author_email: email@brockangelo.com
  author_url: http://brockangelo.com
  date: '2011-08-11 14:01:28 -0500'
  date_gmt: '2011-08-11 19:01:28 -0500'
  content: sweet - thanks!
- id: 3937
  author: Igor
  author_email: igor.dawg@gmail.com
  author_url: ''
  date: '2011-10-22 04:41:18 -0500'
  date_gmt: '2011-10-22 09:41:18 -0500'
  content: thanks much!
- id: 3992
  author: How can I run Oracle SQL Developer on JDK 1.6 and everything else on 1.7?
    &laquo; Ukrainian Oracle User Group
  author_email: ''
  author_url: http://oraclecommunity.in.ua/?p=4008
  date: '2011-10-25 07:20:10 -0500'
  date_gmt: '2011-10-25 12:20:10 -0500'
  content: '[...] You&#8217;ll probably want to do something to make this easier on
    yourself such as setting up an alias in Linux or maybe another environment variable
    in [...]'
- id: 5910
  author: fr3nch174l14n
  author_email: fr3nch174l14n@linux420.com
  author_url: ''
  date: '2012-02-27 14:08:50 -0600'
  date_gmt: '2012-02-27 19:08:50 -0600'
  content: '@Zach if you type the alias command directly in terminal, this will be
    effective only during the time of your session. Reboot your machine and the alias
    will have disappeared. For this reason, it had to be hard-coded in .bashrc'
- id: 5942
  author: Spree
  author_email: spreethegr8@gmail.com
  author_url: ''
  date: '2012-03-01 01:35:48 -0600'
  date_gmt: '2012-03-01 06:35:48 -0600'
  content: "Found it useful. I would like to contribute to this, we can also directly
    enter like this open the file in your favourite editor and enter the alias line
    \ and to make the change into effect have to run the following command from home
    directory\r\nsource .bash_profile/.profile\r\n\r\nAfter this you can see the change
    made.(the alias will start working)"
- id: 8144
  author: nohbdy
  author_email: crappy@gmail.com
  author_url: ''
  date: '2012-05-14 16:55:20 -0500'
  date_gmt: '2012-05-14 21:55:20 -0500'
  content: 'For aliasing multiple commands see here: http://ubuntuforums.org/showthread.php?t=1191607'
- id: 8690
  author: Will
  author_email: william.o.frye@hotmail.com
  author_url: ''
  date: '2012-05-25 13:24:28 -0500'
  date_gmt: '2012-05-25 18:24:28 -0500'
  content: "<blockquote cite=\"#commentbody-2239\">\r\n<strong><a href=\"#comment-2239\"
    rel=\"nofollow\">Zac</a> :</strong>\r\nNice article–I could’t remember the syntax
    for this command, so this we helpful!\r\nJust a quick tip: You can also type the
    “alias la=”ls -alh” directly into the terminal to create an alias. For example,
    entering the following command (minus the “user:~$” part) would allow me to enter
    “la” in place of “ls -alh”:\r\nuser:~$ alias la=”ls -alh”\r\n</blockquote>\r\n\r\nTrue,
    just keep in mind though, that it would only work for your current terminal session,
    as when you exit out of the session, all aliases you typed in that way would be
    lost"
- id: 13273
  author: dzy
  author_email: dzy689@gmail.com
  author_url: ''
  date: '2012-10-10 21:47:16 -0500'
  date_gmt: '2012-10-11 02:47:16 -0500'
  content: In Ubuntu 12.04, aliases should be placed in ~/.bash_aliases
---

<p>If you run the same commands in Linux (or Ubuntu) all the time, you can add what is called an "alias" to your user account. For example, I regularly type:</p>
<blockquote><p><code>ls -alh</code></p></blockquote>
<p>So I setup an alias so that I can just type <strong>la</strong>. (also, see my <a href="http://brockangelo.com/2009/05/30/my-top-10-ubuntu-aliases/">Top 10 Aliases</a> list) To do this, simply edit your "profile". Bash is the program that you typically use when you are in a command shell, so it may be called your "bash profile". Your profile is in your Home folder and stores all of your preferences. Just edit the ".profile" or the ".bash_profile" if it exists.</p>
<blockquote><p><code>cd ~<br />
pico edit .profile<br />
</code></p></blockquote>
<p>Add the following code to the bottom:</p>
<blockquote><p><code>alias la='ls -alh'<br />
</code></p></blockquote>
<p>Now when you are typing at the command prompt, you just type <strong>la</strong> and it acts like you typed <strong>ls -alh</strong>. Pretty handy.</p>
