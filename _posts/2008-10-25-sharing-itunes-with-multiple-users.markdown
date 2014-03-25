---
layout: post
status: publish
published: true
title: Sharing iTunes with Multiple Users
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
wordpress_id: 331
wordpress_url: http://brockangelo.com/?p=331
date: '2008-10-25 16:19:49 -0500'
date_gmt: '2008-10-26 00:19:49 -0500'
categories:
- Windows
- Apple
tags:
- Windows XP
- iTunes
- Apple
- mac
- iPod
- music
comments:
- id: 205
  author: houdjak
  author_email: sacarose@hotmail.com
  author_url: ''
  date: '2009-02-06 19:06:40 -0600'
  date_gmt: '2009-02-07 03:06:40 -0600'
  content: Thanks.
- id: 237
  author: Michael
  author_email: heelots@gmail.com
  author_url: ''
  date: '2009-05-28 17:24:56 -0500'
  date_gmt: '2009-05-29 01:24:56 -0500'
  content: "Nice and concise...and with a few tweaks, it works for me. I have a FreeNAS
    server holding my 10000+ mp3s that I want to share using my Macbook and a Wintel
    notebook.\r\n\r\nStep 2 (Map a network drive....) doesn't work under OS X, but
    since \"freenas\" showed up in my Finder sidebar, I was able to point iTunes to
    the Music subdirectory on the server in Step 3.\r\n\r\nThanks!"
- id: 238
  author: brockangelo
  author_email: email@brockangelo.com
  author_url: http://brockangelo.com
  date: '2009-05-28 18:10:04 -0500'
  date_gmt: '2009-05-29 02:10:04 -0500'
  content: "Michael, \n\nThanks for your comment. On a Mac you can set this up to
    connect on startup if you haven't done this already. From the Finder, click CMD
    + K. This opens your \"Connect to Server\" dialog. You probably already setup
    login information in here (it will remember it later). Then, if you want it in
    your startup, go to System Preferences -&gt; Accounts -&gt; (go to your account)
    -&gt; Login Items. Then at the bottom of this screen, click the + (the plus icon)
    to add the mapped network drive. If it is already mounted, you'll go to Network
    -&gt; Servername -&gt; Connect -&gt; Choose the sharename.\n\nI don't think it
    is as obvious on the mac. :-) But once it is in the startup, it works every time.\n\nLater"
