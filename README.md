# ESP8266 12 Volt LED Driver

## Inspiration
Based upon the good work of [tjclement/esp-dimmer-hardware](https://github.com/tjclement/esp-dimmer-hardware).
TJCLEMENT's v2 board was good, but I had trouble getting recovering my ESP when an over-the-air firmware update failed.

## Schematic
My schematic has some modifications:
  1. Added an FTDI programming port
  1. Made the resistors on the outputs pull-down rather than in-line to the MOSFET
  1. Added an extra IO connector with GND/3.3V to attach a potentiometer for input.

## PCB
The PCB is bigger, primarily as I have the space in my application but also (slightly) because of the additional ports.
I ordered the PCB from JLCPCB.

## BOM:
Most parts are sourced from the sister company of JLCPCB, called LCSC.
The power regulation module can be found on AliExpress with the search "MINI-360"

|Name                |Quantity|Manufacturer Part  |Manufacturer       |Supplier    |Supplier Part|
|--------------------|--------|-------------------|-------------------|------------|-------------|
|ESP-12F(ESP8266MOD) |1       |ESP-12F(ESP8266MOD)|Ai-Thinker         |LCSC        |C82891       |
|0805 10K Resitors   |8       |080500F1003T5E     |UniOhm             |LCSC        |C149504      |
|0808 100nF Cap      |1       |C0805X104K101T     |HEC                |LCSC        |C105951      |
|FDS8896             |3       |FDS8896            |ON Semicon         |LCSC        |C241820      |
|K2-1107ST-A4SW-06   |2       |K2-1107ST-A4SW-06  |SMD Switches       |LCSC        |C118141      |
|MP2307-MINI-360     |1       |                   |Search "MINI-360"  |AliExpress  |             |

I haven't included the IO connectors. All are 2.54 pitch and header strips or screw connectors can be used.

## Assembly
When assembling, solder the power regulation module first and set it to 3.3V output with the 12V input applied.
This ensures you wont blow up the ESP.

## Firmware
The firmware I use makes it play with OpenHab2 over MQTT.
