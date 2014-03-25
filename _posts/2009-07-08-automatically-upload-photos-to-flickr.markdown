---
layout: post
status: publish
published: true
title: Automatically Upload Photos to Flickr
author: brockangelo
author_login: brockangelo
author_email: brockangelo@gmail.com
author_url: http://brockangelo.com
excerpt: Automatically upload photos & videos to Flickr - you plug in your camera,
  and in just 10 seconds you are walking away with your camera in hand.
wordpress_id: 1158
wordpress_url: http://brockangelo.com/?p=1158
date: '2009-07-08 21:06:07 -0500'
date_gmt: '2009-07-09 02:06:07 -0500'
categories:
- Photography
- Windows
- Python
- Batch
tags:
- flickr
- xp
- Digital Photography
- batch
- backup
- Python
- uploadr
- xmltramp
- automatically upload to flickr
- lifehacker
- photos
comments:
- id: 439
  author: Elizabeth
  author_email: elizabethangelo@gmail.com
  author_url: http://angeloarchive.com
  date: '2009-07-10 06:45:25 -0500'
  date_gmt: '2009-07-10 11:45:25 -0500'
  content: I am a satisfied customer!! :)
- id: 20869
  author: Krysta Mathurin
  author_email: monospore@yahoo.com
  author_url: http://
  date: '2013-05-05 06:50:30 -0500'
  date_gmt: '2013-05-05 11:50:30 -0500'
  content: "On 16 May 2006, Flickr updated its services from beta to \"gamma\", along
    with a design and structural overhaul. According to the site's FAQ, the term \"gamma\",
    rarely used in software development, is intended to be tongue-in-cheek to indicate
    that the service is always being tested by its users, and is in a state of perpetual
    improvement..`\r\n\r\nOur own online site\r\n&lt;http://homeimprovementstuffs.com/<B>
    </B>"
---
<p>Here's how this will work: you'll plug in your card reader or digital camera and all your photos & videos are automatically copied to the folders of your choice in about 3 to 5 seconds. Once the photos are copied to the PC, they are automatically removed from the card (this is optional, but recommended). After they have been deleted from the card, they are automatically uploaded to your <a href="http://flickr.com/photos/brockangelo">Flickr</a> account (as private, public, tagged, not tagged, whatever). All in the background without you having to do a thing.</p>
<p>I set this up because my photography workflow had turned into something horrid: I have two digital cameras that we use. One of the two has video, but I don't use Flickr for my videos, I use <a href="http://motionbox.com" target="_blank">Motionbox</a>. So to get photos or videos off the cameras involved the following:</p>
<ol>
<li>Plug in each card</li>
<li>Copy the pics from the card to the PC, name the folders, etc</li>
<li>Copy the videos to the My Videos folder</li>
<li>Delete the photos & videos from the card</li>
<li>Use the Flickr Uploadr and hope it successfully uploads all the pics</li>
<li>Upload videos to <a href="http://motionbox.com" target="_blank">Motionbox</a>.</li>
<li>Come back later and delete the photos & videos off the PC after they got uploaded</li>
</ol>
<p>I decided to put a little thought into it and get a better setup. I now do the following:</p>
<ol>
<li>Insert flash card into card reader right after taking pictures - <strong>pictures & videos download automatically in less than 10 seconds</strong> - card automatically formats (<i>optional, but recommended</i>)</li>
<li>(<i>photos are now uploading to Flickr in the background - so I leave :) </i>)</li>
</ol>
<p>I've completely eliminated my involvement with the computer. I simply plug in the card reader (or camera) and the computer takes care of the entire process of copying the photos over to the computer, then deleting them from the card. It then automatically uploads the photos to Flickr as private. All in the background without any of my involvement. </p>
<blockquote><p>You can modify the batch file to upload all photos and videos to Flickr.</p></blockquote>
<p>There are several steps you'll need to take in order for the process to be completely automatic. Here is an outline of what all is involved. Start to finish the process takes about 15 minutes.</p>
<ol>
<li>Give Digital Cameras persistent drive letters (E:, F:, G:)</li>
<li>Download Python</li>
<li>Download the "Uploadr" python scripts</li>
<li>Download the batch file for your camera</li>
<li>Install TweakUI and add Batch file to the AutoPlay menus</li>
<li>Configure AutoPlay for your digital camera</li>
<li>Test it out</li>
</ol>
<h2>First Step</h2>
<h3>Give Memory Cards and Digital Cameras persistent drive letters (E:, F:, G:)</h3>
<p>In order for you to be able to reliably copy images from a particular card or device, you should set it up so that every time you plug in the device it uses the same drive letter. With your memory card or device plugged in, right click <strong>My Computer</strong> and select <strong>Manage</strong>: </p>
<blockquote><p> <center><img src="http://media.brockangelo.com/wp-content/uploads/2009/07/my_computer_manage.jpg" alt="my_computer_manage" title="my_computer_manage" width="203" height="132" class="aligncenter size-full wp-image-1162" /></center></p></blockquote>
<p>Select <strong>Storage &#8658; Disk Management</strong> (<a href="http://brockangelo.com/2009/07/08/automatically-upload-photos-to-flickr/disk_management/" rel="attachment wp-att-1163">see picture</a>)</p>
<p>In the right panel, your devices will be listed, probably with letters like E, F or G. Do not change the drive letter of the C: drive, and you probably shouldn't change a D: drive if you have one either. Right click on the flash drive that you need to change and select <strong>Change Drive Letter and Paths</strong>: (<a href="http://brockangelo.com/2009/07/08/automatically-upload-photos-to-flickr/change_drive_letter/" rel="attachment wp-att-1164">see picture</a>)</p>
<p>The next box shows you the letter that is already assigned. Just click <strong>Change</strong>:<br />
<img src="http://media.brockangelo.com/wp-content/uploads/2009/07/change_drive_letter_box-300x194.jpg" alt="change_drive_letter_box" title="change_drive_letter_box" width="300" height="194" class="aligncenter size-medium wp-image-1165" /></p>
<p>This box will ask you what letter you want to assign to it. I start from the bottom, in this case, Z: (<a href="http://brockangelo.com/2009/07/08/automatically-upload-photos-to-flickr/select_drive_letter/" rel="attachment wp-att-1166">see picture</a>)</p>
<p>It will ask you to confirm this. Click <strong>Yes</strong>. (<a href="http://brockangelo.com/2009/07/08/automatically-upload-photos-to-flickr/are_you_sure/" rel="attachment wp-att-1167">see picture</a>)</p>
<p>Repeat this for each card or camera that you would like to setup for this.</p>
<p>Now if you go to My Computer, your drive letters should be updated to the new letters.</p>
<h2>Next Step</h2>
<h3>Download Python</h3>
<p><!--nextpage--></p>
<h2>Step 2</h2>
<h3>Download Python</h3>
<p>Python is surprisingly easy to install. Here is a <a href="http://www.python.org/ftp/python/2.6.2/python-2.6.2.msi" target="_blank">direct download link</a> for the current version (as of July 2009). Take all the defaults, which should install it at <strong>c:\Python26\</strong>, named after the current version. You should always check for the current version at the <a href="http://www.python.org/download/" target="_blank">Python Download page</a>.</p>
<h2>Next Step</h2>
<h3>Download the "Uploadr" python scripts to work with your Flickr account</h3>
<p><!--nextpage--></p>
<h2>Step 3</h2>
<h3>Download the "Uploadr" python scripts to work with your Flickr account</h3>
<p>Uploadr requires two python scripts (.py extensions). The first is the uploadr.py file - found <a href="http://berserk.org/uploadr/uploadr.txt" target="_blank">here</a>. This link takes you to a text file. Create an "uploadr" folder inside your Python installation (<i>c:\python26\uploadr\</i>). Copy the text file and rename it to <i>uploadr.py</i> and save in the uploadr folder.</p>
<p>You'll need to modify two settings. The first is the location of the images where you'll copy photos and then upload to Flickr. I would recommend that you work out of your My Pictures folder.  So start by creating a folder with just a few photos in it that you can test later. </p>
<blockquote><p>IMAGE_DIR = "C:/Documents and Settings/Brock/My Documents/My Pictures/Test/"</p></blockquote>
<p>Then customize the settings that you would like to use for files to upload to your Flickr account. I always upload as Private first (is_public: 0), then review on the site for what I want to make public, but you can do it however you like. Public photos would be "is_public: 1".</p>
<blockquote><p>FLICKR = {"title": ""..."is_public": "0"...}</p></blockquote>
<p>The last thing you need to do after modifying the uploadr.py file is to create a new copy of the file called <strong>uploadr.pyw</strong>, or just rename the uploadr.py to uploadr.pyw.</p>
<p>The second script is called <a href="http://berserk.org/uploadr/xmltramp.txt" target="_blank">xmltramp.py</a>. This link also takes you to a text file. Copy the text file and rename it to <i>xmltramp.py</i>, then save to the uploadr folder. No configuration is needed with this file.</p>
<p>Now you need to test the uploadr.pyw file. Copy some test photos to the IMAGE_DIR folder, then open a command prompt (Start -> Run -> cmd). Change to the uploadr directory by typing "cd c:\phython26\uploadr\". Then simply type <strong>uploadr.pyw</strong>. You'll be asked to give permission to the application by logging into Flickr. Once that is done, go back to the command prompt and confirm that you've given Flickr permission. Now run the uploadr script again and it will copy up the photos to your Flickr account. Log into your account and look for the new photos.</p>
<p>If you have trouble, check <a href="http://lifehacker.com/software/hack-attack/automatically-upload-a-folders-photos-to-flickr-262311.php" target="_blank">this link on Lifehacker</a> for a detailed walk-through of setting up "uploadr". The article on lifehacker details how to set this up so that it continually monitors your My Pictures folder for new photos, but since I only add them by card reader, I prefer to let python stop after it is done uploading pictures. Besides, the batch file takes care of all of that for me.</p>
<h2>Next Step</h2>
<h3>Download the batch file for your digital camera</h3>
<p><!--nextpage--></p>
<h2>Step 4</h2>
<h3>Download the batch file for your digital camera</h3>
<p>Now that you've got uploadr working, you just need to setup the batch file to make it all happen automatically.</p>
<p>Download <a href="http://media.brockangelo.com/upload_cameraName_to_flickr.txt" class="s3-link" target="_blank" alt="Upload to Flickr Automatically">Upload to Flickr Batch File</a>  Rename it to match the camera you'll be using, and change the extension to .bat, like this:</p>
<blockquote><p>upload_eos20D_to_flickr<strong>.bat</strong> (not upload_eos20D_to_flickr.bat<strong>.txt</strong>)</p></blockquote>
<p>I've made it as user-friendly as possible. You'll need to modify the variables in the intro to match your settings. Quotes are important, so make your settings match mine. Here is a summary:</p>
<blockquote><ol>
<li><strong>photoFormat="JPG"</strong> - this value is case sensitive. Look on your flash card and see how your camera saves the files. Canon saves them all in uppercase as JPG and AVI.</li>
<li><strong>videoFormat="AVI"</strong> - same as above - it's okay to leave this if your camera doesn't have video</li>
<li><strong>photoLocation="C:\Documents and Settings\Brock Angelo\My Documents\My Pictures\Canon SD790\"</strong> - this is the full path where you want to copy your photos</li>
<li><strong>videoLocation="C:\Documents and Settings\Brock Angelo\My Documents\My Videos\Canon SD790\"</strong> - this is the full path where you'll copy videos - again, its okay to leave this if you don't have video on your camera</li>
<li><strong>flashcard="Z:\"</strong> - this is the drive where we setup your flash drive.</li>
<li><strong>formatCard="yes"</strong> - If this set to "no" it won't format your card, but I recommend it or else you'll get duplicates on your PC, Flickr, etc.</li>
<li><strong>uploadrLocation="C:\Python26\Uploadr\"</strong> - this is the path where you would find the <strong>uploadr.pyw</strong> file.</li>
</blockquote>
<p>Now save the batch file to your Uploadr folder. And here is the great part - you can modify this file and save a new copy for each camera or flash card that you own. Just make sure that you change all of the variables, drive letters, etc. to match the new card.</p>
<h2>Next Step</h2>
<h3>Install TweakUI and add batch file as an option in the AutoPlay menu</h3>
<p><!--nextpage--></p>
<h2>Step 5</h2>
<h3>Install TweakUI and add batch file as an option in the AutoPlay menu</h3>
<p>Download and install <a href="http://download.microsoft.com/download/f/c/a/fca6767b-9ed9-45a6-b352-839afb2a2679/TweakUiPowertoySetup.exe">TweakUI</a> from <a href="http://www.microsoft.com/windowsxp/downloads/powertoys/xppowertoys.mspx">Microsoft</a>. It's free.</p>
<p>Open it up and navigate to </p>
<blockquote><p><strong>My Computer &#8658; AutoPlay &#8658; Handlers</strong> and click Create (<a href="http://brockangelo.com/2009/07/08/automatically-upload-photos-to-flickr/autoplay_handlers/" rel="attachment wp-att-1246">see picture</a>)</p></blockquote>
<p>From the top:</p>
<ol>
<li><strong>Description</strong>: Upload CAMERA_NAME pictures to Flickr</li>
<li><strong>using</strong>: (<em>optional</em>) uploadr</li>
<li><strong>Args</strong>: (<em>in quotes</em>) "C:\Python\Uploadr\path_to_your_batch_file.bat"</li>
<li><strong>Change Icon...</strong> Choose the Camera icon</li>
<li><strong>Supported Media</strong>: I'd suggest checking Mixed content, Video files & Digital Images.</li>
</ol>
<p>[caption id="attachment_1247" align="aligncenter" width="348" caption="Create AutoPlay Handler"]<img src="http://media.brockangelo.com/wp-content/uploads/2009/07/create_handler.jpg" alt="Create AutoPlay Handler" title="create_handler" width="348" height="405" class="size-full wp-image-1247" />[/caption]</p>
<p>You're almost done!</p>
<h2>Next Step</h2>
<h3>Tell AutoPlay to run batch file for each Flash Card or Digital Camera</h3>
<p><!--nextpage--></p>
<h2>Step 7</h2>
<h3>Tell AutoPlay to run batch file for each Flash Card or Digital Camera</h3>
<p>Plug in your camera or flash card and open My Computer. Right click on the drive letter (Y:, Z:) and select Properties. Click the AutoPlay tab, and choose the Media, and select the appropriate batch file to run each time.</p>
<p>[caption id="attachment_1248" align="aligncenter" width="300" caption="Select your Batch File to run"]<a href="http://media.brockangelo.com/wp-content/uploads/2009/07/set_handler.jpg"><img src="http://media.brockangelo.com/wp-content/uploads/2009/07/set_handler-300x260.jpg" alt="Select your Batch File to run" title="set_handler" width="300" height="260" class="size-medium wp-image-1248" /></a>[/caption]</p>
<p>That's it! You've completed all the steps. Let's give it a whirl.</p>
<h2>Next Step</h2>
<h3>Test out the new configuration on a small number of photos</h3>
<p><!--nextpage--></p>
<h2>Step 8</h2>
<h3>Test out the new configuration on a small number of photos</h3>
<p>Take some new photos with your camera (they can't be photos that uploadr has already uploaded). Just take two or three. Then plug in your camera or flash card. You'll be prompted to run the batch file automatically:</p>
<p><img src="http://media.brockangelo.com/wp-content/uploads/2009/07/run_batch-300x197.jpg" alt="run_batch" title="run_batch" width="300" height="197" class="aligncenter size-medium wp-image-1249" /></p>
<p>If all goes well, you'll see a command window pop up showing you progress. Check your Flickr account and you should see new photos in just a few minutes. I've found this to upload photos even faster than the Flickr website - and what's best of all - I don't have to touch a thing anymore!</p>
<p>I hope this helps - this has certainly taken a great deal of time writing this up - so if you've made it this far, please let me know. And if it is working well for you, I'd love to hear it in the comments.</p>
