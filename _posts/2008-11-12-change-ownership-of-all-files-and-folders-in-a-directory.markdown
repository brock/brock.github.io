---
layout: post
status: publish
published: true
title: Change Ownership of All Files and Folders in a Directory
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 699
wordpress_url: http://brockangelo.com/?p=699
date: '2008-11-12 19:01:26 -0600'
date_gmt: '2008-11-13 00:01:26 -0600'
categories:
- Ubuntu
tags:
- chown
- change ownership
comments:
- id: 8609
  author: john
  author_email: johndoe102@hotmail.com
  author_url: ''
  date: '2012-05-23 21:41:25 -0500'
  date_gmt: '2012-05-24 02:41:25 -0500'
  content: Thank u so much for this. I reformated and lost ownership of some of my
    hard drives partitions and could not revert through sudo nautilus. I'm not that
    familiar with the terminal. That -R was tricky to find as well.
- id: 20880
  author: cum
  author_email: leonoracundiff@gmail.com
  author_url: http://www.usbflashcopy.com
  date: '2013-10-18 15:30:38 -0500'
  date_gmt: '2013-10-18 20:30:38 -0500'
  content: "Do you have a spam issue on this website; I also am \r\na blogger, and
    I was wondering your situation; many of us have developed some nice practices
    and we are looking to exchange solutions with \r\nother folks, be sure to shoot
    me an email if interested."
---

I use dynamic DNS for all of my domain names. This means that from time to time, I'll move a website from one server to another for testing. In these cases, it is helpful to be able to log in as the administrator on the parent account and ftp files through the parent account. It's confusing, I know.

But if you need to log in to FTP as an admin or some other user than the typical owner, you'll find that you can't FTP anything in since the directory is owned by that website. So I go in and quickly change the ownership of all files and folders to the admin user so that I can upload files again. Here's how you do it:

```sudo chown -R adminUserName folderToChown```

* Sudo:  elevate privileges of the user.
* chown: change the ownership of the files
* -R: do it recursively (meaning, do it to all files and folders underneath this point)
* adminUserName: this is the account that you want to own all the files
* folderToChown: this is the top-level folder where ownership changes will be made
