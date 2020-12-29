# wireless-printer-custom-kernel
A collection of custom linux i made to optimize a wireless printer app with CUPS

# Quick Description
wirepri-0.1	: The first try, remove Input devices

wirepri-0.2	: Second iter

wirepri-0.3	: Third iter, far worst

wirepri-0.1a	: remove Input devices and PCCard, compress in ZSTD

wirepri-0.1b	: same as 0.1a, but compress in gzip

popcorn-0.1	: a fresh start, base from linux-4.15.1



# Performance (kernel, userspace)
- linux 5.10.1 (base)	: (11.164, 7.477)
- wirepri-0.1		: (11.558,7.319)
- wirepri-0.2		: (12.577, 7.561)
- wirepri-0.3		: (14.075, 8.566)
- wirepri-0.1a		: (14.260, 9.078)
- popcorn-0.1		: (4.704, 8.351)

# Size
- linux 5.10.1 (base)	: 786981441
- wirepri-0.1		: 785786260
- wirepri-0.2		: 782406199
- wirepri-0.3		: 760366747
- wirepri-0.1a		: 779816546
- popcorn-0.1		: 56485062


# Modules Remove List
Wirepri-0.1:
- Device Drivers
	- Input device support
		- Mouse interface
		- Joystick interface
		- Mice
		- Joysticks/Gamepads
		- Tablets
		- Touchscreens
		- Miscellaneous devices

Wirepri-0.2:
- base 0.1
- Device Drivers
	- Input device support
		- Export input device LEDs in sysfs
		- Polled input device skeleton
		- Event debugging
		- RM*
	
Wirepri-0.1a:
- Device Drivers
	- Input device support
		- Mice
		- Joysticks
		- Tablets
		- Touchscreens
		- Miscellaneous devices
		- *all <> modules set too M*
	- PCCard
- General Setup
	- Configure standard kernel features (expert users)
		- BUG() support
		- Enable PC-Speaker support
	- Kernel compression mode -> set to ZSTD

Wirepri-0.1b:
- Device Drivers
	- Input device support
		- Mice
		- Joysticks
		- Tablets
		- Touchscreens
		- Miscellaneous devices
		- *all <> modules set too M*
	- PCCard
- General Setup
	- Configure standard kernel features (expert users)
		- BUG() support
		- Enable PC-Speaker support

Popcorn-0.1:
- Kernel debugging/?
- General Setup
	- Kernel .config support
	- Configure standarad kernel features (expert users)
		- Include all symbols in kallsyms
- Bus oprtions
	- PCCard (PCMCIA/CardBus
- Device Drivers
	- ATA/ATAPI/MFM/RLL support
	- Multiple devices driver support (RAID and LVM)
	- Input device support
		- Mice
		- Joystick
		- Tablets
		- Touchscreens
		- Miscellaneous devices
	
	
