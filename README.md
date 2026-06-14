<h1 align="center">
    ESPGarageLink
</h1>
<h4 align="center">
    Inexpensive Garage Door Opener Link for Home Assistant
</h4>

![image](/assets/zine.png)

<h2 align="center">
About This Project
</h2>
Throughout my life, I would often forget if I closed garage door was closed before heading out of the house. I would have to turn around for the slight chance that it was left open. I built this project to counter this. It uses ESPHome to easily integrate with Home Assistant.

<h2 align="center">
BOM
</h2>

|Part Number|Part Name         |Quantity|Sourcing Link                                       |Cost  |Notes                                             |
|-----------|------------------|--------|----------------------------------------------------|------|--------------------------------------------------|
|1          |ESP32             |1       |https://www.aliexpress.us/item/3256806060462387.html|$5.02 |                                                  |
|2          |Garage Door Remote|1       |https://a.co/d/0b3jvMXJ                             |$6.99 |has to be compatible with your garage opener model|
|3          |22awg dual wire   |100ft   |https://a.co/d/04LgN8tN                             |$15.99|                                                  |
|4          |Reed Switch       |1       |https://a.co/d/087Lrm4S                             |$9.88 |                                                  |
|5          |M3x10 BHCS        |4       |https://www.aliexpress.us/item/2251832624537980.html|$2.02 |                                                  |
|6          |1K Resistor       |1       |https://www.aliexpress.us/item/3256802303553096.html|$0.90 |                                                  |
|7          |2N2222A Transistor|1       |https://www.aliexpress.us/item/3256808419495041.html|$1.91 |                                                  |


<h2 align="center">
Assembly
</h2>

|Case Assembly                        |Wiring Diagram                   |
|-------------------------------------|---------------------------------|
|![image](/assets/exploded_view_1.png)|![image](/assets/schematic_1.png)|

1. Solder the wires to the correct spots on the Garage Remote PCB
2. Place the ESP32 and PCB inside the case.
4. Measure out the length of wire you need to connect the sensor to the ESP32 and cut it. (**MAKE SURE TO ADD SOME EXTRA LENGTH**)
5. String it through the circular hole in the case and connect it to the ESP32
6. Solder the rest of the connections
7. Screw the top case on
8. Flash your ESP32 with ESPHome
9. Link the ESP32 to ESPHome and upload the code to it. 
10. Install the parts in your garage

Source files can be found [here](https://cad.onshape.com/documents/4649b205c89024a5f1492af2/w/5978872a114fc81fb7337ada/e/29e5e7a7f49cdcf4b48956bb?renderMode=0&uiState=6a2f0bc27379316f88a87890)

<h2 align="center">
Credits
</h2>

Thank you to [Hack Club](https://hackclub.com/) for supporting my projects! They're truly an amazing organization.