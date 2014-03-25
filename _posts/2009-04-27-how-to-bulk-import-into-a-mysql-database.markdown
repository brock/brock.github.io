---
layout: post
status: publish
published: true
title: How to Bulk Import into a MySQL Database
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: Importing data into a MySQL table from a text file or pasting the new data
  into the SQL Editor.
wordpress_id: 726
wordpress_url: http://brockangelo.com/?p=726
date: '2009-04-27 10:21:24 -0500'
date_gmt: '2009-04-27 15:21:24 -0500'
categories:
- Ubuntu
- MySQL
tags:
- Ubuntu
- mysql
- phpmyadmin
- sql
- database
- webmin
comments:
- id: 4347
  author: Ken
  author_email: ken@onkea.com
  author_url: ''
  date: '2011-11-29 19:48:45 -0600'
  date_gmt: '2011-11-30 00:48:45 -0600'
  content: Thanks! Local data infile really saved my day when I had to do a mySQL
    backup from a csv file since my regular backup of my <a href="http://www.justdownforme.com"
    rel="nofollow">website</a> was corrupted for some reason. Great article
- id: 7265
  author: Hassan
  author_email: me@me.com
  author_url: ''
  date: '2012-04-25 17:33:39 -0500'
  date_gmt: '2012-04-25 22:33:39 -0500'
  content: Thanks a lot for the 'load data' version. It helped me import a huge csv
    file.
- id: 18647
  author: John B
  author_email: jkmg.inc@gmail.com
  author_url: ''
  date: '2013-01-03 16:22:35 -0600'
  date_gmt: '2013-01-03 21:22:35 -0600'
  content: This was incredibly helpful for me today!  Thank you.  Just FYI...Method
    one only inserted a single record for me, but method 2 worked perfectly.  Thanks
    again.
---
<p>This tutorial shows you how to take a large number of values and import them as cells in your MySQL database.</p>
<p>Here is a typical scenario: we have a list of account numbers at work that tell us when a patient is in network. If a patient is out-of-network when they come to our clinic, they'll have a hefty bill to pay out of pocket; so the staff searches against a MySQL database that I setup to determine if they are in-network or not.</p>
<p>This database has over 8,000 account numbers in it. From time to time, new account numbers need to be added to the database. I will get an e-mail with anywhere from three to fifty new account numbers to add. If it is a small number, I simply go into PhpMyAdmin and manually add the rows. But if there are more than ten new account numbers, it would take a long time to enter them all by hand. So here are two ways to do it.</p>
<p><strong>Method #1</strong></p>
<p>Create a text file with the new account numbers in it, each on it's own line. It should look like this:</p>
<blockquote><p>
1<br />
2<br />
3<br />
4<br />
5<br />
6<br />
7
</p></blockquote>
<p>Save this text file and upload it to your server where the SQL database resides. If you are on a unix server, the full path would look like this:</p>
<blockquote><p><code>/home/username/accounts.txt</code></p></blockquote>
<p>With it saved to the server, we need to execute SQL code in a database editor like PHPMyAdmin or using the Webmin MySQL Database Server software. Inside this software, you'll want to browse into the database (in this case, let's call it "intranet"). Inside the database, you'll have a table for all of your account numbers (let's call this table "accounts").</p>
<p>You'll want to execute SQL code. Most software packages have an option to "Execute SQL" which works a lot like a command line. In this box, you'll execute the following:</p>
<blockquote><p><code>LOAD DATA LOCAL INFILE '/home/username/accounts.txt' INTO TABLE accounts FIELDS TERMINATED BY 'r' (numbers, id)</code></p></blockquote>
<p>Here is what all of that means:</p>
<p><strong>LOAD DATA LOCAL INFILE:</strong> This simply means to pull the data from the text file that we uploaded from the server and to use the data for our import.</p>
<p><strong>'/home/username/accounts.txt' :</strong> This would be the full path and filename of the text file that has all of your new account numbers. The username value refers to the username on the unix server where the file was uploaded. If you are on a Windows server, it would look more like <code>'C:Documents and SettingsusernameMy Documentsaccounts.txt'</code> or something similar.</p>
<p><strong>INTO TABLE accounts :</strong> This simply means that we want to insert the data into our "accounts" table in our database.</p>
<p><strong>FIELDS TERMINATED BY 'r' :</strong> If you are familiar with Excel, this is like your delimiter. Since I have all of the values on their own line, I use 'r' (which refers to a carriage return, or a new line). If you separate them all by commas, you would just use ',' instead.</p>
<p><strong>(numbers, id) :</strong> These are the column names inside the table where the data will be stored. If you were to open my table, you would see "id" first, then "numbers". The "id" field is the primary key assigned to the row, and the "numbers" field is where my account numbers are. The "numbers" field is listed first because SQL will put the data in the first field. ID will then auto increment.</p>
<p><strong>Method #2</strong></p>
<p>The second method is to paste the new data into your MySQL editor (instead of uploading a text file). </p>
<p><!--nextpage--><br />
<strong>Method #2</strong></p>
<p>The second method is to paste the new data into your MySQL editor (instead of uploading a text file). This can be done relatively quickly once you get the hang of it. </p>
<blockquote><p>TIP: I keep an Excel file as a template so that all I have to do when I am e-mailed the list of account numbers is paste in the new numbers. The formulas in the cells then format the text correctly, and I have the commands saved just above. I just take my mouse, copy all of column A, then paste it into the SQL editor and I am done.</p></blockquote>
<p>Here are the commands you would use to add a column full of strings to a database. <strong>Please note</strong>: I am importing strings, so I use single quotes around the values. I believe if you were using integers you would not want to use quotes.</p>
<blockquote><p><code>INSERT INTO accounts (numbers) VALUES<br />
('F1A0'),<br />
('HB01'),<br />
('T601')<br />
</code>
</p></blockquote>
<p>Where "accounts" is the table name and "numbers" is the column name where the data will be imported. The table it will be imported into has two columns, "id" and "numbers". Since "id" will auto-increment and is the primary key, it will generate an ID number for each new account. You can do this manually if you prefer by modifying it to the following:</p>
<blockquote><p><code>INSERT INTO accounts (numbers, id) VALUES<br />
('F1A0',''),<br />
('HB01',''),<br />
('T601','')...</code></p></blockquote>
<p>This works for multiple columns of data. You would simply display the column titles in the order that the data is listed on your import. For example:</p>
<blockquote><p><code>INSERT INTO accounts (numbers, id, company_name, contact_person, phone) VALUES<br />
('F1A0','','Brooks Brothers','Joe Smith','212-555-1212'),<br />
('HB01','','Talbots', 'Jane Smith', '212-555-2121'),<br />
('T601','','Lexus', 'Jack Smith', '212-555-1122')...</code></p></blockquote>
<p>Good luck - and remember - work off of a test database before you run any of these commands on your system. And backup your database before each new command is run!</p>
