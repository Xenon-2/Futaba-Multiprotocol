![screenshot](MPF4.png)

# Futaba-Multiprotocol
Serial Multiprotocol interface for Futaba or every transmitter with PPM interface ( via trainer port ).

**Goal:** Give to all Futaba radios and more in general to all PPM capable radios, the possibility to use the multiprotocol module.

**Adavantages:** <br />
1: Use your own trusted transmitter.<br />
2: Use transmitter that has proprietary firmware, stable and solid( e.g. Futaba, Spektrum, Jr ... )<br />
3: Avoid "Loss of conformity" of your trasmitter installing firmwares like OpenTx or EdgeTx, not officially released on the manufacturer website.<br />
4: Save money, no need to buy other trasmitters.

**USAGE**<br />
**BOM**

1 x Arduino nano<br />
1 x Oled display SH1106<br />
1 x Banggood iRangeX IRX4 Plus 2.4G CC2500 NRF24L01 A7105 CYRF6936 4 IN 1<br />
1 x Sdcard module (Optional)<br />

No source code will be available at the moment, just the binary to upload to arduino nano.

Waiting to test Banggood IRangeX IRX4 LITE 

**Connection diagrams**<br />
<pre>
Oled Display
_______________
Nano  SH1106<br />
 A4    SDA<br />
 A5    SCL<br />
 5V    VCC<br />
GND    GND<br />
</pre>
<pre>
POWER
_______________ 
NANO      TX
VIN      8.4+ ( should work also with 3s but not tested )
GND      GND
</pre>
<pre>
PPM in from TX to nano
_______________
NANO     TX
 D2     PPM signal out
</pre>
<pre>
Nano Serial to Multiprotocol module
_______________
NANO    MPM
TX1     Serial in
VIN     +BAT
GND     -GND
</pre>
<pre>
MPM Pinout
_______________
___________
|         |
|         |
|         |
|         |
|        x|  Serial In  
|        x|
|        x|  +Bat
|        x|  -GND 
|________x|
</pre>
![screenshot](MPF1.png)
![screenshot](MPF2.png)
![screenshot](MPF3.png)

