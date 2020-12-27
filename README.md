# wireless-printer-custom-kernel
A collection of custom linux i made to optimize a wireless printer app with CUPS

# Quick Description
0.1	: The first try, remove Input devices

0.2	: Second iter

0.3	: Third iter, far worst

0.1a	: remove Input devices and PCCard, compress in ZSTD

0.1b	: same as 0.1a, but compress in gzip

# Performance (kernel, userspace)
- linux 5.10.1 (base)	: (11.164, 7.477)
- 0.1			: (11.558,7.319)
- 0.2			: (12.577, 7.561)
- 0.3			: (14.075, 8.566)
- 0.1a			: (14.260, 9.078)

# Size
- linux 5.10.1 (base)	: 786981441
- 0.1			: 785786260
- 0.2			: 782406199
- 0.3			: 760366747
- 0.1a			: 779816546

# Modules Remove List
Ver 0.1:
- Device Drivers
	- Input device support
		- Mouse interface
		- Joystick interface
		- Mice
		- Joysticks/Gamepads
		- Tablets
		- Touchscreens
		- Miscellaneous devices

Ver 0.2:
- base 0.1
- Device Drivers
	- Input device support
		- Export input device LEDs in sysfs
		- Polled input device skeleton
		- Event debugging
		- RM*
	
Ver 0.1a:
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

Ver 0.1b:
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
