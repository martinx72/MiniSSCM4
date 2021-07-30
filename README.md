# MiniSSCM4
for the RGR CM4 carrier for SEGA Saturn Model made by BANDAI

**1**. 
add these at the very end of /boot/cmdline.txt (please make sure everything is in one single line)
```markdown
vt.global_cursor_default=0 logo.nologo loglevel=0 splash silent quiet
```
If you don't want any kernel message printed during booting, you can simply change below in **/boot/cmdline.txt**

> console=**tty1**

to 
>console=**tty3**



**2**. 
Copy files of overlays sub folder of this repo into the **overlays** sub-folder of boot partition of SD card.



**3**. 
Now, copy the right config.txt (don't forget the change the file name from this repo back to config.txt) and
Have fun!
