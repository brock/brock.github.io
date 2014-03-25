---
layout: post
status: publish
published: true
title: How to Add Uploaded Media to WP-DownloadManager
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 740
wordpress_url: http://brockangelo.com/?p=740
date: '2009-05-12 14:22:11 -0500'
date_gmt: '2009-05-12 19:22:11 -0500'
categories:
- Ubuntu
- WordPress
- MySQL
tags:
- Ubuntu
- WordPress
- mysql
- scripting
- wp-downloadcounter
- custom field
- wp-downloadmanager
comments:
- id: 216
  author: LikeCamping
  author_email: funky_beware@mthai.com
  author_url: http://www.discounttentstores.com
  date: '2009-05-22 09:05:36 -0500'
  date_gmt: '2009-05-22 17:05:36 -0500'
  content: Thank for Information
- id: 241
  author: KrisBelucci
  author_email: bestblogger@cndnsfive.cn
  author_url: http://www.google.com
  date: '2009-06-01 21:45:48 -0500'
  date_gmt: '2009-06-02 05:45:48 -0500'
  content: Hi, cool post. I have been wondering about this topic,so thanks for writing.
- id: 2831
  author: Ismail
  author_email: sml.bhuiyan@yahoo.com
  author_url: http://www.zipsoft.nazuka.net
  date: '2011-08-17 08:40:11 -0500'
  date_gmt: '2011-08-17 13:40:11 -0500'
  content: Thanks for your valuable information. I will try it......
- id: 2837
  author: Abnehmen
  author_email: email@diaet.com
  author_url: http://www.diaet.com
  date: '2011-08-17 14:26:40 -0500'
  date_gmt: '2011-08-17 19:26:40 -0500'
  content: Thank you for this post. This is what I'm looking for.
