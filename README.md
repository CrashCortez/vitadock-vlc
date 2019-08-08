Before anything thank you all for your support, couldn't do it without this wonderful community, and its doubt which made me go all out to make this thing as best as it can be.

Project info if new to all of this -> https://www.indiegogo.com/projects/psvita-dock

Indegogo ended, dock will be available again on Etsy in the future.

Our discord server, come and talk to us about anything. (help, coding, or just chat) https://discord.gg/4zrmZ7X

From xCorra, Bu, ZoidBerg, and his wife Si (icon and video), David-OX, SilentNight and Crash. Special thanks to Xerpi (UCDC_UVC plugin, DS3 and DS4 plguins) and TheFlow (MiniVitaTV).

Video of how it works and looks -> https://youtu.be/isULvvi-gS4

​

Info:

-If you don't have UCDC_UVC plugin, make sure to disable LOLICON plugin before installing ucdc_uvc, after it successfully installs you can re install LOLICON

-Make sure not to power off Raspberry PI because then dock won't work

-Please use Dualshock 4 on your PSVITA, its easier to setup and just works better

-This is not final, there is in updater on this software, I believe there are more thing to be done, stay tuned

​

Features:

-60 FPS video streaming

-Auto start/close streaming (just like Switch dock)

-Audio through Bluetooth so no more static noise from aux

-Updater for dock software

​

Remove features:

-This IMG will NOT support PI ZERO, I tried my best but its slow, and performance varies per PI ZERO, Bluetooth was also a dead end, I'm really sorry. You can use my old version without auto opening that works

-> /r/vitahacks/comments/bhaclc/psvitaopz_beta_b_stream_psvita_to_tv_with_pi_zero/ )

​

Requirements:

-Hacked PSVITA with my custom UCDC plugin made from Xerpi's suggestions (allows true 60 FPS in games that play 60 FPS on PSVITA by lowering resolution + makes display on PSVITA go off, to decrease charging times - 60 FPS on high resolution is usb 2.0 transfer rate limitation and cannot be bypassed, if you decide to use official plugin, it will lag because VLC is locked to 60 and thus it will lag so please use my plugins below)

-> plugin for PSVITA 1000 (oled) https://github.com/xCorra/vita-udcd-uvc/releases/download/v1/udcd_uvc_oled_off.skprx

-> plugin for PSVITA 2000 (lcd) https://github.com/xCorra/vita-udcd-uvc/releases/download/v1/udcd_uvc_lcd_off.skprx

and Dualshock plugin, you can use Xerpi's DS4 plugin

-> https://github.com/xerpi/ds4vita

or TheFlow's MiniVitaTV plugin

-> https://github.com/TheOfficialFloW/MiniVitaTV - If you use MiniVitaTV use my app to disable/enable it because it disables your physical buttons on PSVITA

-> my app - https://github.com/xCorra/SwitchtoPSTV/releases/download/1.0/SwitchtoPSTV.vpk

-Raspberry Pi with 5V 3A power adapter (it can be lower then that but then PSVITA will charger slower)

-PC to flash the premade IMG to SD card

-Mouse and keyboard for 1st startup and setup (can be skipped)

-USB Bluetooth dongle for audio, already set up, just plug the dongle in the PI and connect your PSVITA to it

​

Instructions:

-Download this program for flashing the image to the SD card (for windows) >https://sourceforge.net/projects/win32diskimager/

-Install it

-Download premade IMG -> https://drive.google.com/file/d/1b-92DKZwWxu-H2i0QgQtq-bWK96y0smI/view

-Put your micro SD card into your PC via adapter

-Open win32diskimager

-Click on the blue folder icon and select the premade IMG you downloaded, after selecting it just click write

-After flashing connect your PI to TV via HDMI and also connect your USB'S but don't plug the power and the PSVITA, then put your SD card into the PI, plug it in power and it will start, when it starts you will have a setup screen (if you don't have a mouse and keyboard, just unplug power and plug it back in to skip it, the setup can be re run from apps menu later)

-Connect your PSVITA to dock via Bluetooth (if you have the adapter, if not no sound will come through dock)

-Enable USB charging on PSVITA from settings app

-Connect your PSVITA to dock via USB

-Enjoy!

​

For devs:

This IMG uses rules.d in combination with service files to launch VLC with arguments, more info can be found in rules.d and service directories in the IMG.

Boot video is launched also from a service.

Updater and setup are run from X server autostart .dekstop files

Most scripts are in home directory and root.

This IMG is still based on Debian Stretch.
