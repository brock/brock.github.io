---
layout: post
status: publish
published: true
title: Replace Text on Click Using JavaScript
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: Did you know that you can replace text using Javascript? I wrote this script
  for our company intranet. In our staff phone directory I show the internal 5-digit
  phone number by default. Clicking the number reveals a 7-digit external phone number.
  Try the demo.
wordpress_id: 955
wordpress_url: http://brockangelo.com/?p=955
date: '2009-06-19 10:12:19 -0500'
date_gmt: '2009-06-19 18:12:19 -0500'
categories:
- WordPress
- Javascript
tags:
- javascript
- text
- replace
- div
comments:
- id: 628
  author: noa
  author_email: veratfw@yahoo.com
  author_url: http://www.neckerdesigns.com
  date: '2009-09-21 11:52:16 -0500'
  date_gmt: '2009-09-21 16:52:16 -0500'
  content: How about when you have more than 2 texts you want to change? I am building
    a website that has a photo gallery and I want the titles to change when I click
    on a thumbnail. I have some javascript that worked in IE, but not in Firefox,
    and I'm hoping to find another code that'll work.
- id: 672
  author: More For Info
  author_email: moreforinfo@gmail.com
  author_url: http://www.morefor.info
  date: '2009-11-01 23:12:25 -0600'
  date_gmt: '2009-11-02 04:12:25 -0600'
  content: That good tutorial. You can add fade effect  to text link. That maybe helpful
    to me.
- id: 2361
  author: SELF DEFENCE COURSE
  author_email: cbletterweb@gmail.com
  author_url: http://self-defence-courses.blogspot.com
  date: '2011-06-11 23:50:03 -0500'
  date_gmt: '2011-06-12 04:50:03 -0500'
  content: Sirs, My business is extremely thankful just for this wonderful post. I
    was carrying out a research for my university project this also post helped me
    just in the nick of their time. I can be very grateful just for this article.
    Thanks a lot.
