# Project introduction
A breakout board for the Apple Newton MessagePad MP2x00 Interconnect Port. Use 
a cut-in-half Molex 0714390964 connector and bend the legs to solder it to the 
front of the board. The height and distance fit with a standard breadboard, and 
connect to a Newton device at the same time. As it is here, the design is 
untested. Please use with care.

![pcb_3d.jpg](/pcb_3d.jpg)

# Project function
This is just a breakout board. It has no active component. I designed this 
so I can develop a Newton dongle with USB-C.

![breakout_1024.jpg](/breakout_1024.jpg)

# Update: on the way to build a dongle

I am planning a dongle that connects to USB-C and has a MicroSD Card on board. The
RP2040 processor comes on a Seeed Studio Xiao PCB and connectes to an Adafruit MicroSD 
carrier. To hook all that to the Newton, we need an additional board that converts
the serial signal to RS422, and that handles power from USB-C, and to and from the Newton.

Here is my first mini series PCB based on an earlier prototype:

![IMG_5900.jpg](/IMG_5900.jpg)

# Assembling processes
Use a cut-in-half Molex 0714390964 connector and bend the legs

# The Newton Interconnect Port

The Newton Interconnect Port contains the following groups of pins:
- 7-pin AppleTalk/Local Talk interface with handshaking signals, using the 
Serial Communications Controller Channel 0.
- Serial Communications Controller Channel 3 with full control signals, ring 
indicator, and enable
- Power Adapter pins that power the MessagePad and recharge the batteries
- Auxiliary audio input
- Line-level auxiliary audio output
- An auxiliary +5V power source that can be turned on or off under software 
control
- A control input that allows an external peripheral to wake the MessagePad 
system if it is in the Sleep state

The Newton Interconnect Port provides two serial channels — 0 and 3. Channel
0 has a LTC1323 line driver connected to the Newton Interconnect Port, and 
can be used as either a serial channel or as a differential AppleTalk 
connection. Channel 3 can also be used with a serial port, but has no line 
driver, so developers will probably need to provide one.

The Newton Interconnect Port has both Audio Out and Audio In capabilities. 
These can be used to connect to auxiliary audio devices. AudioOut is a 
single-ended signal at line level, referenced from AGND . AudioOut is capable 
of driving impedance loads down to 1KΩ. 