- id: 296
  author: Michael
  author_email: heelots@gmail.com
  author_url: ''
  date: '2009-06-14 22:02:17 -0500'
  date_gmt: '2009-06-15 06:02:17 -0500'
  content: "So, we've noticed something strange, now that things are up and running.
    \r\n\r\nWe have a FreeNAS server running, with all our MP3s in a /media/music
    directory. I dutifully went to both computers (a Macbook Pro and an HP Windows
    XP notebook) and followed your steps. (I created two folders for the iTunes libraries
    on the network -- one's called \"iTunes on HP Notebook,\" the other is \"iTunes
    on Macbook Pro.\")\r\n\r\nRan iTunes on each computer -- it found all the MP3s,
    created iibraries, found cover art, calculated gapless recording parameters, etc.\r\n\r\nEverything
    seemed fine. However....\r\n\r\nIn practical use (on the Windows XP notebook),
    we found that when we added MP3s to the network drive -- then manually added them
    to iTunes via \"add a folder\" -- iTunes would add them...but when we'd quit the
    program and go back into it later, they'd be gone. The actual files were still
    there, they just weren't in the library anymore. Ditto with any playlists that
    we created. They'd simply vanish.\r\n\r\nNot so on the Mac side. MP3s I add and
    playlists I create survive quitting the program and re-starting the program.\r\n\r\nAny
    ideas as to why this might be happening?\r\n\r\nBy the way, I didn't try the \"connect
    to server\" suggestion you talked about in that previous post...not sure I need
    to? I guess I'm not sure what it gives me that I don't already seem to have....\r\n\r\nThanks,\r\nMichael"
- id: 297
  author: brockangelo
  author_email: email@brockangelo.com
  author_url: http://brockangelo.com
  date: '2009-06-15 04:35:42 -0500'
  date_gmt: '2009-06-15 12:35:42 -0500'
  content: "Michael,\n\nWhen you \"Ran iTunes on each computer - it found all the
    MP3's,...\"  did you point it to the new libraries that you just created?\n\nFirst
    thing, check your FreeNAS music folder for any additional \"iTunes\" folders.
    You should just have \"iTunes on HP Notebook\" and \"iTunes on MacBook Pro\".
    If you also have an \"iTunes\" folder, that is the problem. One got setup with
    its own library. (it's probably not this, so I'll move on to step two - but check
    it to be thorough)\n\nIt sounds like your iTunes can read from your FreeNAS music
    share, but it doesn't sound like it has permission to write to it. \"...but when
    we'd quit the program and go back into it later, they'd be gone\" Quitting the
    program is when iTunes saves the changes to the database, so most likely it is
    buffering the changes, then, when you close the program, it just quietly fails.
    Open a folder to the music share by opening a command prompt in XP and going to:
    \\\\freenas-server-name\\music-share-name\\  Try to create a txt file. If it fails,
    you've found the problem. If it doesn't fail, then navigate into the iTunes folders
    and do the same, try creating a text file. If it lets you write to the folder,
    then iTunes should be able to write to the folder as well. \n\nLet me know what
    you find."
- id: 299
  author: Michael
  author_email: heelots@gmail.com
  author_url: ''
  date: '2009-06-15 12:58:38 -0500'
  date_gmt: '2009-06-15 20:58:38 -0500'
  content: "Hi, Brock, and thanks for those suggestions.\r\n\r\nFirst, I checked the
    media folder where I store the iTunes folders for the HP and the Macbook...there
    were no extra iTunes folders.\r\n\r\nAt an XP command prompt, I tried to navigate
    to the network drive using the method you suggested...to no avail....\r\n\r\n\"CMD
    does not support UNC paths as current directories.\"\r\n\r\nHowever, I have the
    folder where the iTunes library folders are stored mapped as a network drive (Z:\\),
    so I cd'd to Z: and then cd'd to Z:\\Media (that's where the library folders are
    stored).\r\n\r\nI was able to create (and delete) both new directories with the
    \"md\" command, as well as text files with the \"edit\" command.\r\n\r\nThis is
    getting puzzling...and I really appreciate your taking the time to help me out....\r\n\r\nThanks!"
- id: 300
  author: Michael
  author_email: heelots@gmail.com
  author_url: ''
  date: '2009-06-15 13:07:03 -0500'
  date_gmt: '2009-06-15 21:07:03 -0500'
  content: "Forgot to note this....\r\n\r\nAfter quitting iTunes on the XP laptop,
    when I go to the \"iTunes on HP Laptop\" folder, the files \"iTunes Library.xml\"
    &amp; \"iTunes Library.itl\" show \"Date Modified\" dates and times that are consistent
    with the date &amp; time I quit iTunes. \r\n\r\nClearly, something is getting
    changed in those files -- they're just not getting updated with the MP3s I add
    or playlists I create.\r\n\r\n(But the Mac side is still working fine....)\r\n\r\nThanks!"
- id: 302
  author: brockangelo
  author_email: email@brockangelo.com
  author_url: http://brockangelo.com
  date: '2009-06-15 16:47:25 -0500'
  date_gmt: '2009-06-16 00:47:25 -0500'
  content: "The date modified will change even if no changes were made to the database...\n\nI
    would guess that it is still a permissions issue with FreeNAS. Is the share setup
    with write access for everyone? My FreeNAS box got retired when I did an upgrade
    recently, so my music share is on my XP machine mounted as M:\\. When I was using
    FreeNAS though, I had a wide open share that was world writable. If I remember
    right, if I used Windows Share Level permissions on FreeNAS, I wasn't able to
    write anything to it. \n\nYou may also try connecting to the share at the CMD
    prompt using the IP address: \\\\192.168.1.100\\music-share\\.\nIf that works,
    you would want to make sure that you re-map your network drive using the IP. Not
    likely, but another thought.\n\nI don't think this is it either, but it came up
    in a search: Right click My Computer, Properties, Advanced, Performance Settings,
    Advanced tab, Memory Usage box: is \"Programs\" checked? One user said that this
    made the difference."
- id: 703
  author: Desi
  author_email: sites@desipilot.com
  author_url: ''
  date: '2009-12-14 07:28:49 -0600'
  date_gmt: '2009-12-14 12:28:49 -0600'
  content: "Hi - I setup FreeNAS and setup itunes server on freenas also.  I can see
    my files but iTunes does not see the music share.\r\n\r\nAny ideas what am I missing?\r\n\r\nThanks."
- id: 704
  author: brockangelo
  author_email: email@brockangelo.com
  author_url: http://brockangelo.com
  date: '2009-12-14 08:27:12 -0600'
  date_gmt: '2009-12-14 13:27:12 -0600'
  content: I have since abandoned FreeNAS in favor of using a Windows XP box as my
    home server. I was having similar problems with the share, as a couple others
    have mentioned too. I haven't played with FreeNAS enough to figure it out, and
    I've found that XP worked better in the role of a file server anyway. I hope this
    helps.
---
<p><strong>How to share iTunes with a Mac & a PC, using one collection of music, and multiple users & computers :<br />
</strong></p>
<p>So here is exactly what you'll get as the result of this tutorial: all of your PC's will have the exact same iTunes library. If you open up iTunes on your laptop, it will look exactly like the iTunes on your PC. It will see the same podcasts, same videos, same playlists, you get the idea.</p>
<p>However, if you have a Mac, that will have a different iTunes library. You won't have duplicate MP3 files, but you will have a different "library". Apple calls the music database your iTunes library. It's just a fancy way of saying "your list of music". Now then, anytime you add music in iTunes on the PC, <strong>you'll have to manually add it</strong> to the iTunes library on the Mac if you want the music to appear. If you have multiple Macs, they'll all share the same library, so a change to the Mac iTunes library will look the same on all Macs.</p>
<p>This is how my wife and I wanted it. We have a large collection of music, a Desktop PC, a Vista Laptop, and a MacBook. We wanted to be able to save our music (the MP3's) to one place (our home media server) but be able to access it from any computer and be able to plug in our iPods to any computer to sync the new stuff.</p>
<p><strong>1. Copy all of the music to one folder</strong> in Windows XP (like C:\music). Now share this folder using Windows File Sharing (right click the folder and select Sharing) then be sure to click "allow users to edit the files".</p>
<blockquote><p><del datetime="2009-12-14T13:27:51+00:00">If you are computer savvy and have considered setting up a home server, you can do what I did and install a <a href="http://freenas.org/">FreeNAS</a> server instead. It is a separate computer used just for the music. (or in my case, music, photos, video & documents) It does the job really well, but I wouldn't recommend this unless you need a Network Attached Storage device. Don't know what I mean? Then use Windows XP. You'll be much happier. :)</del></p></blockquote>
<blockquote><p>Several of you reported that you were having issues with FreeNAS, and I came up against a few roadblocks myself. I haven't played with FreeNAS enough to figure out why it doesn't work out of the box, but Windows XP does. I replaced my FreeNAS server with Windows XP and have not had any problems since. I would recommend setting up a Windows XP box with file sharing and keep your music on this box. - Again, this is only if you want a central file server. For most folks, sharing the C:\music folder on your primary PC will do the job just fine.</p></blockquote>
<p>	<strong>2. Map a network drive on all computers</strong> (even the Windows XP machine where your music is located). Map the drive to this shared folder and call it the M:\ drive (music, media, etc). Make sure you have copied all of your music into this folder. (yes, do this before you open iTunes for the first time)</p>
<p>	<strong>3. Fire up iTunes for the first time</strong> on the host computer, but hold down the shift key on a PC (or Alt/Option on a Mac) while it is opening. Select Create a New Library, and point it to your M:\ drive (it will create a folder called M:\ITunes if it doesn't already exist). </p>
<blockquote><p>
Here's what you need to know: your music will be located in the M: drive. iTunes will create a folder inside the M: drive called iTunes. No music will be inside the "M:\iTunes" folder. This is just where your newly created library will live and where the database that keeps track of all of your music will save information about your music.
</p></blockquote>
<p>	4. Now then, if you are also going to use a Mac with this collection of music, you have to <strong>create a different iTunes library</strong> database. No, you don't have to copy any of your music. You can still point the library to the same music files, but iTunes libraries are specific to the OS, so you will need to create a separate iTunes folder. I call mine "iTunes for Mac" so it is clear. So when you start up your Mac iTunes for the first time, hold down Alt/Option and select "Create Library". Now it will ask you where you want to save the new library. Go into your M: drive and select "M:\iTunes for Mac" (or create this folder now if it doesn't exist).</p>
<blockquote><p>Something important to note about this: these are different databases. Changes made to the PC library and the Mac library are not the same. But, the music is in the same shared location. So if I'm on my PC and I copy a new CD into my library, it is copying into the iTunes Library for PC's only. The iTunes for Mac library won't ever know about the new CD. So you must go in and select "Add Folder to Library" when a new album has been added to the other library. </p></blockquote>
<blockquote><p><strong>NOTE: </strong>If you open a PC iTunes library with your Mac iTunes, it will break all of the links and you'll have to recreate the library from the PC again. Remeber, the "library" is different from all of your MP3 files. The library is just the iTunes database, and it is only chosen when you first set up iTunes. If you do make this mistake, it's not big deal. Just go back to the PC and delete the iTunes library folder then recreate a new library. Remember, the iTunes folder is just the database and doesn't touch your music files.
</p></blockquote>
<p>	5. On each machine, one at a time, go into iTunes, Preferences, Advanced Tab and <strong>change the iTunes Music Folder location</strong> to M:\ (not M:\ITunes). When you import CD's later on any of the machines, it will then save your music into the M:\ folder (not the M:\ITunes folder). That way, if you have to recreate the database, music isn't mixed up with your iTunes folder. You may lose some playlists, but music files will still be there.</p>
<p>	6. I uncheck both the <strong>Copy to iTunes folder</strong> and the <strong>Keep my Music Organized</strong> boxes. "Nope, I'm good. I can handle keeping my files organized. Thanks."</p>
<p>	7. Once you have setup your iTunes Libraries on one PC and one Mac, your ready to add other PC's to those libraries. When adding new computers, hold down the shift key and click "Choose Existing Library". This will allow new computers to share the existing library and all your stars, playlists, etc. instead of creating their own. You will share all of your settings. But remember to choose the correct library for your OS ("iTunes" folder for the PC's and "iTunes for Mac" folder is how I set them up).</p>
<blockquote><p>One other important thing to note is that iTunes doesn't save the database until you close the application, so if you make changes to one copy of iTunes, you have to close it before another PC accesses the library again if you want to see the changes right away.
</p></blockquote>
<p>That's it. I hope this helps someone. It keeps our music synced in our house, and so far we haven't had any problems with it.</p>
