# wireless-printer-custom-kernel
A collection of custom linux i made to optimize a wireless printer app with CUPS

# Performance (kernel, userspace)
- linux 5.10.1 (base)	: (11.164, 7.477)
- 0.1			: (11.558,7.319)

# Size
- linux 5.10.1 (base)	: 786981441
- 0.1			: 785786260

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
