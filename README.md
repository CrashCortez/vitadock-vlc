# Vita Dock VLC DIY

This is xCorra's VLC version, if you wnat Crash's MPV version [click here](https://github.com/CrashCortez/vitadock-setup)

I adjusted xCorra's Video Streaming [instructions](https://www.reddit.com/r/vitahacks/comments/a7x735/psvitaopi_vita_video_out_with_raspberry_pi/).

[xCorra VitaDock Video Showcase](https://www.youtube.com/watch?v=do6uWdvBSWk)

[VitaDock video sneak peak](https://youtu.be/uhU4KG8FZ6s)

Here is what you will need for this build.
----------
- Hacked PSVITA Henkaku/enso/h-encore with [udcd-uvc](https://github.com/xerpi/vita-udcd-uvc) plugin by xerpi

- 2 hours of your time

- Raspberry PI (tested only on pi 3 b+, all pi 3 and all pi 2 version will work, others like zero (testing) etc won't because the gpu isn’t powerful enough)

- 5v 2a amp power supply minimum (The best option would be to use a 3 amp charger if you have it)

- Micro sd MIN 16GB for Raspberry PI (I used a 16gb Scandisk Ultra, but xCorra recommends using a slower sd card as faster ones tend to fail a lot, tested about 9 sd cards, 2 fastest ones got corrupted, also 1 sandisk card got corrupted so he does not recommend them. I did not have this problem over 5 differt cards)

- Mouse, keyboard, hdmi cable for raspberry pi

- Vita usb cable

- WIFI OR LAN (only first time)

- Usb Bluetooth dongle

# Setup Instructions

# Setup your OS

1- Download Raspbian lite or with a desktop from:
-------
[Raspberrypi.org downloads](https://www.raspberrypi.org/downloads/raspbian/), remember to use the lite or desktop, NOT the desktop with recomended software.

2 - Using Win32diskimager or etcher, "write" the unzipped Raspbian image to your SD Card. 
------
3 - Once done remove the SD Card from PC and put your card in you pi and boot it up.
------
4 - After the first boot set your time zone, language etc. [DO NOT SKIP UPDATE ONCE ASKED] 
--------
5 - Once everything is done restart your raspberry pi (system message will appear asking you to press reboot).
---------
or 

If you have a card with Raspbian Stretch or used the lite version update and upgrade
```
sudo apt-get update && sudo apt-get -y upgrade
```
6 - (Optional) If you want to use [Putty](https://www.putty.org/), here is a quick [tutorial](https://youtu.be/h3_zNvAvJtE).

Enable SSH on the pi, if you want to use a pc and putty.
---------

# Setup VLC for Vita Streaming

1 - Settig up vlc for viedo streaming from the Vita
----------
Using PC: 
-----------
Use Putty to connect to your Pi. Copy and paste the following commands, pressing enter after you paste:
```
sudo apt-get -y remove vlc libvlc-bin libvlc5 vlc-bin vlc-data vlc-l10n vlc-plugin-base vlc-plugin-notify vlc-plugin-qt vlc-plugin-samba vlc-plugin-skins2 vlc-plugin-video-output vlc-plugin-video-splitter vlc-plugin-visualization && cd /home/pi/Desktop && wget https://raw.githubusercontent.com/CrashCortez/vitadock/master/vitasetup.sh && wget https://raw.githubusercontent.com/CrashCortez/vitadock/master/RunPSVITA.sh && sudo chmod a+x /home/pi/Desktop/*.sh && sudo reboot
```
Let your pi finish booting, then Using putty log back in, then run the the vitasetup.sh script. Copy and paste the following 
```
cd /home/pi/Desktop && bash vitasetup.sh
```
Using Pi: 
-----------
Now open terminal (black icon, last right icon next to raspberry icon in top left corner) and copy and paste the following:
```
sudo apt-get -y remove vlc libvlc-bin libvlc5 vlc-bin vlc-data vlc-l10n vlc-plugin-base vlc-plugin-notify vlc-plugin-qt vlc-plugin-samba vlc-plugin-skins2 vlc-plugin-video-output vlc-plugin-video-splitter vlc-plugin-visualization && cd Desktop && wget https://raw.githubusercontent.com/CrashCortez/vitadock/master/vitasetup.sh && wget https://raw.githubusercontent.com/CrashCortez/vitadock/master/RunPSVITA.sh && sudo chmod a+x /home/pi/Desktop/*.sh && sudo reboot
```
After reboot, Run script vitasetup.sh (when asked click in terminal), script will automatically reboot your raspberry pi when finished.

2 - After reboot move to the pi, if you were using putty on a pc. 
--------

On the Raspberry pi desktop, left click raspberry icon, then left click Sound & Video, left click VLC, left click tools, than left click preferences than right click video, than left click output box left to output letters and choose "OpenMAX IL video output", then left click save [YOU'll ONLY NEED TO DO THIS ONCE]

3 - Now test your "stream" 
------
To launch the vita "stream" you can: 

A) Run the RunPSVITA.sh script 

B) Open vlc -> media -> open capture device -> set video device to /dev/video0 -> set live caching to 0 -> Play 

[BOTH METHODS MIGHT TAKE 2 ~ 3 TRIES]

or via command line
```
vlc v4l2:///dev/video0 :v4l2-standard= :live-caching=0
```
To Close the "stream" press the S key on your keyboard. 

4 - Setup your pi as a BT Reciver and send the vits's sound to your tv via hdmi. 
------
Since we are using a BT dongle add dtoverlay=pi3-disable-bt to your /boot/config.txt.

Once again use putty or terminal on the raspberry pi
```
sudo nano /boot/config.txt
```
and add 
```
dtoverlay=pi3-disable-bt
```
Then reboot. 

Once again use Putty or your Pi's terminal
-------------

Copy and paste the following, and press enter, Then follow the on screen prompts.
```
git clone https://github.com/bareinhard/super-simple-raspberry-pi-audio-receiver-install
cd super-simple-raspberry-pi-audio-receiver-install
git checkout stretch-fix
sudo ./install.sh
```
During the setup it will ask you some questions. Here were my answers.

Answers:

Which installation would you like to choose? (1/2/3/4/5/6) : 2. Install the Raspberry Pi Audio Receiver Home Installation 

Do you want all the Devices to use the same name? (y/n) : y 

Device name: vitadock 

Airplay password (y/n): n 

Which Sound Card are you using? (0/1/2/3/4/5/6/7/8/9/10/11) : 0. No Sound Card


5 - Reboot the pi when it is finished.
--------
You're Done. 

Connect your Vita to the Pi, launch the RunPSVITA.sh for video, and connect to the vitadock via Bluetooth for sound Grab a ps4 controller and sit on your couch and play your vita on your tv.

How to shutdown the system
----
With Desktop

Hit S on your keyboard, and shutdown normally.

With command line (Raspbian lite or via SSH)
```
sudo shutdown
```


# Notes :

If you want a premade plug and play system check out [xCorra's indegogo](https://www.indiegogo.com/projects/psvita-dock#/)

- Runs upscaled 1080 30fps, ~2 frame latency

- You can use xerpi's ds3/4 plugin to use controller with vita

- For audio I recommend usb bluetooth because you cannot use the onboard BT (testing this). using a usb sound card has lots of additional white noise and distortion, feel free to try on your own, if you figure it out, please let me know.

- I used [BaReinhard's Super Simple Raspberry Pi Audio Receiver Install](https://github.com/BaReinhard/Super-Simple-Raspberry-Pi-Audio-Receiver-Install) for the BT Sound setup, all credit for the BT sound setup goes to him.

- Find a dock and get it printed on [Thingverse](https://www.thingiverse.com/search?q=vita+raspberry+pi&dwh=875cb8a1f5323f8)

# Huge Thanks to xCorra and xerpi.

--------------------------------------------------------------------------

# Releases: 

Coming soon. Out for testing.