---
<blockquote><strong>WARNING: All of the recommendations in this post work off of a test database. The following commands could damage your live site if not tested first. Always work off a test site, then perform a database backup before doing any of these things.</strong></p></blockquote>
<p>I was faced with a challenge at work this week: I wanted to track how many downloads our forms were getting on the company intranet (built on WordPress). I had already uploaded over one thousand forms to the site. I needed an upload tool that would be able to look at all of the forms and other media that we have accumulated. Unfortunately, none of the download counter plugins for WordPress will look add existing media, and they all want you to upload your forms (or media) through their "Add download" button.</p>
<p>Well, if I'd uploaded only a couple of forms, this wouldn't be a problem. But since I was dealing with one thousand, I needed a way to import <em>existing</em> uploads into the new download counter. This would have to be done in MySQL. </p>
<p>I looked at download counters on wordpress.org and found one that I liked: <a href="http://wordpress.org/extend/plugins/wp-downloadmanager/" target="_blank">WP-DownloadManager</a>. There seem to be quite a few of them, including <a href="http://wordpress.org/extend/plugins/wp-downloadcounter/">WP-DownloadCounter</a> (which I also liked) but I chose this one simply because it had been around longer and had a very high rating.</p>
<p>WP-DownloadManager has a way to import existing forms from the management page, but they have to be done one at a time, and you have to manually type all of your titles over again. This would take way too long. So I came up with a way to migrate all of my uploaded form titles and filenames to the WP-DownloadManager's database. </p>
<p><!--nextpage--></p>
<p>I think this is a good time to spell out the configuration of my site (you can skip this page if you just want the code, but do it at your own risk - my configuration is different from the default):</p>
<p>All of our clinic forms are sub-pages of a page called "Forms". Each of the "form pages" uses a custom built <a href="http://codex.wordpress.org/Templates" target="_blank">WordPress Template</a> called "Forms". Each of the form pages points to a file that was uploaded to our local server - <strong>it was not uploaded through the media library</strong> (making this work with the Media Library is possible, I found, but messy - if you need it done, and we're talking about having more than 1,000 media files, leave a comment and I'll post an update). </p>
<p>Since the pdf's and doc's are not "attached" like media uploaded via the Media Library, each page has a custom field called "FileName" and the value of the custom field is simply the filename, like "0423_employee_handbook.pdf". The "Forms template" then points to the directory where the forms are stored (./wp-content/forms/) and the custom field adds the file name to complete the download url.</p>
<p>All of the download managers for WordPress put the title and filename of the download into a MySQL table. Since all of my forms have a custom field called "FileName", I simply need to create a list of those posts. Then I needed to find the values stored in the custom field called "FileName" that links each form page to the download-able form. </p>
<p>Let's translate all of that to MySQL terminology:</p>
<p><!--nextpage--></p>
<p>Here's what we are doing, in terms of what MySQL knows:</p>
<p>The form pages are in the "wp_posts" table, and custom fields are stored in the "wp_postmeta" table in WordPress. The "wp_postmeta" table tracks the "post_id" that each custom field is connected to. The end result of our query should display the column called "post_title" from the "wp_posts" table, and it should display the value inside "meta_value" from the "wp_postmeta" table if the "meta_key" value is called "FileName".</p>
<p>I know this sounds extremely confusing; that's because it is. :-)</p>
<p>So let's get to the code. This shows me the output of all of my uploaded forms that have a value for the custom field "FileName":</p>
<p>[sql]SELECT wp_posts.post_title, wp_postmeta.meta_value FROM wp_posts INNER JOIN wp_postmeta ON wp_posts.ID=wp_postmeta.post_id WHERE wp_postmeta.meta_key = 'FileName' ORDER BY wp_postmeta.meta_value[/sql]</p>
<p>When I typed this in the MySQL Editor, I got a nice long list that showed Form Titles, then Form Filenames sorted by Filename (I sort by filename because all of our forms are prefaced with a four digit number).</p>
<p>Now that you have the list of forms and their filenames, we want to insert this into the WP-DownloadManager's database. The first time I did this, I copied it all to an excel file, reformatted the data, saved as a CSV, uploaded to my server, and so on. But MySQL can handle all of that for you very easily.</p>
<p>But I should point out that WP-DownloadManager tracks things that WordPress doesn't. Specifically, you won't have the file size until you go into the manager and click "Edit". Then PHP automatically calculates the filesize. (I don't think there is a way to have MySQL calculate this as part of our import, but I could be wrong - let me know). <strong>(UPDATE: You can run another script to populate all the file sizes - see the end of this article)</strong>. Permissions and Categories are not available either, but it wouldn't be impossible to map your post categories over to the WP-DownloadManager categories. I just didn't need this so I skipped it.</p>
<p>Executing the following code will take your results and map them to values inside the WP-DownloadManager's database:</p>
<p><!--nextpage--></p>
<p>Executing the following code will take your results and map them to values inside the WP-DownloadManager's database:</p>
<p>[sql]INSERT INTO wp_downloads (file_name, file, file_date, file_updated_date, file_last_downloaded_date) SELECT wp_posts.post_title, wp_postmeta.meta_value, UNIX_TIMESTAMP(wp_posts.post_date_gmt), UNIX_TIMESTAMP(wp_posts.post_date_gmt), UNIX_TIMESTAMP(wp_posts.post_date_gmt) FROM wp_posts INNER JOIN wp_postmeta ON wp_posts.ID=wp_postmeta.post_id WHERE wp_postmeta.meta_key = 'FileName' ORDER BY wp_postmeta.meta_value[/sql]</p>
<p>I should point out that I used the "Post Date" from the WordPress Page and copied this to all three dates inside WP-DownloadManager (file_date, file_updated_date & file_last_downloaded_date). And of course, the hit counter starts at zero. I should also point out (again) that the "FileName" custom field is unique to my configuration.</p>
<p>Just like that I have all of my 1,000 forms showing up in the Download Manager. </p>
<p>Now that they are in the WP-DownloadManager database, I need to find a way to link to the downloads from my template or add the "file_id" value to my wp_posts table. That's because the WordPress pages that I've created for each form only know the file name, they don't know anything about the Download Manager. The pages were created before the WP-DownloadManager created the "file_id" values.</p>
<p>MySQL allows a simple solution to this as well. Since I've already created a custom field called "FileName" and since this value is the same as the "file" value inside the wp_downloads table, I just need to query MySQL and pull in the associated "file_id" value. </p>
<p><!--nextpage--></p>
<p>To connect the "file" value to the "file_id" value, I just add the following function to the bottom of the wp-downloadmanager.php file:</p>
<p>[php]function get_download_id($content) {<br />
	global $wpdb;<br />
	// Get ID numbers from the value in the &quot;file&quot; column<br />
	$content = $wpdb-&gt;get_var(&quot;SELECT file_id FROM $wpdb-&gt;downloads WHERE file ='$content'&quot;);</p>
<p>	return $content;<br />
}[/php]</p>
<p>Then I will pull this variable into each page or template where I want to track downloads. In my case, I add it to the top of the forms.php file:</p>
<p>[php]$downloadID = get_download_id($FileName);[/php]</p>
<p>Where I've pulled my file name into a variable called $FileName.</p>
<p>Then I stick the $downloadID variable on the end of the download url and I have tracking for all of my downloads.</p>
<p>That said, I'm aware that you probably <em>don't</em> have a custom field for all of your file names. If you uploaded via the Media Library, you are in luck. The "file" field in the wp_downloads table matches the "post_title" value in the "wp_posts" table for your attachments uploaded through the media library. So you can match those up the same way that I do in this example, but you'll have to pull in your "post_title" of the attachment and stick it into a variable first. This will vary depending on your template, theme, etc.</p>
<p><!--nextpage--></p>
<p>If you uploaded all of your Media using the Media Library, doing the bulk import will take more work than mine did above. That's because WP-DownloadManager references files by their full file name (like "brockangelo.jpg") but WordPress references them by title and mime type (like "brock_angelo" for the title and "image/jpeg" for the mime type). So for this to work, MySQL would have to conditionally concatenate file names to file types. Not pretty. </p>
<p>On the other hand, if you <em>need</em> to make this happen, you can perform the following query to output the results to the screen, then paste them into excel to do the cleanup. From there, you can pull the information back in through MySQL. This query shows you all of the media that is in your library, with all necessary info you would need to put into excel for a MySQL import back into the WP-DownloadManager database:</p>
<p>[sql]SELECT post_title, post_date_gmt, guid, post_mime_type FROM wp_posts WHERE post_type = 'attachment' ORDER BY ID[/sql]</p>
<p>Leave a comment if you would need instructions on how to finish this up.</p>
<p><!--nextpage--></p>
<p>If you imported all of the forms, and want the file sizes to show up in the database, there is a script that you can put into a php file that will populate all of the file sizes into the database. Thanks <a href="http://lesterchan.com">Lester</a> for helping this along!</p>
<p>I put this in my "single.php" file, but I would guess that you could throw it in any file. You'll put this php code into one of the templates in your theme (single.php, page.php, etc), load the page once so that it will gather all of the info, then you'll need to remove it from the php file. It will populate the database, but in the process, it will throw a warning for each file and display it in your browser. Trust me, it does not look pretty; you get a page full of warnings all over your website. Best to use an unused template or something that no one else will come across. :-)  But it works, or at least it did on my configuration (I'm running an Ubuntu dedicated server). Here you go:</p>
<p>[php]<br />
&lt;?php<br />
$filesizes = $wpdb-&gt;get_results(&quot;SELECT file FROM wp_downloads&quot;);<br />
$location = &quot;/var/www/wp-content/uploads/&quot;;<br />
foreach($filesizes as $fsize) {<br />
	$name = $fsize-&gt;file;<br />
	$size = filesize($location.$name);<br />
	echo $size;<br />
	$wpdb-&gt;query(&quot;UPDATE wp_downloads SET file_size='$size' WHERE file = '$name'&quot;);<br />
} ?&gt;[/php]</p>
