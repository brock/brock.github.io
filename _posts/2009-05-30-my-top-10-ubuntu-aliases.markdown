---
layout: post
status: publish
published: true
title: My Top 10 Ubuntu Aliases
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: 10 Ubunutu Aliases You Can't Live Without
wordpress_id: 773
wordpress_url: http://brockangelo.com/?p=773
date: '2009-05-30 04:25:50 -0500'
date_gmt: '2009-05-30 09:25:50 -0500'
categories:
- Ubuntu
- Bash
tags:
- Ubuntu
- command shell
- alias
- bash
- shell script
- aliases
- command prompt
comments:
- id: 552
  author: Brad Fullmer
  author_email: brad@accessdata.com
  author_url: ''
  date: '2009-07-29 15:42:25 -0500'
  date_gmt: '2009-07-29 20:42:25 -0500'
  content: "Brock,\r\nI am newer to Ubuntu, but loves aliases. Please send me the
    shell script add_alias.sh.\r\nThank,s\r\nBrad Fullmer"
- id: 619
  author: What's in your bin directory?
  author_email: ''
  author_url: http://www.jessirae.com/blog/articles/2009/09/09/whats-in-your-bin-directory
  date: '2009-09-09 20:38:54 -0500'
  date_gmt: '2009-09-10 01:38:54 -0500'
  content: '[...] not terribly creative with my aliases; so, here are some [...]'
- id: 662
  author: Tony
  author_email: Linuxjuicer@gmail.com
  author_url: http://se7ene7es.net
  date: '2009-10-21 22:35:22 -0500'
  date_gmt: '2009-10-22 03:35:22 -0500'
  content: Thanks for the alias suggestions i especially like typing s instead of
    sudo. i also added one called sag="sudo apt-get install" but i would really like
    to take a look at your aa script :)
- id: 1417
  author: Qusai Abu Hilal
  author_email: kousaiey2020@gmail.com
  author_url: http://www.tvquran.com/
  date: '2011-02-18 22:38:26 -0600'
  date_gmt: '2011-02-19 03:38:26 -0600'
  content: "Hello\r\nMy I have your script ?\r\n\r\nThank you in advance !."
- id: 1445
  author: brockangelo
  author_email: email@brockangelo.com
  author_url: http://brockangelo.com
  date: '2011-02-28 05:08:23 -0600'
  date_gmt: '2011-02-28 10:08:23 -0600'
  content: Hey guys, just updated the post to include the shell script. Enjoy!
- id: 2051
  author: Add Aliases in Ubuntu Shortcut | Server Cobra
  author_email: ''
  author_url: http://www.servercobra.com/add-aliases-in-ubuntu-shortcut/
  date: '2011-03-23 00:38:59 -0500'
  date_gmt: '2011-03-23 05:38:59 -0500'
  content: '[...] and upgrades all the packages on my system). While searching for
    other fun shortcuts, I came across this helpful post. It provides a quick way
    to install aliases into your system. I&#039;ve modified it to make it a bit [...]'
- id: 2052
  author: Josh Gachnang
  author_email: Josh@ServerCobra.com
  author_url: http://ServerCobra.com
  date: '2011-03-23 00:41:57 -0500'
  date_gmt: '2011-03-23 05:41:57 -0500'
  content: "Hey I made a few modifications to your script. Mainly, I dumped the aliases
    into ~/.bash_aliases, which is supported in the standard .bash_rc in Ubuntu. I
    also added a note that you simply need to type 'bash' into the terminal for changes
    to take effect instead of logging in and out. I also set up an alias to the script
    (and auto-restarting the terminal after the script) for convenience. Here's my
    write up:\r\n\r\nhttp://www.servercobra.com/add-aliases-in-ubuntu-shortcut/"
- id: 3321
  author: Vijay
  author_email: mali@un.org
  author_url: ''
  date: '2011-09-12 06:02:02 -0500'
  date_gmt: '2011-09-12 11:02:02 -0500'
  content: Cool Stuff, I am very new to Ubuntu and your post is really very helpful
    Thanks!!!
- id: 7332
  author: Alex
  author_email: anatale@luthresearch.com
  author_url: http://luthresearch.com
  date: '2012-04-27 11:19:05 -0500'
  date_gmt: '2012-04-27 16:19:05 -0500'
  content: Sweet! very nice...
- id: 20867
  author: http://greencoffeeadvanceblog.com
  author_email: christelcovey@inbox.com
  author_url: http://www.adagain.com/3/posts/3-Coupons-Gift-Cards/260-health-and-wellness/1217-Green-Coffee-Advanced.html
  date: '2013-04-22 20:16:49 -0500'
  date_gmt: '2013-04-23 01:16:49 -0500'
  content: "Very soon this web page will be famous among all blogging \r\nand site-building
    people, due to it's fastidious articles or reviews"
---
<h2>aka: The Ultimate List of Ubuntu Aliases</h2>
<p>Okay, maybe this isn't the <em>ultimate</em> list, and maybe it's more than 10, but this is my list of essential, must-have aliases for <a href="http://www.ubuntu.com/">Ubuntu</a> (or any version of Linux). Aliases are "shortcuts". For example, if you're at the command prompt and want to exit,  you normally type <code>exit</code>. But I have an alias for the letter <code>e</code> to exit. I cut my typing by 75%!! Do this all throughout your workflow and you'll seriously wonder how you ever lived without it. Backup your aliases. </p>
<p>By adding these aliases, I have turned 277 characters of typing down to just 35. That's a reduction of over 87%!!! Finally, I can leave work at 10am.  :)  </p>
<p>If you want to use an alias in <a href="http://www.ubuntu.com/">Ubuntu Linux</a>, insert these commands (or any other commands that speed up your workflow) at the bottom of your <code>.profile</code> or <code>.bashrc</code> files:</p>
<blockquote><ul>
alias sp='sudo pico'<br />
alias la='ls -alh'<br />
alias m='mutt'<br />
alias e='exit'<br />
alias cdw='cd /var/www/'</p>
<ul>alias cdb='cd /var/www/brockangelo/'<br />
alias cda='cd /var/www/angeloarchive/' <em style="color:blue">(if you host multiple websites, replace the "a" with a website identifier. aka, photoshopsamurai = ps)</em><br />
alias cdps='cd /var/www/photoshopsamurai/'</ul>
<p>alias cdn='cd /usr/local/nagios/etc/'<br />
alias nr='sudo /etc/init.d/nagios restart'<br />
alias ar='sudo /etc/init.d/apache2 restart'<br />
alias coffee='cat > /var/www/brockangelo/coffees.txt' <em style="color:blue">(I used to have a coffee-counter on my website and I would update the number of coffees my espresso machine had made - you can use this to <strong>replace</strong> the contents of a text file quickly)</em><br />
alias s='sudo'<br />
alias aa='/home/brock/scripts/add_alias.sh' <em style="color:blue">(I created a shell script to add new aliases by just typing aa - leave a comment if you'd like to download the script)</em>
</ul>
</blockquote>
<p>And here is the code for the shell script:</p>
<blockquote><ul>
#!/bin/bash<br />
echo Enter the shortcut, or alias, you want to use:<br />
read SHORTTEXT<br />
echo Now enter what text you want it to replace:<br />
read LONGTEXT<br />
echo "alias $SHORTTEXT='$LONGTEXT'" >> ~/.profile<br />
echo "alias $SHORTTEXT='$LONGTEXT' was added to your profile. Changes effective after logout/in."</p>
</blockquote>
