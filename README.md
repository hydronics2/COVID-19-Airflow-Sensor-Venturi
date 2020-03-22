# Easy Flow Rate Sensor

##Project Description ([from Helpful Engineering](https://www.helpfulengineering.org/))
The intent here is to create a monitoring device, based on a mass airflow meter, that can be used when splitting a ventilator into two or more patients. This will allow staff to monitor individual patients while being controlled by one device in extreme situations where the number of ventilators are not enough to handle the number of patients. The readout should be visible locally on the device and there may need to be parameters input by staff to create a safe operating range and to possibly create alarms when the system is measuring an out of range parameter.




This version of the flow rate sensor PCB has off the shelf micro-controllers for quick prototyping. Developed through

The printed circuit board (PCB) accepts multiple Arduino platforms made by Adafruit including their line of [Adafruit Feather](https://www.adafruit.com/category/777) type micro-controllers and [Adafruit ItsyBitsy](https://www.adafruit.com/category/1008) micro-controllers.   The Adafruit feathers include wifi and SAMD M0 and M4 options. All the ItsyBitsy 3V models (M0, M4, and 32u4) should work fine.

[google Doc](https://docs.google.com/document/d/14zgp7OhsyWClFdLCb04ITVAHAoAawH8Gl29P4oe5PJs/edit?usp=sharing)

### Still to do
- select the operational amplifiers and gain serving the pressure sensors
- Select alarm conditions
- Might need to add a separate power connector (⅛” barrel?)  as the USB micro connector might not be strong enough
- Verify any i2C conflicts between humidity sensor and OLED display


### General Operation
.....

### Pressure Sensors
Two pressure sensors used here. Both manufactured by [NXP MP3V5004 Series](https://www.nxp.com/docs/en/data-sheet/MP3V5004G.pdf)
- One pressure sensor measures differential pressure from an external venturi
- One pressure sensor measures gauge pressure.
Both pressure sensors are connected directly to the micro-controllers ADC inputs as well as operational amplifiers so their outputs may be amplified as needed. (A0, A1, A2, A3,A4,A5).
![foo](https://github.com/hydronics2/Easy-Flow-Sensor/blob/master/pics/analog_amplifiers.PNG)


### Micro-Controller Pinout
#### Feather ESP32 Pinout
![feather](https://github.com/hydronics2/Easy-Flow-Sensor/blob/master/pics/feather.PNG)
#### ItsyBitsy Pinout
![itsy](https://github.com/hydronics2/Easy-Flow-Sensor/blob/master/pics/itsy.PNG)


### Power
Power is delivered through the USB cable on the micro-controller. The Feather micro-controllers have a lipo charge circuit.  The main board is powered from the vBat pin of the micro-controller. The smaller Adafruit micro-controller does not have a lipo charge circuit and powers the PCB from the USB pin.
Feather lipo charge circuit
![foo](https://github.com/hydronics2/Easy-Flow-Sensor/blob/master/pics/feather_power.PNG)

![foo](https://github.com/hydronics2/Easy-Flow-Sensor/blob/master/pics/Schematic.PNG)
![foo](https://github.com/hydronics2/Easy-Flow-Sensor/blob/master/pics/board%20view.PNG)
