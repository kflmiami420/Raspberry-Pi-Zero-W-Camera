# Raspberry-Pi-Zero-W-Camera
Raspberry Pi Zero W with camera module
2018 Raspberry Pi Zero Camera module 



to get the Camera Module working on a raspberry pi 


sudo apt-get install git-core

       Note: If you get an error installing Git, run sudo apt-get update and try it again.

      

    
    Update and Upgrade  
    
sudo apt-get update 
sudo apt-get upgrade

       1. Enter this at the command prompt to download the library:
To install the GPIO library:

sudo apt install python3-gpiozero  or 
sudo pip3 install gpiozero

        2. Now enter this:

curl -L https://raw.github.com/pageauc/speed-camera/master/speed-install.sh | bash

        IMPORTANT speed-cam.py ver 8.x or greater Requires Updated config.py and plugins.

cd ~/speed-camera
cp config.py config.py.bak
cp config.py.new config.py
To replace plugins rename (or delete) plugins folder per below

cd ~/speed-camera
mv plugins pluginsold   # renames plugins folder
rm -r plugins           # deletes plugins folder
Then run menubox.sh UPGRADE menu pick.

 <div class="Box-body p-6">
        <article class="markdown-body entry-content" itemprop="text"><h1><a id="user-content-raspberry-pi-camera-amazon-s3-uploader" class="anchor" aria-hidden="true" href="#raspberry-pi-camera-amazon-s3-uploader"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Raspberry Pi Camera Amazon S3 Uploader</h1>
<h2><a id="user-content-requirements" class="anchor" aria-hidden="true" href="#requirements"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Requirements</h2>
<ul>
<li>Raspberry Pi + Camera + Network Adapter</li>
</ul>
<h2><a id="user-content-initial-setup" class="anchor" aria-hidden="true" href="#initial-setup"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Initial Setup</h2>
<ul>
<li>
<p>Ensure Raspberry Pi Camera has been enabled:</p>
<ul>
<li>Running <code>sudo raspi-config</code> will get you into the settings to enable</li>
</ul>
</li>
<li>
<p>Install the <code>python-picamera</code> library:</p>
<pre><code>sudo apt-get update
sudo apt-get install python-picamera
</code></pre>
</li>
<li>
<p>Install <code>tinys3</code> library: <code>pip install tinys3</code></p>
</li>
<li>
<p>Install <code>pyyaml</code> library: <code>pip install pyyaml</code></p>
</li>
<li>
<p>Update <code>config.yml</code> and provide S3 credentials as well as specify a bucket name</p>
</li>
</ul>
<h2><a id="user-content-running" class="anchor" aria-hidden="true" href="#running"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Running</h2>
<p><code>python s3cam.py</code></p>
</article>
      </div>
  </div>

Snapping a Picture With Your Raspberry Pi
By now you should have a Raspberry Pi hooked up to an enabled camera module, and everything mounted in a case. You’re now ready to take a photo.

Open a terminal window, and enter this simple command:

raspistill -o image.jpg
This test photo can be found in the Pictures directory on your Raspberry Pi desktop. Other commands are possible.

For example, if the photo is upside down, you can use the -vf and -hf flags to flip the vertical and horizontal axes.

raspistill -vf -hf -o image.jpg
For a full list of commands for taking photos, enter the single command:

raspistill
