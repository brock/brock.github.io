---
layout: post
status: publish
published: true
title: Show Forms When Radio Button is Clicked
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: Have you been on a website, clicked a radio button, and a form appears with
  text boxes that weren't there before? Here's free code to make that happen with
  Javascript.
wordpress_id: 862
wordpress_url: http://brockangelo.com/?p=862
date: '2009-06-04 08:18:51 -0500'
date_gmt: '2009-06-04 16:18:51 -0500'
categories:
- Javascript
tags:
- javascript
- forms
- hide
- show
- radio
- checkbox
- function
comments:
- id: 7082
  author: hakki
  author_email: mail@desteksitesi.net
  author_url: http://www.desteksitesi.net
  date: '2012-04-17 18:58:09 -0500'
  date_gmt: '2012-04-17 23:58:09 -0500'
  content: "I have a Contact Form 7 form that has 2 radio buttons: Yes and No - when
    the user clicks No, I'd like to enable/unhide a Paypal purchase button. Conversely,
    if they click Yes, I'd like to hide the Paypal button.\r\n\r\nte?ekkürler"
- id: 9491
  author: Kyra
  author_email: tanishay@hotmail.fr
  author_url: ''
  date: '2012-06-17 14:04:35 -0500'
  date_gmt: '2012-06-17 19:04:35 -0500'
  content: Thanks very much for sharing this code. It was really helpful :)
---
<p>I've been using my Javascript a bit more than usual as I've been writing the <a href="http://brockangelo.com/wordpress/plugins/google-chart-generator/">Google Chart Generator</a> plugin for WordPress. Here is one that I think gives an awesome effect. You click a radio button or a checkbox and a form element shows up that wasn't there before. This is helpful for Google Charts because datasets are only available for some types of charts. So it is easier for the user if they don't show up unless they are needed. Here's how it's done:</p>
<p>Create a function inside your javascript tags in the head of your page. This checks to see which radio button was checked. If it is a pie chart, it shows the pie chart entry form and hides the line chart entry form. (and vice-versa) The "chart_type" gets passed in by the form (see below):</p>
<p>[javascript]	function gcg_radio_check(chart_type) {</p>
<p>	if (chart_type == &quot;p3&quot;) {<br />
	document.getElementById(&quot;pie_chart_data&quot;).style.display = &quot;block&quot;;<br />
	document.getElementById(&quot;line_chart_data&quot;).style.display = &quot;none&quot;;<br />
	}<br />
	if (chart_type == &quot;lc&quot;) {<br />
	document.getElementById(&quot;line_chart_data&quot;).style.display = &quot;block&quot;;<br />
	document.getElementById(&quot;pie_chart_data&quot;).style.display = &quot;none&quot;;<br />
	}<br />
     }<br />
[/javascript]</p>
<p>Now we need to create our form element, and pass the chart_type value to javascript so it can decide what to do. We do this by passing "value" in the function parameter.</p>
<p>[html]<br />
&lt;form&gt;<br />
&lt;input type=&quot;radio&quot; name=&quot;gcg_charttype&quot; onClick=&quot;gcg_radio_check(value);&quot; value=&quot;bhs&quot;&gt;Bar Chart&lt;br /&gt;<br />
&lt;input type=&quot;radio&quot; name=&quot;gcg_charttype&quot; onClick=&quot;gcg_radio_check(value);&quot; value=&quot;lc&quot;&gt;Line Chart&lt;br /&gt;<br />
&lt;/form&gt;<br />
[/html]</p>
<p>So if I clicked the radio button for "Bar Chart", it passes this to javascript: <code>gcg_radio_check(bhs)</code></p>
<p>Lastly, we need to create the form that will be displayed once we click the radio box. I set it to <code>display:none</code> so that it is hidden by default:</p>
<p>[html]<br />
&lt;div id=&quot;pie_chart_data&quot; style=&quot;display:none&quot;&gt;<br />
	&lt;h3&gt;Data Points&lt;/h3&gt;<br />
	&lt;table&gt;<br />
		&lt;tr&gt;<br />
		&lt;input type=&quot;text&quot; size=&quot;4&quot; name=&quot;gcg_chartdata&quot; value=&quot;&quot;&gt; Data1<br />
		&lt;input type=&quot;text&quot; size=&quot;6&quot; name=&quot;gcg_data_color&quot; value=&quot;&quot;&gt; Color<br />
		&lt;input type=&quot;text&quot; size=&quot;10&quot; name=&quot;gcg_labels&quot; value=&quot;&quot;&gt; Label&lt;br /&gt;<br />
		&lt;/tr&gt;<br />
	&lt;/table&gt;<br />
&lt;/div&gt;<br />
[/html]</p>
<p>Then repeat this for the line chart and any other forms you want to hide or show.</p>
