# Catalina
<<<<<<< HEAD
=======
### The “EFI” folder containing CLOVER and BOOT folder for USB Installer and for the system EFI too. 

- After you created an USB Installer: Mount your USB’s EFI:
	- On Mac: use Terminal or an EFI Mounter (for ex.: EFI MountainShow.app) and copy the EFI folder to the EFI partition
	(If there is an EFI folder in EFI partition then you just cover it)
	- On Windows: use MiniTool Partition Wizard to mount your USB’s EFI:
	Select your USB drive, right click, then “Change Letter”, Apply and OK
	-You can’t open EFI folder with default Windows Explorer, you’ll need Explorer++ or Total Commander (run these in Admin mode)
	(If there is an EFI folder in EFI partition then you just cover it)

- After you installed the system, mount EFI with an EFI mounter and copy & paste the EFI folder to the EFI partition.
	- If you experiencing freezes during boot, boot with “config_debug.plist”

### “postinstall” folder contains kexts you need to install manually.
- “FakePCIID.kext”, “FakePCIID_Intel_HDMI_Audio.kext” and “ACPIBatteryManager.kext” must be installed to “Library/Extensions” (“/L/E”)

- Not promise it will work.
	- You could try the touchpad driver for gestures in the “optional_touchpad_gestures” folder (install to “/L/E”), but delete “VoodoPS2Controller.kext” from everywhere, that will broke your mouse. If that happens use an external mouse (or do it from single user mode “-s”), delete, rebuild caches.

- Headphone Combo Jack fix:
	- To fix your garbage sound output on combo jack first install “CodecCommander.kext” (in “ALCPlugFix” folder) to “L/E”, then mount the system drive in rw: 
		- Before start on macOS Catalina your system drive is read-only, so you must mount in read-write:
			- sudo mount -uw
			- sudo killall Finder
		- Finally, install ALCPlugFix by double clicking “english_install.command”.
		- Wait while the script copies the required files and rebuild kextcache (related files are in the `fix` folder). It may take a few seconds.
		- When it's done, you'll see `Press any key to Exit`. Type any key and press Enter, then restart your computer. The installation now completes.

	- ATTENTION: You may have to replug the headphone after every boot to let headphone work.

- After you copied every kexts repair permissions && rebuild kextcache, then you done.
>>>>>>> c90ac308ccbfec8c053cb3620b89c0428a0eb60b
