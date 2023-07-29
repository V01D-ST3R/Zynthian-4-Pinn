# Zynthian-4-Pinn
This is a pre-made Zynthian image compatible with Pinn multiboot running on the Raspberry Pi 4

*Check back the README.md for any future changes.*

# **Link to the Zynthian OS folder:**

Download the file from any provider below

----------------***WIP Updating to latest ZynthianOs***----------------

Host 1. [Sync]()WIP

Host 2. [Mega]()WIP

Host 3. [Google Drive]()WIP

# **Note:**

1. `USB(1)` Primary USB that will contain Pinn and any other OS `(I recommend 32GB or more if installing 3+ different Operating Systems)`
2. `USB(2)` Different USB with `8GB min` which will contain the OS folder for Pinn to see/detect Zynthian.
3. Recommend to use RPI Imager to flash the bootloader with "USB Boot" (Unless using a MicroSd card)
4. It looks like you can ***`allocate more space to Zynthian`*** by messing with **OS/Zynth/***partitions.json*****                          
***`"edit the second section under; ext4/rootfs"`*** --> "partition_size_nominal": `(default 15108)` <-- set to whatever size you want (this would be 15GB). <sub> ***(Do not mess with "uncompressed_tarball_size: 11608" as this is the size required for the Zynthian image)***<sub>
5. The "root=" will look different for MicroSD and USB. Ex: `MicroSD= "root=/dev/mmcblkXXX"` and `USB= "root=PARTUUID=XXXXXX-X"`

# **Instructions:**
1. Install Pinn Multiboot to a `USB(1)` using "Raspberry Pi Imager->Misc utility images->Pinn->Pinn" then select the correct Storage `USB(1)` and write.
2. Download and drag the `"OS"` folder only ***(Not the entire zip/Zynthian-4-pinn folder, Only the OS folder)*** to the root of a different `USB(2)` drive and **plug it in after booting Pinn**.**`(The USB should look like xX:/OS/Zynth)`**
3. During the Pinn OS installation screen where you select the OS to install, scroll to the bottom then select Zynthian (and any other OS's you want) then press install.
4. You should now be able to boot Zynthian from the `USB(1)` after Pinn is done with the setup. (it will take a few seconds for Zynthian to boot)
   
   You might see a message "controller never released inhibits" but it should still boot after about 20-30 seconds

Check below to backup "root=PARTUUID=XXXXXX or root=/dev/mmcblkXXX" before updating or making changes in zynthian.local; else booting will fail.

# **IMPORTANT! Backup Instructions for "Root=/"**
1. Inside of Pinn, head to the maintenance menu by clicking "More" in the corner `(to see the main Pinn menu; connect a keyboard while holding shift during boot)` and click on Zynthian and `"Edit Config > cmdline.txt"` located at the top and copy down the "root=PARTUUID=XXXXXX or root=/dev/mmcblkXXX". This is the partition id for Zynthian. [Reference](https://github.com/procount/pinn/blob/master/README_PINN.md#easy-config-file-editor)

2. If you updated or messed with zynthian.local and forgot to copy down the `"root=PARTUUID=XXXXXX or root=/dev/mmcblkXXX"`; in the maintenance menu click on `"Fix > File System Check > OK"`  and there will be two different "PARTUUID=XXXXXX or /dev/mmcblkXXX" `copy down the last one (you might see two which are similar so ignore those)` and `place it accordingly after the "=" in "root="` inside of the Zynthian "cmdline.txt". [Quick Guide](https://youtu.be/vIRjE890PFs)

## ****Do not use these; it's only an Output Example:****

    Checking Filesystems.....

    Checking ZynthianStable....

    /dev/mmcblk0pX1 or PARTUUID=XXXXXXX-08.....  (<----- ignore)

    xxxxxxxxxxxxx.....

    xxxxxxxxxxxxx.......

    /dev/mmcblk0pX1 or PARTUUID=XXXXXXX-08.............   (<----- ignore)

    /dev/mmcblk0pX2 or PARTUUID=XXXXXXX-09 (<-----This is the one you want to use in the cmdline.txt for Zynthian)

    ext4......


# **Zynthian.local setup:**

1. After installing and booting; connect to ethernet and configure Zynthian at [Zynthian.local](http://zynthian.local) or the Pi's local IP `(password = raspberry)` (Ex:`192.168.1.XX` find yours in router settings or a wifi ip scanning app). Wifi can be enabled in the System>Wifi section.

2. if there is **`no Display`** check the Display settings located in the Hardware>Display Section and try messing with the different options (Ex: Waveshare DSI 4.3" screen will work with the option `Pi 7 Touchscreen Display 800x480`). Also check the config.txt(available in the [Pinn menu](https://github.com/procount/pinn/blob/master/README_PINN.md#easy-config-file-editor)) from Zynthian and comment `"hdmi_safe=1" --> "#hdmi_safe=1"` (<--Only if there's no display)


# **Notice:** 
1. I'm not a developer for Zynthian or Pinn and have only converted the .img from [Zynthian](https://Zynthian.org/) into the needed files (boot.tar.xz and rootfs.tar.xz) required for Pinn.

3. If you want to create this yourself, download and flash the Zynthian image to any USB over **32GB** and follow the instructions located in this [guide](https://github.com/procount/pinn/wiki/How-to-Create-a-Multi-Boot-SD-card-out-of-2-existing-OSes-using-PINN) and ignore the "Backup Retropie" section. You can also edit the other files to accommodate the image you are converting (OS.json, xXx.png, and Marketing.tar).
