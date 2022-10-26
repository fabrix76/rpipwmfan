# Raspberry PWM fan controller 
## Introduction

![Alt text](/img/1666790543910.jpg "Raspberry rack")
I have a nice 4 bays raspberry rack, which helps me to get some sort of order on my workbench, but it cause overheating on raspberries and that make them throttling.

Here you have a really simple circuit to drive a fan in order to cap RPMs and (obviously) the noise it makes.

I have choosen to use Node-Red to control speed

## Hardware setup

I get +5v and GND from raspberry GPIO, and i'm going to use GPIO21 (pin40) to control fan speed.

### Schematics and pcb
![Alt text](/img/schematics.png)   ![Alt text](/img/pbc.png)

Please pay attention to the way the transistor is connected:
- emitter raspberry ground
- base raspberry GPIO21
- collector to fan ground 

### Bill Of Material
- 1 x 1KOhm resistor (R2)
- 1 x 2N2222A NPN transistor (Q2)
- 1 x diode
- 1 x 3 pin connector (J2)
- 1 x 2 pin connector (J1)

### Board I/O connection
J1 (Fan connector)
- Pin 1 fan +
- Pin 2 fan -

J2 (Raspberry connector)
- Pin 1 +5v 
- Pin 2 gnd
- Pin 3 raspberry GPIO12 (pin32)

### Prototype circuit board
This is how it should look like. I'm sure yours will be better than mine :)

![Alt text](/img/IMG_20221026_140357.jpg "Selfmade prototype board")

in this photo there is also a second connector, used to power the fan's led ring.

### connect and go!
Here a detail of connection on my cluster head raspberry

![Alt text](/img/IMG_20221026_141100.jpg "Wiring")

In the four cable (purple, black, white and gray) are used for a SPI device, not of interest for this project.

Now you can import in Node-Red the flow.json, containing application logic and dashboard to setup speed varying dutycycle.
Required palette:
- node-red-node-pi-gpio
- node-red-dashboard

Note: to change speed you need to change frequency on GPIO so varying frequency value on GPIO you can increase or decrease fan rotation. For value less than 20 (more or less) your fan doesn't rotate well, but it shoud tick sometime, it is normal.


![Alt text](/img/nodered.png "Node Red fan commands")


If you like, you can command fan speed from console, without NR, setting PWM and frequency on GPIO12 o whatever you will use.
Enjoy!