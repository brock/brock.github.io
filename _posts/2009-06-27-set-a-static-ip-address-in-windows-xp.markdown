---
layout: post
status: publish
published: true
title: Set a Static IP Address in Windows XP
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: How to Set a Static IP Address in Windows XP - (w/ screenshots).
wordpress_id: 1133
wordpress_url: http://brockangelo.com/?p=1133
date: '2009-06-27 06:19:06 -0500'
date_gmt: '2009-06-27 11:19:06 -0500'
categories:
- Windows
tags:
- networking
- static ip
- ip address
- dhcp
comments: []
---
<p>To set a Static IP Address in Windows XP, open the <strong>Control Panel</strong> by clicking Start, then Control Panel. Double click on <strong>Network Connections</strong>. </p>
<p>You may have several network connections in this box, depending on your configuration. But most likely you will need to modify the "Local Area Connection". If you are unsure which one to modify, look for the one that is not grayed out and does not have a big red X on it. It doesn't matter what it is called. If you are really brave, you can test to make sure you have the right one by right clicking on it and selecting Disable. Once it is disabled, you should no longer be able to browse the internet. If so, you've found the right Network Connection. (Now right click it and select Enable.)  :)  (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/network_connections/" rel="attachment wp-att-1113">see picture</a>)</p>
<p><strong>Double click</strong> on the "Local Area Connection" icon.</p>
<p>A box will appear with the name of the Network Connection in the title. It will be called the the "Local Area Connection <em>Status</em>" box. The "General" tab will selected. Click the "Properties" button at the bottom. (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/lac_status/" rel="attachment wp-att-1118">see picture</a>)</p>
<p>The "Local Area Connection <em>Properties</em>" box will appear. You will need to scroll down inside the white box until you see "Internet Protocol (TCP/IP)". Select this and click the "Properties" button. (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/lac_properties/" rel="attachment wp-att-1117">see picture</a>)</p>
<p>In the "Internet Protocol (TCP/IP) Properties" box, your setting is probably on "Obtain an IP address automatically". This means that on your local network, your private IP address can change from time to time. To set a S tatic IP Address, click "Use the Following IP Address". (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/ip_properties/" rel="attachment wp-att-1116">see picture</a>)</p>
<p>You shouldn't just guess what IP Address to use, or you'll have a hard time with your local network down the road. Instead, go back to the "Local Area Connection Status" box (it should still be open) and click the "Support" tab. Your current IP address, Subnet Mask and Gateway will be in this box. Change the last number in your IP address to an IP address that is below 100, but not 0 and not 1. It should be an IP address that is not in use. (192.168.1.3 is generally safe) If you want to be sure that the IP Address is not in use, open a command prompt (Start-> Run -> type "cmd" and hit enter) and type "ping 192.168.1.3". If it says "Request Timed Out" then the IP address is not already in use and you are safe to use it for your PC.</p>
<p>Enter this new IP address and the values for Subnet Mask and Default Gateway into the "Internet Protocol (TCP/IP) Properties" box that you were just on. Where it asks for "Preferred DNS Server", enter the value that you used for the Default Gateway <em>(it will probably be the IP address of your Router, most likely 192.168.1.1 or 192.168.0.1)</em>. (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/ip_properties/" rel="attachment wp-att-1116">see picture</a>) Now click OK to all open boxes until you are back at the Network Connections box. Your network connection will now refresh. When you double click on the "Local Area Connection" icon in Network Connections, you can click the Support tab and see the new "Static IP Address".</p>