- id: 20876
  author: Norge
  author_email: comradeangel.spirit@gmail.com
  author_url: ''
  date: '2013-09-13 21:42:33 -0500'
  date_gmt: '2013-09-14 02:42:33 -0500'
  content: "I was wondering if it was possible to replace text like this when a person
    clicks on an image? Or vice-versa?\r\n\r\nAs is, there's an image on the page
    with text below it, and you click on it. Upon clicking on it, the image changes
    to a second image, and the text changes as well to describe the new image.\r\n\r\nThis
    is my image-swapping script:\r\n\r\n\r\nfunction changeImage()\r\n{\r\nelement=document.getElementById('myimage')\r\nif
    (element.src.match(\"http://z5.ifrm.com/30233/37/0/f5229284/EleuKitty.png\"))\r\n
    \ {\r\n  element.src=\"http://z5.ifrm.com/30233/37/0/f5229283/NordKitty.png\";\r\n
    \ }\r\nelse\r\n  {\r\n  element.src=\"http://z5.ifrm.com/30233/37/0/f5229284/EleuKitty.png\";\r\n
    \ }\r\n}\r\n\r\n\r\n\r\n\r\n\r\nClick the kitty and see what happens!\r\n\r\n----\r\nI've
    been meddling with a few different ways my pea-brain thought might achieve the
    desired result, but to no avail."
- id: 20877
  author: Norge
  author_email: comradeangel.spirit@gmail.com
  author_url: ''
  date: '2013-09-13 21:44:11 -0500'
  date_gmt: '2013-09-14 02:44:11 -0500'
  content: "And it would appear that I was stupid enough to not use the code&gt;...\r\n\r\n<code>\r\nfunction
    changeImage()\r\n{\r\nelement=document.getElementById('myimage')\r\nif (element.src.match(\"http://z5.ifrm.com/30233/37/0/f5229284/EleuKitty.png\"))\r\n
    \ {\r\n  element.src=\"http://z5.ifrm.com/30233/37/0/f5229283/NordKitty.png\";\r\n
    \ }\r\nelse\r\n  {\r\n  element.src=\"http://z5.ifrm.com/30233/37/0/f5229284/EleuKitty.png\";\r\n
    \ }\r\n}\r\n\r\n\r\n\r\n\r\n\r\nClick the kitty and see what happens!</code>"
- id: 20970
  author: Ethan
  author_email: flynnx2@rocketmail.com
  author_url: ''
  date: '2013-12-31 06:29:52 -0600'
  date_gmt: '2013-12-31 11:29:52 -0600'
  content: Thank you! I'm relatively new to javascript and your tutorial totally smashed
    the problem I was trying to solve. It was a real buzz to get it to work! Great
    website by the way.
- id: 21199
  author: luiz187
  author_email: luiz.matthew187@gmail.com
  author_url: http://thebestoftheweb.tk
  date: '2014-02-28 17:50:10 -0600'
  date_gmt: '2014-02-28 22:50:10 -0600'
  content: Thank you this really helped me!!!
---
<p><script type="text/javascript" src="/wp-content/themes/downtown-java-3column.js"></script><br />
<script type="text/javascript"><br />
function toggle_text(shown, hidden) {<br />
       var e = document.getElementById(shown);<br />
       var f = document.getElementById(hidden);<br />
    if(e.style.display == 'inline') {<br />
			e.style.display = 'none';<br />
			f.style.display = 'inline';<br />
	}<br />
	else {<br />
			e.style.display = 'inline';<br />
			f.style.display = 'none';<br />
	}<br />
}<br />
</script><br />
This tutorial will show you how to replace text with text by using JavaScript. The text that you click will be replaced with new text. Specifically, we will use JavaScript to hide one div and show another in it's place. Here is a demo:</p>
<blockquote><p><center><br />
<h2>
<div id="shown_first" style="display:inline"><a style="cursor:pointer" onclick="toggle_text('shown_first', 'hidden_first')">Click me	</a></div>
<div id="hidden_first" style="display:none"><a style="cursor:pointer" onclick="toggle_text('shown_first', 'hidden_first')">I used to be hidden!</a></div>
</h2>
<p></center></p></blockquote>
<p>JavaScript does the magic behind the scenes. The way you accomplish this is by putting your two text fields into divs. I'll set the first one to be visible, then when you click on it, I will hide the first and show the second in its place. I use the <code>style.display</code> feature of JavaScript to change whether or not it is visible or shown. Let's take a look at the JavaScript:</p>
<p>[javascript]<br />
&lt;script type=&quot;text/javascript&quot;&gt;</p>
<p>function toggle_text(shown, hidden) {<br />
       var e = document.getElementById(shown);<br />
       var f = document.getElementById(hidden);<br />
    if(e.style.display == 'inline') {<br />
			e.style.display = 'none';<br />
			f.style.display = 'inline';<br />
	}<br />
	else {<br />
			e.style.display = 'inline';<br />
			f.style.display = 'none';<br />
	}<br />
}<br />
&lt;/script&gt;<br />
[/javascript]</p>
<p>I'm simply passing in the two divs to the JavaScript function, then JavaScript checks whether or not the first div (the <code>shown</code> div) is visible or not. If it is visible, it hides it and shows the hidden one. The opposite happens if it isn't visible. Note that using <code>inline</code> will display your text on the same line. If we wanted it to be on its own line, we could just use <code>block</code> instead.</p>
<p>Now you just need to insert the divs into the body of the page. Here is the code used from the sample above:<br />
[html]<br />
&lt;div id=&quot;shown_first&quot; style=&quot;display:inline&quot;&gt;<br />
	&lt;a style=&quot;cursor:pointer&quot; onclick=&quot;toggle_text('shown_first', 'hidden_first')&quot;&gt;<br />
	Click me<br />
	&lt;/a&gt;<br />
&lt;/div&gt;<br />
&lt;div id=&quot;hidden_first&quot; style=&quot;display:none&quot;&gt;<br />
	&lt;a style=&quot;cursor:pointer&quot; onclick=&quot;toggle_text('shown_first', 'hidden_first')&quot;&gt;<br />
	I used to be hidden!<br />
	&lt;/a&gt;<br />
&lt;/div&gt;<br />
[/html]</p>
