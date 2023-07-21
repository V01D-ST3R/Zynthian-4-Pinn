# Zynthian-4-Pinn
This is a pre-made Zynthian image compatible with Pinn multiboot running on a USB

Zythian Image from https://zynthian.org

If you want to create this yourself, follow the instructions located at https://github.com/procount/pinn/wiki/How-to-Create-a-Multi-Boot-SD-card-out-of-2-existing-OSes-using-PINN and ignore the retropie part.

`USB(1)` (Primary USB that will contain Pinn and any other OS)
  
`USB(2)` (Spare USB with 8GB min to copy the OS folder for Pinn to read the Custom OS from)

**Instructions:**
1. Install Pinn Multiboot to a `USB(1)` (with the recommended size of `32GB`) using "Raspberry Pi Imager/Misc utility images/Pinn/Pinn" then select the correct Storage(USB) and write.
2. Download and put the `"OS"` folder at the root of a different `USB(2)` drive `(8GB minimum)` and plug it in after booting Pinn.
3. During the Pinn OS installation screen where you select the OS to install, scroll to the bottom then select Zynthian (and any other OS you want)then install.
4. You should now be able to boot Zynthian from a USB after Pinn is done with the setup

**Notice:** I'm not sure if this will work for a Micro-SD but don't see why it wouldn't.

**Zynthian.local setup:**

1. After installing you can Configure Zynthian at `zynthian.local` or the Pi's local IP `(password = raspberry)` (Ex:`192.168.1.XX` find yours in router settings or a wifi ip scanning app). `Use an ethernet cable to setup` the wifi if needed in the System/Wifi section.
2. if there is no Display check the Display settings located in the Hardware/Display Section and try with `"Generic Hdmi Display"`.
