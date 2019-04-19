# Vita Dock DIY

Warning!
--------
This build uses force_turbo=1 which Will void the warranty on your Pi! 


I adjusted X Corra's Video Streaming instructions.

https://www.reddit.com/r/vitahacks/comments/a7x735/psvitaopi_vita_video_out_with_raspberry_pi/

Here is what you will need for this build.
----------
- Hacked PSVITA Henkaku/enso/h-encore with uvc plugin by xerpi

- 2 hours of your time

- Raspberry PI (tested only on pi 3 b+, all pi 3 and all pi 2 version will work, others like zero etc. wontbecause the gpu isn’t powerful enough)

- 5v 2.5a amp power supply (best would be 3 amp charger if you have it)

- Micro sd MIN 16GB for Raspberry PI (I used a 16gb Scandisk Ultra, but X Corra recommends using a slower sd card as faster ones tend to fail a lot, tested about 9 sd cards, 2 fastest ones got corrupted, also 1 sandisk card got corrupted so he does not recommend them. I did not have this problem over 5 differt cards)

- Mouse, keyboard, hdmi cable for raspberry pi

- Vita usb cable

- WIFI OR LAN (only first time)

- Usb Bluetooth dongle

# Setup Instructions

# Setup your OS

1- Download Raspbian with a desktop from:
-------
https://www.raspberrypi.org/downloads/raspbian/

2 - Using Win32diskimager or etcher "write" the unzipped Raspbian image to your SD Card. 
------
3 - Once done remove the SD Card from PC and put your card in you pi and boot it up.
------
4 - After the first boot set your time zone, language etc. [AND DO NOT SKIP UPDATE ONCE ASKED!!!] Also enable SSH if you want to use a pc and putty to help set this up.
--------
5 - Once everything is done restart your raspberry pi (system message will appear asking you to press reboot).
---------
or 

If you have a card with Raspbian Stretch update and upgrade
```
sudo apt-get update && sudo apt-get -y upgrade
```

# Setup VLC for Vita Streaming

1 - Settig up vlc for viedo streaming from the Vita
----------
Using PC: 
-----------
Use Putty to to connect to your Pi. copy and paste the following commands pressing enter after you paste. Now open putty and copy and paste the following:
```
sudo apt-get -y remove vlc libvlc-bin libvlc5 vlc-bin vlc-data vlc-l10n vlc-plugin-base vlc-plugin-notify vlc-plugin-qt vlc-plugin-samba vlc-plugin-skins2 vlc-plugin-video-output vlc-plugin-video-splitter vlc-plugin-visualization && cd /home/pi/Desktop && wget https://raw.githubusercontent.com/CrashCortez/vitadock/master/vitasetup.sh && wget https://raw.githubusercontent.com/CrashCortez/vitadock/master/RunPSVITA.sh && sudo chmod a+x /home/pi/Desktop/*.sh && sudo reboot
```
Using putty, let your pi finish booting, and log back in then run the script, 
```
cd /home/pi/Desktop && bash vitasetup.sh
```
Using Pi: 
-----------
Now open terminal (black icon, last right icon next to raspberry icon in top left corner) and copy and paste the following:
```
sudo apt-get -y remove vlc libvlc-bin libvlc5 vlc-bin vlc-data vlc-l10n vlc-plugin-base vlc-plugin-notify vlc-plugin-qt vlc-plugin-samba vlc-plugin-skins2 vlc-plugin-video-output vlc-plugin-video-splitter vlc-plugin-visualization && cd Desktop && wget https://raw.githubusercontent.com/CrashCortez/vitadock/master/vitasetup.sh && wget https://raw.githubusercontent.com/CrashCortez/vitadock/master/RunPSVITA.sh && sudo chmod a+x /home/pi/Desktop/*.sh && sudo reboot
```
After reboot Run script vitasetup.sh (when asked click in terminal), script will automatically reboot your raspberry pi when finished.

2 - After reboot move to the pi if on pc. On the Raspberry pi desktop, left click raspberry icon, then left click Sound & Video, left click VLC, left click tools, than left click preferences than right click video, than left click output box left to output letters and choose "OpenMAX IL video output", then left click save [YOU'll ONLY NEED TO DO THIS ONCE]
-------
3 - Now test your "stream" 
------
To launch vita stream you can A) run the 3rd script, or open vlc -> media -> open capture device -> set video device to /dev/video0 -> set live caching to 0 -> Play [BOTH METHODS MIGHT TAKE 2 ~ 3 TRIES]

or via command line
```
vlc v4l2:///dev/video0 :v4l2-standard= :live-caching=0
```
To Close the "stream" press the S key on your keyboard. 

or via command line
```
killall vlc
```

4 - Reboot
------
5 - Setup your pi as a BT Reciver and send the vits's sound to your tv via hdmi. 
------
If using a BT dongle add dtoverlay=pi3-disable-bt to your /boot/config.txt. 
once again use putty or terminal on the raspberry pi
```
sudo nano /boot/config.txt
```
and add 
```
dtoverlay=pi3-disable-bt
```
Then reboot 

I used BaReinhard's Super Simple Raspberry Pi Audio Receiver Install : https://github.com/BaReinhard/Super-Simple-Raspberry-Pi-Audio-Receiver-Install

Once again use Putty or your Pi's terminal
-------------
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


6 - Reboot the pi when it is finished.
--------
You're Done. 

Connect your Vita to the Pi, launch the RunPSVITA.sh and the connect to the vitadock via Bluetooth for sound, grab a ps4 controller and sit on your couch and play your vita on your tv.

# Notes :

If you want a premade plug and play system check out X Corra's indegogo: https://www.indiegogo.com/projects/psvita-dock#/

- Runs upscaled 1080 30fps, ~2 frame latency

- You can use xerpi's ds3/4 plugin to use controller with vita

- For audio I recommend usb bluetooth because you cannot use the onboard BT (testing this). using a usb sound card has lots of additional white noise and distortion.

- Find a dock and get it printed
https://www.thingiverse.com/search?q=vita+raspberry+pi&dwh=875cb8a1f5323f8

# Huge Thanks to X Corra and Xerpi.

--------------------------------------------------------------------------

# Releases: 

Coming soon. Out for testing.
