---
layout: post
status: publish
published: true
title: Setup Remote Desktop Using DynDNS
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: Windows has a built-in program that allows you to gain remote access to your
  PC from anywhere in the world. You just need to know how to set it up.
wordpress_id: 1075
wordpress_url: http://brockangelo.com/?p=1075
date: '2009-06-24 08:18:55 -0500'
date_gmt: '2009-06-24 13:18:55 -0500'
categories:
- Windows
tags:
- remote desktop
- vnc
- dyndns
- static ip
- mstsc
comments:
- id: 359
  author: brian bell
  author_email: bbell@parkland.edu
  author_url: ''
  date: '2009-06-24 14:08:39 -0500'
  date_gmt: '2009-06-24 19:08:39 -0500'
  content: hey brock...nice site..good to hear from ya...
- id: 2802
  author: TDR Computers
  author_email: info@tdrcomputers.co.za
  author_url: http://www.tdrcomputers.co.za
  date: '2011-08-16 01:59:02 -0500'
  date_gmt: '2011-08-16 06:59:02 -0500'
  content: "Hey there\r\n\r\nNice post. Very easy to understand and works well.\r\n\r\nThanks"
- id: 20872
  author: lannguyen
  author_email: crystallove122@gmail.com
  author_url: ''
  date: '2013-05-21 10:21:48 -0500'
  date_gmt: '2013-05-21 15:21:48 -0500'
  content: "this is a awesome tutorial. Very clear\r\nthank you"
