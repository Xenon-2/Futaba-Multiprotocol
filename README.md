# As today the 16th of august 2025 I consider the project completed.
After months of positive tests flying with different radios, protocols and receivers i can say that the goal of the project is reached.

No further development will be done in order to keep this level of security and service.

I decided not to share the source becouse of the risks that you can face modifying the code. 

Anyway anyone can develop the same code studying the multiprotocol project https://github.com/pascallanger/DIY-Multiprotocol-TX-Module

Radios tested: Futaba T9, T14SG, T14MZ



![screenshot](MPF4.png)

# Futaba-Multiprotocol
Serial Multiprotocol interface for Futaba or every transmitter with PPM interface ( via trainer port ).

**Goal:** Give to all Futaba radios and more in general to all PPM capable radios, the possibility to use the multiprotocol module Banggood iRangeX IRX4 Plus via **serial connection**.<br />

**Legal aspects:**<br />
In EU is legal to control remote aircrafts only if:<br />
**-Use a ground control station (aka transmitter) that is EU Certified.**<br />
*-Note that transmitters that have installed open source firmware loose conformity and are not legal in EU.<br />
**-Use a RX that works on a certified protocol in EU in the band of 2.4 Ghz only.**<br />
<pre>
For example:
 Spektrum DSM 1 - No more available but certified in EU - Legal to use.
 Spektrum DSM 2 - Never certified in EU                 - NOT Legal to use.
 Spektrum DSM X - Still Available and certified in EU   - Legal to use.
 
</pre>
**Adavantages:** <br />
1: Use your own trusted transmitter.<br />
2: Use transmitter that has proprietary firmware, stable and solid( e.g. Futaba, Spektrum, Jr ... )<br />
**3: Avoid "Loss of conformity" (EU law 2019/947) of your trasmitter installing open source firmwares not certified by the constructor.**<br />
4: Save money, no need to buy other trasmitters.<br />
5: Using the multiprotocol module Banggood iRangeX IRX4 Plus in **serial mode** is far more simpler and safer then using **PPM mode**, no need to select protocol via the knob and bank of memory. Also avoid the risk to destroy contacts of the knob.<br />


**USAGE**<br />
After turning on the transmitter, the last used protocol is prompted.<br />
After 10 seconds the prompted protocol is activated unless ailerons stick is moved.<br />
Moving ailerons stick you can change the protocol to be activated(see pictures below).<br />
Once done you can move down elevator stick or wait 10 seconds to activate the selected protocol.<br />
See the picture above with radio in flight mode.<br />
**Important: For security reasons once protocol is activated (Flight Mode), it cannot be changed anymore. Need to recycle power.**<br />

**Pay attention that at the moment are used channel 1 for ailerons and channel 2 for elevators (AETR). If you use other mapping channels move sticks accordingly for channels 1 and 2.**<br />
**Channel mapping affects only protocol selection while the real channel mapping for your RX is controlled by the firmware version loaded on the IRANGEX**<br />

**BINDING procedure**<br />
After turning on the transmitter, move elevator stick UP to activate binding procedure as shown on the display.<br />
You have 10 seconds to put receiver on bind mode if not done before. After 10 seconds system will return to protocol selection.<br />

**Power consumption**<br />
With Futaba T14SG power consumption with internal module is 152mah.<br />
With this system and Banggood iRangeX IRX4 Plus 2.4G power consumption is almost identical, 153mah.<br />
So no issue with battery.<br />

**Supported protocols**<br />
All the protocols of the Banggood IRANGEX are supported.<br />
With scdcard a file named PROT.TXT is scanned to let browse supported protocols.<br />
User can choose protocols to use instead of browsing more then 100 protocols.<br />
Here is an example of PROT.TXT file(if sdcard is not present, system defaults to the protocols as shown in the example below):<br />
<pre>
"FRSKY D ",003,00,252
"  KDS   ",024,00,000
" CORONA ",037,16,254
"AFHDS2A ",028,17,000
" DSMX   ",006,48,000
"FRSKY R ",015,00,252
</pre>
fixed record lenght of 23 bytes 21 of data and CRLF<br />
Syntax: protocol name, protocol number, RxNum | Power | Sub protocol, fine tuning<br />


**BOM**

1 x Arduino nano<br />
1 x Oled display SH1106<br />
1 x Banggood iRangeX IRX4 Plus 2.4G CC2500 NRF24L01 A7105 CYRF6936 4 IN 1<br />
1 x Sdcard module (Optional)<br />

No source code will be available at the moment, just the binary to upload to arduino nano (find instructions online).<br />

Waiting to test Banggood IRangeX IRX4 LITE.<br />

**Hoping Banggood can create a IRangeX IRX4 with this system embended.**<br />
**I know that many people are not able to do it by themselves. They deserve one.**<br />

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
**Thanks to:**<br />
https://www.banggood.com/<br />
https://downloads.multi-module.org/?irangex<br />
https://github.com/pascallanger/DIY-Multiprotocol-TX-Module<br />

![screenshot](MPF1.png)
![screenshot](MPF2.png)
![screenshot](MPF3.png)

