# A Kernel based emulator for the Raspberry PI Sense hat
The system is based on the i2c-stub "driver" from the Linux kernel, it has been modified
in order to pretend that the device present on the sense hat exist on its virtual bus.
For convenience the drivers used by the Raspberry Pi are also included in a slightly modified
version so they can be built without having the Raspberry Pi's kernel source tree on your machine.

## rpi-drivers
In here you will find the 3 drivers used by the Sense HAT as well as a Makefile to build them.

## i2c-stub
In here you will find the stub module as well as a Makefile to build it.

## TODOs
- [ ] figure out what is actually needed in order to emulate all of the registers.
	can we just place predefined values in the required registers and setup some
	registers to write and call it a day? Or is there actual logic involved such as:
	If register X is written to in register Y value Z should show up.

- [ ] Implement the logic that is required to convince the core driver that a chip is in fact present.
	From here on we can start splitting work up.

- [ ] Check what we require to convince the framebuffer (aka the LED Matrix) driver that the virtual hardware exists.
- [ ] Check what we require to convince the joystick driver that the virtual hardware exists.
- [ ] Implement the logic to convince the framebuffer driver that the virtual hardware exists.
- [ ] Implement the logic to convince the joystick driver that the virtual hardware exists.
- [ ] Implement a mechanism to input joystick stuff from userspace
- [ ] Implement a mechanism to read out the LED state from userspace
- [ ] Implement a program that makes use of these two mechanisms in order to provide a nice GUI or whatever to use this module
- [ ] Make the setup of all the kernel stuff as easy as possible
- [ ] Profit

