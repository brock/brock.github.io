---
layout: post
status: publish
published: true
title: How to Reset a Form Using Javascript
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 854
wordpress_url: http://brockangelo.com/?p=854
date: '2009-06-04 07:53:39 -0500'
date_gmt: '2009-06-04 15:53:39 -0500'
categories:
- Javascript
tags:
- javascript
- form
- reset
comments: []
---
<p><strong>How to Reset a Form Using Javascript</strong></p>
<p>[javascript]<br />
&lt;form&gt;<br />
&lt;input type=&quot;button&quot; onclick=&quot;document.forms[0].reset()&quot; value=&quot;Reset This Form&quot;&gt;<br />
&lt;/form&gt;<br />
[/javascript]</p>
<p>It doesn't clear the data, it just resets all form values to their original value. Here's a demo:</p>
<form>
<input type="text" size="20" value="this comes back"><br />
<input type="text" size="20"><br />
<input type="button" class="button" onclick="document.forms[0].reset()" value="Reset This Form"><br />
</form>
