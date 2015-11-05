# Bluegiga

This repository contains firmware for the Bluegiga BLE121LR bluetooth chip required for datalink operation with PaparazziUAS (https://github.com/paparazzi/paparazzi).

File Description
----------------
config.xml - Application configuration file

gatt.xml - Contains the GATT database. The bluetooth smart profile which defines the services and characteristics

hardware.xml - Hardware configuration file

datalink.bgs - BGScript application source code for the datalink

datalink.bgproj - Project file which defined which files make up the datalink project

Required Software and Hardware
------------------------------
Bluegiga BLE Update application with a Texas Instruments CC Debugger are required to flash the Bluegiga modules. More information on the the software and hardware can be found at: https://bluegiga.zendesk.com/entries/22442106—HOW-TO-Using-the-BLE-Update-utility-to-program-a-BLE-module.

Notes
-----

TX power is a signed 8-bit value, and is not changed automatically when using "hardware_set_txpower(<power>)". This may be anywhere from -23 to +3 based on your settings. Negative values may be converted to two's complement form by adding 256, so for example -23 dBm would be 233 or $E9.

Manufacturer data fields should contain the Company Identifier Code in order to stay within BT 4.0 spec. You should also ideally obtain an an official Company Identifier Code, but 0xFFFF is suitable for development. (this is why the minimum ad field length for this is 3, so the CIC fits) More bytes are possible here, but not necessary for this demo. Compare with automatically generated ad packets from other demo projects to see what else you might put here, or read the relevant portions of the Bluetooth 4.0 Core Spec document
for greater detail.
