---
layout: post
status: publish
published: true
title: Run a Batch File Invisibly
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: Run a Batch File invisibly. Users won't know a thing.
wordpress_id: 1279
wordpress_url: http://brockangelo.com/?p=1279
date: '2009-07-14 08:55:40 -0500'
date_gmt: '2009-07-14 13:55:40 -0500'
categories:
- Windows
- Batch
tags:
- batch
- visual basic
- invisible
comments: []
---
<p>Running a batch file invisibly can come in handy, especially if you manage computers for other users. It allows you to perform a task without the user knowing anything about it.</p>
<p>Its very simple. Instead of telling the batch file to run, you tell a Visual Basic script to launch the batch file; and Visual Basic has the ability to launch things invisibly.</p>
<blockquote><p>Follow this demo and you’ll be up and running in just a few seconds</p>
<p>You’ll create two files: the vbs script and a sample batch file</p>
<p>&#160;</p>
</blockquote>
<p>Open Notepad, and paste this content, then save the file as <strong>invisible.vbs </strong>to the Desktop</p>
<blockquote><p>Set WshShell = CreateObject(&quot;WScript.Shell&quot;)     <br />WshShell.Run chr(34) &amp; &quot;C:\Documents and Settings\%username%\Desktop\1.bat&quot; &amp; Chr(34), 0      <br />Set WshShell = Nothing</p>
</blockquote>
<p><a href="http://media.brockangelo.com/all_files_txt.jpg" alt="click to enlarge"><img style="display: block; float: none; margin-left: auto; margin-right: auto" height="284" src="http://media.brockangelo.com/all_files_txt.jpg" width="413" /></a></p>
<p>&#160;</p>
<p>Open Notepad again, and paste this content, then save the file as <strong>1.bat </strong>to the Desktop:</p>
<blockquote><p>echo hello &gt; &quot;C:\Documents and Settings\%username%\Desktop\1.txt&quot;</p>
</blockquote>
<p>&#160;</p>
<p>Now double click on <strong>invisible.vbs</strong>. You should see a <strong>1.txt</strong> file get magically (<em>invisibly</em>) created on the Desktop.</p>
<p>That’s it! Modify to your liking!</p>
