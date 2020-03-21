# Easy Flow Rate Sensor

This version of the flow rate sensor has off the shelf micro-controllers for quick prototyping.
[Helpful Engineering Slack Channel](helpfulengineering.slack.com)

The printed circuit board (PCB) accepts multiple Arduino platforms made by Adafruit including their line of [Adafruit Feather](https://www.adafruit.com/category/777) type micro-controllers and [Adafruit ItsyBitsy](https://www.adafruit.com/category/1008) micro-controllers.   The Adafruit feathers include wifi and SAMD M0 and M4 options. All the ItsyBitsy 3V models (M0, M4, and 32u4) should work fine.

[google Doc](https://docs.google.com/document/d/14zgp7OhsyWClFdLCb04ITVAHAoAawH8Gl29P4oe5PJs/edit?usp=sharing)

### Still to do
- select the operational amplifiers
- add buttons for user input
  - alarm selection
- add piezo buzzer for audio alarm

### General Operation
.....

### Pressure Sensors
Two pressure sensors used here. Both manufactured by [NXP MP3V5004 Series](https://www.nxp.com/docs/en/data-sheet/MP3V5004G.pdf)
- One pressure sensor measures differential pressure from an external venturi
- One pressure sensor measures relative pressure.
Both pressure sensors are connected to operational amplifiers so their outputs maybe amplified into the micro-controller's ADC.
![foo](https://github.com/hydronics2/Easy-Flow_Sensor/blob/master/pics/analog_amplfier.PNG)


### Micro-Controller Pinout
#### Feather ESP32 Pinout
![feather](https://github.com/hydronics2/Easy-Flow_Sensor/blob/master/pics/feather.PNG)
#### ItsyBitsy Pinout
![itsy](https://github.com/hydronics2/Easy-Flow_Sensor/blob/master/pics/itsy.PNG)


### Power
The PCB design uses the USB power pin from the micro-controller. The Feather micro-controllers have a lipo charge circuit.  The main board then get's power from the vBat pin of the micro-controller.
Feather lipo charge circuit
![foo](https://github.com/hydronics2/Easy-Flow_Sensor/blob/master/pics/feather_power.PNG)
