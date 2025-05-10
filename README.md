# RD15HVF1 Amplifier for 280-320 mhz

This repo consists of a board that uses the RD15HVF1 amplifier.  
It's tuned to the uplink satcom frequencies but it can be used for other purposes aswell.  

<img src="./img/kicad_3d.png" alt="kicad" width="400"/>
<img src="./img/circuit.png" alt="kicad" width="400"/>

------

## Important notes:

- Do not put more than 1-2W of input RF power. The max power output of this PA is 15W
- You will need a tx/rx swith if you want to recieve when using this amplifier and also a lowpass filter to avoid it's harmonics!
- The recomended vias voltage is 2.7v. **Before soldering the amplifier adjust the potentiometer!**

<img src="./img/bias_voltage.png" alt="vias voltage" width="400"/>

- There are **a lot** of fake RD15HVF1 chips on aliexpress! It's better to buy a used RD15HVF1 with the legs cut (as in [here](aliexpress.com/item/1005008441262750.html) than paying more for a "new" chip that will never work.

## Features:

- With 1,5W at 300mhz it gives an output of 15W
- The frequency with maximum power is at 305mhz
- The input SWR is well tunned

<img src="./img/swr.png" alt="swr" width="200"/>

## Aditional information:

- Be sure to use a proper heatsink. Ideally it should be 100x50mm
- Apply thermal paste to the `RD15HVF1` amplifier
- The wound coils act as RF chokes. They should have between 150-300nH so wound a 0.7mm enameled wire around a 5mm drill bit for 6 turns

<img src="./img/heatsink.png" alt="heatsink" width="200"/>

- The zener diode acts as a voltage limiter. Buy one with a breakdown voltage of around 4v so even if the potentiometer is open it will not push to the bias the 9v of the voltage regulator

------

## Ordering the PCB:

Download the [GERBER-Amplifier](./GERBER-Amplifier.zip) file from this repo and order it a jlcpcb with the default options. The only option I've changed is to remove the manufacture code mark

<img src="./img/jlcpcb.png" alt="kicad" width="400"/>

------

## Prototype image:

<img src="./img/prototype.png" alt="prototype" width="400"/>

------

## Output power:

<img src="./img/pwr.png" alt="output power" width="300"/>

------

## Prototype image:

<img src="./img/prototype.png" alt="prototype" width="400"/>

------

## BOM:

```
- PCB that you can order ar jlcpcb or somewhere else.
- RD15HVF1 (https://aliexpress.com/item/1005008441262750.html)
- 0805 560p Capacitor
- 0805 27p Capacitor
- 0805 62p Capacitor
- 0805 36p Capacitor
- 0805 10p Capacitor
- 0805 100p Capacitor
- 2x 1812 100n Capacitor
- 2x 1812 1u Capacitor
- 0805 10 ohm resistor
- 0805 1k ohm resistor
- L7809  9v voltage regulator
- 33uF SMD electrolitic cap 25v 5X5.4mm (https://aliexpress.com/item/1005005427427871.html)
- 3314G 10k potentiometer (https://aliexpress.com/item/1005003118598266.html)
- 100x50x50mm heatsink (https://aliexpress.com/item/1005004879389236.html)
- 0.7mm enameled wire for making air wound coils
- 2x SMA connectors
- (Optional) LL41 SMD 3v9 or 4v7 Zener Diode (Voltage limiter)
```