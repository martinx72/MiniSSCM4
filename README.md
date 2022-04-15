# MiniSSCM4

for the RGR CM4 carrier for SEGA Saturn Model made by BANDAI
  
  
# MUST KNOW

This toturial is based one RetroPie 4.7.1 image, we got some reports that newer raspbian with newer kernel update has some power warning came out on screen from time to time, but 4.7.1 is totally fine. So please just use 4.7.1 as the major image currently.  
And, you can get RetroPie 4.7.1 right here: https://github.com/RetroPie/RetroPie-Setup/releases/download/4.7.1/retropie-buster-4.7.1-rpi4_400.img.gz  
or the official github repo release page here https://github.com/RetroPie/RetroPie-Setup/releases
  
  
# Tutorial of basic settings

**1**. 
add these at the very end of /boot/cmdline.txt (please make sure everything is in one single line)

```markdown
vt.global_cursor_default=0 logo.nologo loglevel=0 splash silent quiet
```

If you don't want any kernel message printed during booting, you can simply change below in **/boot/cmdline.txt**

> console=**tty1**

to

> console=**tty3**

**2**. 
Copy files of overlays sub folder of this repo into the **overlays** sub-folder of boot partition of SD card.

**3**. 
Now, copy the right config.txt (don't forget the change the file name from this repo back to config.txt) and
Have fun!

**<u>*<mark>NOTE</mark>*</u>**

**If you DON'T copy the <u>prepared </u>and <u>correct </u>config.txt file, the USB port wont even work at all. As the <u><mark>USB</mark></u> on CM4 is set off out of the box. And, some trick also necessary to disable/enable the WiFi or BT of it (if your CM4 came with WiFi/BT, and our config just simply disable WiFi/BT as default), you all need to do modify the confg.txt**.

![](https://raw.githubusercontent.com/martinx72/MiniSSCM4/main/photo/cm4_setting.png)

#

# To install RPi4/CM4 compatible lr-yabasanshiro core

**1**.  
Upate your RetroSetup script to the latest version.

```markdown
sudo ~/RetroPie-Setup/retropie_setup.sh
```

and then execute the `Update RetroPie-Setup script` feature.
![](https://raw.githubusercontent.com/martinx72/MiniSSCM4/main/photo/0000.png)

**2**.  
download necessary patch/script for RetroPie-Setup

```markdown
cd ~/RetroPie-Setup/scriptmodules/libretrocores/
wget https://raw.githubusercontent.com/joolswills/RetroPie-Setup/7fc52613b4c27788bb90530a71231ee67ab65f24/scriptmodules/libretrocores/lr-yabasanshiro.sh
mkdir lr-yabasanshiro
cd ~/RetroPie-Setup/scriptmodules/libretrocores/lr-yabasanshiro
wget https://raw.githubusercontent.com/joolswills/RetroPie-Setup/7fc52613b4c27788bb90530a71231ee67ab65f24/scriptmodules/libretrocores/lr-yabasanshiro/01_shader_hack_rpi4.diff
cd ~/RetroPie-Setup/
sudo ./retropie_setup.sh
```

And now the RetroPie-Setup would be executed again, now, we do as follow steps.  
--> `Manage packages`  
![](https://raw.githubusercontent.com/martinx72/MiniSSCM4/main/photo/001.png)

-> `Manage experimental packages`  
![](https://raw.githubusercontent.com/martinx72/MiniSSCM4/main/photo/002.png)

-> `lr-yabasanshiro` (yes, you have it now!)  
![](https://raw.githubusercontent.com/martinx72/MiniSSCM4/main/photo/003.png)

-> `Install from source`  
![](https://raw.githubusercontent.com/martinx72/MiniSSCM4/main/photo/004.png)

-> `<Yes>`  
![](https://raw.githubusercontent.com/martinx72/MiniSSCM4/main/photo/005.png)

Once the code compiled as expected, then you would copy BIOS/ROM files and restart your EmulationStation.  
And Now it is about time to have fun! :)
