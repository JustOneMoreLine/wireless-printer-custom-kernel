# wireless-printer-custom-kernel
A collection of custom linux i made to optimize a wireless printer app with CUPS

# Performance (kernel, userspace)
- linux 5.10.1 (base)	: (11.164, 7.477)
- 0.1			: (11.558,7.319)
- 0.2			: (12.577, 7.561)

# Size
- linux 5.10.1 (base)	: 786981441
- 0.1			: 785786260
- 0.2			: 782406199

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
