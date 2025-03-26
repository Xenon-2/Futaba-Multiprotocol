# Futaba-Multiprotocol
Serial Multiprotocol interface for Futaba or every transmitter with PPM interface ( via trainer port ).

Goal: Give to all Futaba radios and more in general to all PPM capable radios, the possibility to use the multiprotocol module.

Adavantages: 

1: Use your own trusted transmitter.

2: Use transmitter that has proprietary firmware, stable and solid( e.g. Futaba, Spektrum, Jr ... )

3: Avoid "Loss of conformity" of your trasmitter installing firmwares like OpenTx or EdgeTx, not officially released on the manufacturer website.

4: Save money, no need to buy other trasmitters.

BOM

1 x Arduino nano

1 x Oled display SH1106

1 x Banggood iRangeX IRX4 Plus 2.4G CC2500 NRF24L01 A7105 CYRF6936 4 IN 1

1 x Sdcard module (Optional)

No source code will be available at the moment, just the binary to upload to arduino nano.

Waiting to test Banggood IRangeX IRX4 LITE

Connection diagram<br />
<pre>
Nano  SH1106<br />
 A4    SDA<br />
 A5    SCL<br />
 5V    VCC<br />
GND    GND<br />
</pre>
_______________
<pre>
POWER
NANO      TX
VIN      8.4+ ( should work also with 3s but not tested )
GND      GND
</pre>
_______________
<pre>
PPM in from TX
NANO     TX
 D2     PPM signal out
</pre>
_______________
<pre>
Serial to Multiprotocol module
NANO    MPM
TX1     Serial in
VIN     +BAT
GND     -GND
</pre>

MPM Pinout
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


