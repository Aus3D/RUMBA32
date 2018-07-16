# RUMBA+

RUMBA+ is an updated version of the RUMBA 3D Printer control board, originally developed by [RepRapDiscount](http://www.reprapdiscount.com/). 

The RUMBA+ update is designed to address several shortcomings with the original design, and improve on the otherwise solid framework it presents. More information on RUMBA is available on the RepRapWiki page [here](http://reprap.org/wiki/RUMBA).

RUMBA+ boards are for sale in the [Aus3D shop](http://aus3d.com.au/rumba-plus). Additional documentation is available on the [Aus3D wiki](http://wiki.aus3d.com.au/RUMBA_Plus).

In keeping with the original RUMBA design, RUMBA+ is fully open source.

## Image
![RUMBA+ PCB Preview](https://raw.githubusercontent.com/Aus3D/RUMBA-Plus/master/Images/boardPhoto.jpg "RUMBA+ PCB Preview")
![RUMBA+ Pinout](https://raw.githubusercontent.com/Aus3D/RUMBA-Plus/master/Images/pinOut.png "RUMBA+ Pinout")
## Changes From Original RUMBA
### Input Voltage Compatibility
While the original RUMBA board claims compatibility with power supplies ranging from 12-35V, it uses PTC resettable fuses that are rated for 16V maximum. This means that the board requires modification to be used at voltages above this - though some manufacturers or suppliers may have modified the fuses or shipped boards without them to suit higher voltages.

The RUMBA+ upgrade replaces the PTC fuses with replaceable automotive blade fuses, which are suitable for operating at higher voltages.

### Improved MOSFETs
While the MOSFETs used to drive outputs in the original RUMBA design were sufficient and usually up to the tasks required of them, they did not perform as well as is desirable under heavy loads.
This is because they are not true logic-level MOSFETs, and do not switch 'fully' on when being driven by the 5V microcontroller - i.e. they operate in the linear region, not reaching saturation mode. This results in inefficient operation and significant self-heating.

The MOSFETs have been replaced with newer MOSFETs that are logic-level compatible, and that will switch on at a much lower voltage. Additionally, these new MOSFETs also have a much lower on-state resistance, and so will be more efficient and generate less heat while in use.

Further, flyback diodes have been added in order to protect the MOSFETs from back-EMF during switching loads with an inductive component (such as PCB heated beds).

### LCD Smart Display Wiring
Labelling on expansion ports 1 and 2 has been updated to match the labelling common to most compatible LCD displays, as it was previously reversed from the norm.

### Additional I2C Headers
In order to be able to host the new Aus3D Magnetic Encoder modules, four I2C headers have been added to the board. This allows easy connection of up to four encoder modules, and removes the need for an external splitter cable or adaptor board.

### Other Housekeeping
* Routing on several decoupling capacitors has been changed to better reflect best practices 
* Board size changed from 135x75mm to 140x75mm to fit changes / additional components
* Thermistor connectors changed from 1x10 to 2x5 header to be more compact.
* Labels on thermistors and endstops adjusted.
* Schematic updated for readability, full bill-of-materials made available

## License
RUMBA+ is fully open source, and may be freely modified or changed by anyone, provided they maintain the license it is released under. The design is free to use for any purpose, including commercial uses. RUMBA+ maintains the GPLv2 license of the original RUMBA board. For more information on this license, please see the included license file.

## Design Images
![RUMBA+ Schematic](https://raw.githubusercontent.com/Aus3D/RUMBA-Plus/master/Schematic.png "RUMBA+ Schematic")
