# Raspberry PWM fan controller 
## Introduction

![Alt text](/img/1666790543910.jpg "Raspberry rack")
I have a nice 4 raspberry rack, which help me to get a little bit of order in my study, but it introduce overheating on raspberies so them get throttled.

Here you are a really simple circuit to drive a fan, in order to cap rpm and obviously the noise.

I decide to use Node-Red to control speed

Here you are the schematics and the BOM
![Alt text](/img/schema.png)

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

Varying frequency on GPIO you can increase or decrease fan rotation.