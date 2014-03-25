---
layout: post
status: publish
published: true
title: Removing Categories from your RSS feed
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 154
wordpress_url: http://brockangelo.com/?p=154
date: '2008-09-21 19:47:04 -0500'
date_gmt: '2008-09-22 00:47:04 -0500'
categories:
- WordPress
- PHP
tags:
- php
- rss
- WordPress
comments: []
---
<p><strong>Removing Categories from your RSS feed</strong>: <br />It's pretty straightforward. Just go into your feed files and add a filter saying: "if the post is in one of these categories, don't include it in the feed". Well, that's the basic concept. Here are the details:I edited the <code>/wp-includes/feed-rss.php</code> &amp; <code>/wp-includes/feed-rss2.php</code> You probably should also do the atomfeeds and others found inside wp-includes, but everyone who is subscribed to our blog uses Google Reader, and afaik, Google uses RSS, so I didn't bother. I added the following lines just after the beginning of the loop and right after the </p>
<p>[php]while have_posts : the_post:[/php]</p>
<p>Add this php code:</p>
<p>[php]if ((!(in_category(53))) &amp;amp;&amp;amp; (!(in_category(55))) &amp;amp;&amp;amp; (!(in_category(56)))) : {<br />
[/php]</p>
<p>Where 53, 55 & 56 are categories that you don't want in your feed. Notice that this is an <em>if</em> statement and this ends with an <em>opening</em> curly brace. So all you have to do is close this if statement.</p>
<p>You must close the if statement at the bottom of the file by issuing a <em>closing</em> curly brace and an <code>endif</code> statement just before the <code>endwhile</code>. So the bottom of my "feed-rss.php" looks like this:</p>
<p>[php]<br />
&amp;lt;?php while (have_posts()) : the_post(); ?&amp;gt;<br />
&amp;lt;?php if ((!(in_category(53))) &amp;amp;&amp;amp; (!(in_category(55))) &amp;amp;&amp;amp; (!(in_category(56)))) : { ?&amp;gt;<br />
&amp;lt;item&amp;gt;<br />
&amp;lt;title&amp;gt;&amp;lt;?php the_title_rss() ?&amp;gt;&amp;lt;/title&amp;gt;<br />
&amp;lt;?php if (get_option('rss_use_excerpt')) { ?&amp;gt;<br />
&amp;lt;description&amp;gt;&amp;lt;![CDATA[&amp;lt;?php the_excerpt_rss() ?&amp;gt;]]&amp;gt;&amp;lt;/description&amp;gt;<br />
&amp;lt;?php } else { // use content ?&amp;gt;<br />
&amp;lt;description&amp;gt;&amp;lt;?php the_content_rss(”, 0, ”, get_option(’rss_excerpt_length’)) ?&amp;gt;&amp;lt;/description&amp;gt;<br />
&amp;lt;?php } ?&amp;gt;<br />
&amp;lt;link&amp;gt;&amp;lt;?php permalink_single_rss() ?&amp;gt;&amp;lt;/link&amp;gt;<br />
&amp;lt;?php do_action(’rss_item’); ?&amp;gt;<br />
&amp;lt;/item&amp;gt;<br />
&amp;lt;?php } endif; ?&amp;gt;<br />
&amp;lt;?php endwhile; ?&amp;gt;<br />
&amp;lt;/channel&amp;gt;<br />
&amp;lt;/rss&amp;gt;<br />
[/php]</p>
<p>The Codex article can be found here: <a href="http://codex.wordpress.org/Customizing_Feeds">Customizing Feeds</a>.</p>
