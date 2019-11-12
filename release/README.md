![image](https://github.com/CrashCortez/vitadock-vlc/blob/master/icon/VitaDocklogo.png)
# VitaDock VLC Final


-----------

![image](https://github.com/CrashCortez/vitadock-vlc/blob/master/icon/wooden.jpg)
![image](https://github.com/CrashCortez/vitadock-vlc/blob/master/icon/mini.png)


For the Pi4b, Pi3b+/a+, or Pi3b with bt dongle
---------------
![image](https://github.com/CrashCortez/vitadock-vlc/blob/master/icon/pi4.jpg)
![image](https://github.com/CrashCortez/vitadock-vlc/blob/master/icon/pi.jpg)
![image](https://github.com/CrashCortez/vitadock-vlc/blob/master/icon/pi3b.jpg)

-------------

# Updating this image CAN break the custom VLC build, update at your own risk. 
--------------


# This image includes

VLC

BT Reciever

FileZilla

Onscreen Keyboard

Zram

Auto start/stop vlc stream at usb plug in/out

On/off script For momentary button (pins 5 and 6)

On board BT working (pi4b, pi3b+, pi3a+ only)

BT switch script from external to internal and vice versa

WiFi working - use 5GHz 2.4ghz can case audio issues (US WiFi country)

Enable/Disable scripts for, boot video, Vita notification, and boot text.

-------------
SSH  info
------
hostname: vitadock 

user: pi  

password: raspberry 

-----------------
FileZilla:
-----
Have The VitaDock and your PS Vita on the same network and use  Molecule And SSH over files. Attach a thumb drive or HDD storage to your VitaDock and you can manage your games and files with the dock itself. 

![image](https://github.com/CrashCortez/vitadock-vlc/blob/master/icon/filezilla.png)
 
--------------------- 
Bluetooth:
-------
Name: vitadock 

Note the VitaDock is also a BT Receiver/Speaker, and will act as such sending sound from a device that is connected via BT to your tv (tested with iPhone and Android phone).  

Note the BT on the vita is old, the closer the vita is to the dock the better the sound quality.

-----------------
# FAQ
----
Is there latency?
---
Yes very minimal to none, and I would not use it for a fps competition, but I was able to play Dragon's Lair with a PS4 controller. [Watch Test Video](https://youtu.be/j-mcQHRgISE)

What Pi can I use to build the VitaDock? 
-----
Pi4b, Pi3b/b+/a+ have all been tested and work. This has been fully tested by Crash on the pi3b+ and the pi3a+ with a "Fat" PS Vita and Xerpi's 1.4 UCDC and his PS4 controller plugin from auto plugin vpk. This image has also been tested by M0tie with a "Slim" Vita with a pi4b and a pi3b (with a dongle) and the same plugins.

Can I use a Vita Dock with a capture card?
-----
On my setup with an el gato capture card, I could not capture a good video. It was jumpy and sound was bad on the video. The VitaDock preformed perfectly even if the capture was bad. Others have had no issues witch video/audio captures. 



Credits
---------------
Thank you M0tie for coming back and helping me with this final image release.

Huge Thank You to the original VitaDock team: Bu (m0tie), ZoidBerg, and his wife Si (icon and video), David-OX, SilentNight and Crash. 

Special Thanks to Xerpi (UCDC_UVC plugin, DS3 and DS4 plguins) and TheFlow (MiniVitaTV). For with out their work none of this would be possible. 


-----
# Download link
------------
VitaDock VLC Final pre-made image: [Download](https://drive.google.com/file/d/1athBPeKyaEyIVlC-bIuqu38SslV-cSaj/view?usp=drivesdk)
