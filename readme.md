# Raspberry PWM fan controller 
## Introduction

![Alt text](/img/1666790543910.jpg "Raspberry rack")
I have a nice 4 raspberry rack, which help me to get a little bit of order in my study, but it introduce overheating on raspberies so them get throttled.

Here you are a really simple circuit to drive a fan, in order to cap rpm and obviously the noise.

I have decided to use Node-Red to control speed

Here you are the schematics, pcb and the BOM
![Alt text](/img/schematics.png) ![Alt text](/img/pbc.png)

1 x 1KOhm resistor (R2)
1 x 2N2222A NPN transistor (Q2)
1 x diode
1 x 3 pin connector (J2)
1 x 2 pin connector (J1)

J1 (Fan connector)
Pin 1 fan +
Pin 2 fan -

J2 (Raspberry connector)
Pin 1 +5v 
Pin 2 gnd
Pin 3 raspberry GPIO21 (pin40)

Here you are my prototype circuit board

![Alt text](/img/IMG_20221026_140357.jpg)

in this photo there is also a second connector, used to power the fan's led ring.

Now you can import in Node-Red the flow.json and varying frequency on GPIO you can increase or decrease fan rotation.
If you like, you can command fan speed from console, without NR, setting PWM and frequency on GPIO21 o whatever you will use.