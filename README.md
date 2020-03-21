# Easy Flow Rate Sensor

This version of the flow rate sensor has off the shelf micro-controllers for quick prototyping.
[Helpful Engineering Slack Channel](https://hackaday.io/project/170446-helpful-engineeringopen-source-mass-airflow-meter)

The printed circuit board (PCB) accepts multiple Arduino platforms made by Adafruit including their line of [Adafruit Feather](https://www.adafruit.com/category/777) type micro-controllers and [Adafruit ItsyBitsy](https://www.adafruit.com/category/1008) micro-controllers.   The Adafruit feathers include wifi and SAMD M0 and M4 options. All the ItsyBitsy 3V models (M0, M4, and 32u4) should work fine.

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
![feather](https://github.com/hydronics2/2019-easy-bee-counter/blob/master/pics/feather_pinout3.PNG)
#### ItsyBitsy Pinout
![itsy](https://github.com/hydronics2/2019-easy-bee-counter/blob/master/pics/itsy_pinout2.PNG)
### Shift-in registers
There are 6 shift-in registers. Here's a great description for how to connect and program [shift registers](http://www.gammon.com.au/forum/?id=11979).  The micro-controller's SPI pins read the shift registers. All six shift registers are read at the same time. The sensors are normally pulled low and show 3.3V or HIGH when a transistor is triggered and a bee is present.

### Power
The PCB design uses the USB power pin from the micro-controller. The Feather micro-controllers have a lipo charge circuit.  The main board then get's power from the vBat pin of the micro-controller.
Feather lipo charge circuit
![foo](https://github.com/hydronics2/Easy-Flow_Sensor/blob/master/pics/feather_power.PNG)


### Bill of Materials
#### uController
The code was tested with the feather esp32 Huzzah and itsyBitsy M0 but will work with all these boards.
- feather Huzzah from [mouser](https://www.mouser.com/ProductDetail/485-3591)
- feather esp8266 from [mouser](https://www.mouser.com/ProductDetail/485-2821)
- feather LoRa 900mhz from [mouser](https://www.mouser.com/ProductDetail/485-3178)
- ItsyBitsy M0 from [mouser](https://www.mouser.com/ProductDetail/485-3727)
- ItsyBitsy M4 from [mouser](https://www.mouser.com/ProductDetail/485-3800)
#### PCB
[JLCPCB](https://jlcpcb.com/quote#/) ~$16-25 with shipping. Order the PCBs Black. See [these instructions](https://github.com/hydronics2/2019-easy-bee-counter/tree/master/instructions/ordering_instructions) for ordering.
#### Parts and Pieces from [mouser](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=054286973a)
See alternative pricing below for cheaper options specifically for the reflectance sensors.
- [qre1113 Reflective Sensors](https://www.mouser.com/ProductDetail/512-QRE1113f) qty(48)
- [6 pin female headers](https://www.mouser.com/ProductDetail/437-8018700610001101) 7mm high, 0.1" spacing, qty(~36)
- [22ohm resistors](https://www.mouser.com/ProductDetail/Xicon/266-22-RC?qs=sGAEpiMZZMvrmc6UYKmaNXFefT4dxyTCwtpTxTI0yoo%3D), bussed, qty(4)
SIP Packaged, bussed
- [100k ohm resistors](https://www.mouser.com/ProductDetail/IRC-TT-Electronics/L091S104LF?qs=sGAEpiMZZMvrmc6UYKmaNdnTrsZX%2FuSiyGduauH5Qpc%3D) bussed, qty(6)
SIP-9, 8 resistors, 9 pins
- Shift registers, qty(6)
[74HC165](https://www.mouser.com/ProductDetail/595-CD74HC165E)
- [3.3V Regulator](https://www.mouser.com/ProductDetail/Microchip-Technology/MCP1826S-3302E-AB?qs=sGAEpiMZZMsGz1a6aV8DcJ7KfjtCj7Xd5CqQpyOghgk%3D), (input, ground, output - IGO, pinout), qty(1)
- [screw terminals](https://www.mouser.com/ProductDetail/490-TB006-508-02BE) Two pin, 0.1", qty(3)
- [0.1 uF Ceramic Capacitor](https://www.mouser.com/ProductDetail/594-K104K15X7RF53H5), through hole, qty(6)
- [1 uF Ceramic Capacitor](https://www.mouser.com/ProductDetail/594-K105Z20Y5VF5TL2), through hole, qty(1)
- [560uF, 6.3V Capacitor](https://www.mouser.com/ProductDetail/661-APSC6R3L561MH08S)
low esr, 3.5mm lead spacing, 8mm diameter
- N-Channel Mosfet [FQP30N06](https://www.mouser.com/ProductDetail/512-FQP30N06L), qty(2)

#### Alternative pricing from Chinese distributor LCSC
Someone pointed out some alternative pricing that can really bring the cost down.
- [ITR8307 Reflectance Sensors](https://lcsc.com/product-detail/Photo-Interrupter_Everlight-Elec-ITR8307_C63451.html) ~$0.13/each @ qty(48) (same as QRE1113)
- [6 pin female headers](https://lcsc.com/product-detail/Pin-Header-Female-Header_BOOMELE-Boom-Precision-Elec-C40877_C40877.html) 8.5mm high. ~$0.05/each @ qty(36+)
- [22 ohm SIP](https://lcsc.com/product-detail/Resistor-Networks-Arrays_FH-Guangdong-Fenghua-Advanced-Tech-A09-220JP_C9105.html) 8 resistor, 9 pin, it will fit. $0.44 for qty(4)
- [100k SIP Resistors](https://lcsc.com/product-detail/Resistor-Networks-Arrays_FH-Guangdong-Fenghua-Advanced-Tech-A09-104JP_C9108.html) 8 resistor, 9pin, it will fit. $0.44 for qty(6)