---
<p>There are a number of ways to get remote access to your home PC. LogMeIn, VNC, Crossloop and several others come to mind. But with most of these, you have to install their software and, in most cases, you have to go through their website to get access to <em>your </em>PC. Fortunately, Windows has a much easier method. </p>
<p>This tutorial will guide you through the process of setting up your PC so that when you are away from home, you will be able to log into it using any other Windows PC (on the planet). When you sit down to the off-site PC, your screen will look identical to the screen you are using at home. We won't be viewing your home PC through a browser. No sir. This will look like you are sitting down in front of your PC. Wallpapers and all.</p>
<blockquote><p>Man, it is the coolest feeling when you use this for the first time and see your screen pop up on someone else's computer, no matter where you are.</p></blockquote>
<p>Let's get started.</p>
<p>To access your PC when you are away from home, we need to run through the following steps:</p>
<ol>
<li>Setup the Home PC to Listen for Remote Desktop Connections</li>
<li>Assign a static IP address to the Home PC</li>
<li>Open a Port in the Router's Firewall to Allow Remote Desktop Connection requests</li>
<li>Setup a free DynDNS account with an easy to remember name</li>
<li>Tell DynDNS to automatically update our Public IP Address</li>
<li>Test it from another Location</li>
</ol>
<h2>Step 1</h2>
<h3>Setup the Home PC to Listen for Remote Desktop Connections</h3>
<ol>
<li>Right click on the My Computer icon on the Desktop or in the Start Menu and click Properties. (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/my_comp_properties/" rel="attachment wp-att-1098">see picture</a>)</li>
<li>Click on the Remote tab</li>
<li>In the "Remote Desktop" box, check the box that says "Allow Users to Connect Remotely to this Computer". Add your username to the list of allowed users, then click OK to exit My Computer Properties. (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/my_computer_remote/" rel="attachment wp-att-1099">see picture</a>)</li>
</ol>
<p>Your computer is now listening for Remote Desktop Connections, and an exception has been made in the Windows Firewall to allow this traffic to come through. But the traffic has no way of knowing where this computer is, so first, let's assign a static IP address to this computer.</p>
<h3>Next Step: Assign a static IP address to the Home PC</h3>
<p><!--nextpage--></p>
<h2>Step 2</h2>
<h3>Assign a static IP address to the Home PC</h3>
<p>Your home network will handle routing all of the Remote Desktop traffic to your Home PC, but first we need to assign a static IP address to your PC. Open the <strong>Control Panel</strong> by clicking Start, then Control Panel. Double click on <strong>Network Connections</strong>. </p>
<p>You may have several network connections in this box, depending on your configuration. But most likely you will need to modify the "Local Area Connection". If you are unsure which one to modify, look for the one that is not grayed out and does not have a big red X on it. It doesn't matter what it is called. If you are really brave, you can test to make sure you have the right one by right clicking on it and selecting Disable. Once it is disabled, you should no longer be able to browse the internet. If so, you've found the right Network Connection. (Now right click it and select Enable.)  :)  (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/network_connections/" rel="attachment wp-att-1113">see picture</a>)</p>
<p><strong>Double click</strong> on the "Local Area Connection" icon.</p>
<p>A box will appear with the name of the Network Connection in the title. It will be called the the "Local Area Connection <em>Status</em>" box. The "General" tab will selected. Click the "Properties" button at the bottom. (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/lac_status/" rel="attachment wp-att-1118">see picture</a>)</p>
<p>The "Local Area Connection <em>Properties</em>" box will appear. You will need to scroll down inside the white box until you see "Internet Protocol (TCP/IP)". Select this and click the "Properties" button. (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/lac_properties/" rel="attachment wp-att-1117">see picture</a>)</p>
<p>In the "Internet Protocol (TCP/IP) Properties" box, your setting is probably on "Obtain an IP address automatically". This means that on your local network, your private IP address can change from time to time. Normally this is okay, but if we are going to start telling our network to point all Remote Desktop Connection traffic to this PC, it needs to be using the same IP address all the time. So click "Use the Following IP Address". (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/ip_properties/" rel="attachment wp-att-1116">see picture</a>)</p>
<p>You shouldn't just guess what IP Address to use, or you'll have a hard time with your local network down the road. Instead, go back to the "Local Area Connection Status" box (it should still be open) and click the "Support" tab. Your current IP address, Subnet Mask and Gateway will be in this box. Change the last number in your IP address to an IP address that is below 100, but not 0 and not 1. It should be an IP address that is not in use. (192.168.1.3 is generally safe) If you want to be sure that the IP Address is not in use, open a command prompt (Start-> Run -> type "cmd" and hit enter) and type "ping 192.168.1.3". If it says "Request Timed Out" then the IP address is not already in use and you are safe to use it for your PC.</p>
<p>Enter this new IP address and the values for Subnet Mask and Default Gateway into the "Internet Protocol (TCP/IP) Properties" box that you were just on. Where it asks for "Preferred DNS Server", enter the value that you used for the Default Gateway <em>(it will probably be the IP address of your Router, most likely 192.168.1.1 or 192.168.0.1)</em>. (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/ip_properties/" rel="attachment wp-att-1116">see picture</a>) Now click OK to all open boxes until you are back at the Network Connections box. Your network connection will now refresh. When you double click on the "Local Area Connection" icon in Network Connections, you can click the Support tab and see the new "Static IP Address".</p>
<h3>Next Step: Open a Port in the Router's Firewall to Allow Remote Desktop Requests</h3>
<p><!--nextpage--></p>
<h2>Step 3</h2>
<h3>Open a Port in the Router's Firewall to Allow Remote Desktop Requests</h3>
<p>Using the address you found for the Default Gateway (mostly likely 192.168.1.1 or 192.168.0.1) open your Internet Browser and type in the address (for example: http://192.168.1.1)  If you've never been to this page before, you will need to find the login information for your router. If you are using a Linksys router, the default login information is to use no username and the password of "admin" (without the quotes). Consult your notes or router documentation if you don't have access. Only you will know this.</p>
<p>On the Router Configuration pages, you will see many pages using names that probably won't mean much to you. A Linksys router menu can be confusing (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/router/" rel="attachment wp-att-1086">see picture</a>).</p>
<p>You'll see things like "NAT", "Access Restrictions", "Applications & Gaming", "Port Forwarding", etc. These probably don't mean much to most people. That's okay. What we are going to use is a feature called "Port Forwarding". Most of the other features won't be used. "Port Forwarding" is found under "Applications & Gaming" on a Linksys Router. </p>
<p>Linksys calls it "Port Range Forward". On the Port Range Forward tab, you will type in a name for the application that you will be using. The Remote Desktop program is a file called "mstsc.exe" which stands for <strong>M</strong>icro<strong>s</strong>oft <strong>T</strong>erminal <strong>S</strong>ervices <strong>C</strong>lient (catchy name, right? :) ), so I call it "mstsc", but you can call it whatever you like. <em>("remote" works well too)</em>  The port range that Remote Desktop Connection uses is 3389, so enter that in the start box and the end box. Remote Desktop Connection uses the TCP Protocol, so select that under the Protocol column. Then enter the new Static IP address in the next box, and be sure to click enable. (<a href="http://brockangelo.com/2009/06/24/setup-remote-desktop-using-dyndns/port_fwd_mstsc/" rel="attachment wp-att-1088">see picture</a>)</p>
<p>You will need to save and apply changes to the router. </p>
<p>At this point, you have enabled Remote Desktop Connections to be accepted on your PC. You've also setup your router to route all incoming Remote Desktop traffic to your PC. At this point, it should work. Using your Public IP Address (not your <em>Static IP Address</em>) you should be able to enter the following in the Start --> Run box:</p>
<p><strong>mstsc /v:your.public.ip.address</strong></p>
<p>This <em>may </em>be your current IP Address: <strong><? echo $_SERVER["REMOTE_ADDR"]; ?></strong></p>
<p>But if this looks like a static IP address, (like <em>192.168.1.1</em>) you'll need to find your Public IP Address. Here's a good place to find it: <a href="http://ipchicken.com" target="_blank">ipchicken.com</a> or <a href="http://checkip.dyndns.com" target="_blank">dyndns</a>.</p>
<p>MSTSC will ask you for your username and password when you try to connect to the PC using Remote Desktop. If it doesn't work, then you need to go back through the steps again and make sure all of the steps are complete. If it does work, great! You're ready for the next step!</p>
<h3>Next Step: Setup a free DynDNS account with an easy to remember name</h3>
<p><!--nextpage--></p>
<h2>Step 4</h2>
<h3>Setup a free DynDNS account with an easy to remember name</h3>
<p>But what if your IP Address changes? Or maybe it doesn't, but you can't remember it...  This is where <a href="http://www.dyndns.com" target="_blank">DynDNS.com</a> comes in. DynDNS will allow you to create an easy to remember name that keeps track of your IP address for you, even after the IP address changes. You can create any name you like, but you'll have to use DynDNS's trailing domain name (like goonies.dyndns.com). So goonies.dyndns.com may point to <? echo $_SERVER["REMOTE_ADDR"]; ?> today, but when your public IP address changes tomorrow, goonies.dyndns.com will update to the new one. Best of all, DynDNS offers this for free for up to five domain names! If you want it to point to what they call a custom domain name, (like goonies.com - without the dyndns part) you can simply pay for an upgrade. </p>
<p>When you go to DynDNS.com, you'll need to create an account the first time. Once you are logged in, click on the Services tab. Then click "Dynamic DNS" and then "Dynamic DNS Free". At the time of this writing, you click the "Get Started" button on the right to start setting up a new dynamic address. </p>
<p>Type in the hostname you want to choose, and select a domain suffix (like dyndns.com or blogdns.org). Leave the Service Type as Host with IP Address, use the auto-detected IP address, and don't setup Mail routing. </p>
<p>Once you have created the account, you may need to give it an hour or two to register in the system. From my experience though, once I've setup a dyndns name, it is live almost immediately. Once it does go live, you should be able to gain access to your desktop from another computer using the new domain name:</p>
<p>mstsc /v:goonies.dyndns.com</p>
<h3>Next Step: Tell DynDNS to automatically update our Public IP Address</h3>
<p><!--nextpage--></p>
<h2>Step 5</h2>
<h3>Tell DynDNS to automatically update our Public IP Address</h3>
<p>Okay, it works now. But you haven't set it up to update when your IP address updates yet. So if your IP address changes overnight tonight, and you go to work tomorrow to show this off, it won't work. :(  You need to download a program to your PC so that it will update your domain name anytime your IP address changes. Go to <a href="https://www.dyndns.com/support/clients/" target="_blank">DynDNS Supported Clients</a> and follow the instructions to download a Windows client to your Home PC.</p>
<p>Installing this program is pretty straightforward. I would leave all of the defaults, and make sure that you have it start with Windows, or else your IP could get changed without updating the DynDNS address. The latest version allows you to install it as a service, which is the better way to do it, so check "Install the DynDNS Updater as a Windows Service", then Install.</p>
<p>Now DynDNS will keep track of your IP address all the time. Anytime it changes, your new DynDNS domain name will update automatically to reflect it. I've been using them for several years, and I can honestly say that I've never once had my DynDNS domain name time out. It is very reliable.</p>
<h3>Next Step: Testing from another Location</h3>
<p><!--nextpage--></p>
<h2>Step 6</h2>
<h3>Test it from another Location</h3>
<p>The Acid Test: leave home and try it from another PC. Man, it is the coolest feeling when you use this for the first time and see your screen pop up on someone else's computer, wherever you are. If you wanna really get some attention, sit down at someone's PC in their house, hit Start --> Run, type "mstsc /v:goonies.dyndns.com", pull up your computer, and watch them go, "Hey! How did you do that!?" It is so fun to see people's response.</p>
