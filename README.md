# Zynthian-4-Pinn
This is a pre-made Zynthian image compatible with Pinn multiboot running on a USB for the Raspberry Pi 4

I'm not sure if this will work for the Micro-SD slot but don't see why it wouldn't.

I'm currently booting Pinn Multiboot with a 256GB Samsung Micro-SD with USB adapter "New PRO Plus + USB Reader"

*Check back the README.md for any future changes.*

# **Link to the Zynthian OS folder:**

Download the file from any provider below

Host 1. [Sync](https://ln5.sync.com/dl/2d24fb220/issh3ezf-pdct6b8s-iderb8v6-ud6zyr9z)

Host 2. [Mega](https://mega.nz/file/RN9kUDLK#Z5Z_Jp6yEz1c-FcOvyUdl7DodRu4broVGdOD3zJ_7Qc)

Host 3. [Google Drive](https://drive.google.com/file/d/1a4XwmpCFEhuqFlBqsRf_ayjaNmcC8SSQ/view?usp=sharing)

# **Note:**

1. `USB(1)` Primary USB that will contain Pinn and any other OS `(I recommend 32GB or more if installing 3+ different Operating Systems)`
2. `USB(2)` Different USB with `8GB min` which will contain the OS folder for Pinn to see/detect Zynthian.
3. Recommend to use RPI Imager to flash the bootloader with "USB Boot" (Unless using a MicroSd card)
4. It looks like you can ***`allocate more space to Zynthian`*** by messing with **OS/Zynth/***partitions.json*****                          
***`"edit the second section under; ext4/rootfs"`*** --> "partition_size_nominal": `(default 14108)` <-- set to whatever size you want (this would be 14GB). <sub> ***(Do not mess with "uncompressed_tarball_size: 11608" as this is the size required for the Zynthian image)***<sub> 

# **Instructions:**
1. Install Pinn Multiboot to a `USB(1)` using "Raspberry Pi Imager->Misc utility images->Pinn->Pinn" then select the correct Storage `USB(1)` and write.
2. Download and drag the `"OS"` folder only ***(Not the entire zip/Zynthian-4-pinn folder, Only the OS folder)*** to the root of a different `USB(2)` drive and **plug it in after booting Pinn**.**`(The USB should look like xX:/OS/Zynth)`**
3. During the Pinn OS installation screen where you select the OS to install, scroll to the bottom then select Zynthian (and any other OS you want) then press install.
4. You should now be able to boot Zynthian from the `USB(1)` after Pinn is done with the setup. (it will take a few seconds for Zynthian to boot)

Check below to backup cmdline.txt incase booting fails before updating.

# **Info**
Take a backup of the cmdline.txt (picture or type it somewhere) check the [Maintenance Menu](https://github.com/procount/pinn/blob/master/README_PINN.md#easy-config-file-editor) (the menu should show up automatically if a keyboard is connected on boot)

If booting fails after an update check the Pinn readme_pinn [How to Fix an OS](https://github.com/procount/pinn/blob/master/README_PINN.md#how-to-fix-an-os) or the section [re-run-partition](https://github.com/procount/pinn/blob/master/README_PINN.md#re-run-partition_setupsh) for fixing.

***`If you want to only else ignore;`*** You can manually backup the **`cmdline.txt`** located in the **`boot partition`** for restoring if booting fails.`(If you selected many different OS systems during Pinn setup; look through all the mounted partitions until you locate the file "zynthianos-wpa-supplicant.txt" and backup the cmdline.txt anywhere else)` There is also another cmdline.txt located on the Rootfs(0-x) partition located at **/home/pi/zynthian-sys/boot/cmdline.txt** make sure to note down the directory and not mix it with the other cmdline.txt from the main boot partition. (not sure if this cmdline.txt is important but still worth backing up)

# **Zynthian.local setup:**

1. After installing and booting; connect to ethernet and configure Zynthian at [Zynthian.local](http://zynthian.local) or the Pi's local IP `(password = raspberry)` (Ex:`192.168.1.XX` find yours in router settings or a wifi ip scanning app). Wifi can be enabled in the System>Wifi section.
2. if there is **`no Display`** check the Display settings located in the Hardware>Display Section and try messing with the selections (Waveshare DSI 4.3" screen will work with the option `Pi 7 Touchscreen Display 800x480`).


# **Notice:** 
1. I'm not a developer for Zynthian and have only converted the .img from https://Zynthian.org/ into the needed files (boot.tar.xz and rootfs.tar.xz) required for Pinn.

3. If you want to create this yourself, download and flash the Zynthian image to any USB over **32GB** and follow the instructions located at https://github.com/procount/pinn/wiki/How-to-Create-a-Multi-Boot-SD-card-out-of-2-existing-OSes-using-PINN and ignore the "Backup Retropie" section. You can also edit the other files to accommodate for the image you are converting (OS.json, xXx.png, and Marketing.tar).
