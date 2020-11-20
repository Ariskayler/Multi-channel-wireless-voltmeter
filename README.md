# Multi-channel-wireless-voltmeter
A multi-channel wireless voltmeter display using ATTINY402, NRF24L01+ and 128 x 32 I2C OLED.
The transmitter is optimised for low power and will run from a battery for weeks or months depending on useage, sample frequency and of course battery capacity.
Range is a few meters to 100m depending on how well the radio module is isolated from the controller, and the power setting.
Developed on Auduino

## Overview
The display receives voltage data from up to 4 transmitters and shows them on a 128x32 OLED display.
Features:
* 0-20V range, can be configured by resistor selection.
  * Positive voltage only. Over voltage and undervoltage (negative) indication.
  * 1Mohm input impedance, can be configured by resistor selection.
  * 

* Item 2
  * Item 2a
  * Item 2b

A Mode button rotates around display modes:
1. Summary display (up to 4 channels): Row 1: '1 vv.vv*?2 nn.nn*?
                                      Row 2: '3 vv.vv*?4 nn.nn*?
 where vv.vv = voltage. *=battery alert, ? = timeout AKA lost signal alert. 16 pixel rows
 Over voltage shows as -----, under voltage as -0.00, no data is just blank

2. Single channel: Row 1: N vv.vv *   Min
                  Row 2:             mm.mm
                  Row 3:         ?   Max
                  Row 4:  Bat b.bb   mm.mm

 where N=channel, nn.nn = volatage,, mm.mm= min or max voltage, 
 b.bb=sender's Vdd (bat) voltage (appears for a few seconds only to reduce clutter)
 Rows are 8 pixels high in Single view, though N and vv.vv are taller.

A customised font file is used with battery state and signal timeout chars
Tested on Arduino nano and Auduino IDE 1.8.13
