# VitaDock VLC DIY

This is xCorra's VLC version, if you wnat Crash's MPV version [click here](https://github.com/CrashCortez/vitadock-setup)

I adjusted xCorra's Video Streaming [instructions](https://www.reddit.com/r/vitahacks/comments/a7x735/psvitaopi_vita_video_out_with_raspberry_pi/).

[xCorra VitaDock Video Showcase](https://www.youtube.com/watch?v=do6uWdvBSWk)

[VitaDock video + sound sneak peak](https://youtu.be/uhU4KG8FZ6s)

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

- Download Raspbian lite or with a desktop from:

[Raspberrypi.org downloads](https://www.raspberrypi.org/downloads/raspbian/), remember to use the lite or desktop, NOT the desktop with recomended software.

- Using Win32diskimager or etcher, "write" the unzipped Raspbian image to your SD Card. 

- Once done remove the SD Card from PC and put your card in you pi and boot it up.

- After the first boot set your time zone, language etc. [DO NOT SKIP UPDATE ONCE ASKED] 

- Once everything is done restart your raspberry pi (system message will appear asking you to press reboot).

or 

If you have a card with Raspbian Stretch or used the lite version update and upgrade
```
sudo apt-get update && sudo apt-get -y upgrade
```
- (Optional) If you want to use [Putty](https://www.putty.org/), here is a quick [tutorial](https://youtu.be/h3_zNvAvJtE).

Putty allows you to use a PC to input these commands. Don't forget to enable SSH on the pi. 

# Setup your pi as a BT Reciver and send the vits's sound to your tv via hdmi. 

Since we are using a BT dongle add dtoverlay=pi3-disable-bt to your /boot/config.txt.

- Use putty or terminal on the raspberry pi
```
sudo nano /boot/config.txt
```
- and add 
```
dtoverlay=pi3-disable-bt
```
- Save (CTRL +x), hit Y, then enter.

- Then reboot. 

Once again use Putty or your Pi's terminal

- Copy and paste the following, and press enter, Then follow the on screen prompts.
```
git clone https://github.com/bareinhard/super-simple-raspberry-pi-audio-receiver-install
cd super-simple-raspberry-pi-audio-receiver-install
git checkout stretch-fix
sudo ./install.sh
```
- During the setup it will ask you some questions. Here were my answers.

Answers:

Which installation would you like to choose? (1/2/3/4/5/6) : 2. Install the Raspberry Pi Audio Receiver Home Installation 

Do you want all the Devices to use the same name? (y/n) : y 

Device name: vitadock 

Airplay password (y/n): n 

Which Sound Card are you using? (0/1/2/3/4/5/6/7/8/9/10/11) : 0. No Sound Card


- Reboot the pi when it is finished.

# Setup VLC for Vita Streaming

Here is the script update I promised in the initial tutorial 😉, also I apologize it took so long, but I was doing this and working on Switch to vita bit I didn't expect that switch to vita software side will be so complicated so that took most of my time, again my apologies 😕

- Hacked PSVITA Henkaku/enso/h-encore with uvc plugin by xerpi

- 2 hours of your time

- Raspberry PI (tested only on pi 3 b+, all pi 3 and all pi 2 version will work, others like zero etc. wontbecause the gpu isn’t powerful enough)

- 2 amp charger (best would be 3 amp charger if you have it)

- Micro sd MIN 16GB for Raspberry PI (I recommend using a slower sd card as faster ones tend to fail a lot, tested about 9 sd cards, 2 fastest ones got corrupted, also 1 sandisk card got corrupted so I do not recommend them)

- Any archiving software that has extracting functionality on

- Mouse, keyboard, hdmi cable for for raspberry pi

- Vita usb cable

- WIFI OR LAN (only first time)

- Script 1 : http://www.mediafire.com/file/an79zlgkflhadth/s1.sh/file

- Script 2 : http://www.mediafire.com/file/07v00h7ib75900g/s2.sh/file

- Script 3 : http://www.mediafire.com/file/5qcuqeqnse87ltl/RunPSVITA.sh/file

---------------------------------------------------------------------------------------------------------------------------

1- Make sure that ONLY Mouse, keyboard and HDMI are plugged in the pi, without charging cable

2- Download noobs software from here https://www.raspberrypi.org/downloads/noobs/

3- Make a desktop folder named FSD

4- Extract files from downloaded noobs RAR file to FSD folder you created

5- Insert Micro SD into your PC and format it with this tool as fat32 https://www.sdcard.org/downloads/formatter_4/

6- After formatting copy files from FSD folder to SD (NOT THE FOLDER JUST FILES WITHIN THE FOLDER)

7- When copied EJECT SD card with software first and then pull it out and put in Raspberry PI (its located on the back of the Raspberry pi board)

8- After putting SD card in Raspberry pi plug the charging cable into Raspberry PI

9- When running for the first time it will ask you what OS you want to install, chose Raspberrian by clicking the empty box left from it, once checked click install, press yes on all the boxers that appear

10- After installing set your time zone, language etc. [AND DO NOT SKIP UPDATE ONCE ASKED!!!]

11- After everything is done restart your raspberry pi (system message will appear asking you to press reboot)

12- After rebooting open your browser(blue icon right next to raspberry icon in top left corner), open this reddit post and download scripts s1, s2 and RunPSVITA, once downloaded press ctrl+j on your keyboard, than click show in folder, than drag and drop 3 downloaded scripts to your desktop

13- Now open terminal(black icon, last right icon next to raspberry icon in top left corner) and copy and paste the fallowing, this will allow the scripts to be executable(after copying 1st press enter, than 2nd press enter,3rd press enter):

chmod +x /home/pi/Desktop/s1.sh

chmod +x /home/pi/Desktop/s2.sh

chmod +x /home/pi/Desktop/RunPSVITA.sh

14- Run script s1(when asked click in terminal), script will automatically reboot your raspberry pi when finished, when asked press Y

15- Run script s2(when asked click in terminal), script will automatically reboot your raspberry pi when finished, when asked press Y

16- After reboot, left click raspberry icon, then left click Sound & Video, left click VLC, left click tools, than left click preferences than right click video, than left click output box left to output letters and choose OpenMAX IL video output, then left click save [ONLY ONCE YOU NEED TO DO THIS]

17- To launch vita stream you can A) run the 3rd script, or 😎 open vlc -> media -> open capture device -> set video device to /dev/video0 -> set live caching to 0 -> Play [BOTH METHODS MIGHT TAKE 2 ~ 3 TRIES]

18- When closing stream press s, than close vlc!

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Notes :

- Runs upscaled 1080 30fps, ~2 frame latency

- Proof https://www.youtube.com/watch?v=0ldvrnjzig4

- You can use xerpi's ds3/4 plugin to use controller with vita

- For audio i recommend usb sound card, with aux cable connected to vita's aux to usb audio cards microphone input, also disable usb power on vita to get rid of hissing sound [raspberry cant charge vita anyway]

- If you have raspberrian from before update it to stretch

- Some games may crush, i'm aware and i'm working on a WIFI solution for those games 🙂

- Check out my other ongoing project /r/vitahacks/comments/a632e9/switch_to_vita/

- Fallow https://twitter.com/x_corra for updates 🙂

- If you want to buy pre-configured sd card contact me via twitter 🙂

- Switch to Vita update/demo in 2 days!!!

--------------------------------------------------------------------------

# Releases: 
- Optimized udcd_uvc.skprx for 60 fps: [Download Link](https://github.com/CrashCortez/vitadock-vlc/blob/master/plugin/udcd_uvc.skprx)

- Pi Zero/Zero W premade Image: [Download Link](https://drive.google.com/uc?id=1CVzXpNHRVgTN4eUmLZm2jnp9T2DWijxd&export=download) 

- Pi 3 B/B+ Image: Coming soon. Out for testing.
