# Experiences-with-esp-controllers
# purpose share experiences 
# 1)power issues
Destroyed esp32? Backcurrent due to voltage difference powersupplies.<br />

Using the usb connection and external power 5v  together can destroy your esp32!!<br />

When there is a voltage difference between the power 5v usb and external power ,current will flow to the lowest V power. 

Sadly destroyed regulator on nodemcu on one and then completely ruined another one.

It does not always happen luckily but is really annoying. Disconnect powersupply when using usb cable or use usb cable where 5v is disconnected  and use wires tx rx and gnd only usb cable. then you can use the external 5v on.<br />

I use a lot serial com for debugging. <br />

Another solution is ideal diode circuit in series with power this prevents backcurrent to your powersupply or esp but then you have  to use 2 of these bloody things. <br />
The ideal diode is a mosfet module that you put in series at output power (drop is max 0.05v).  <br />
You can order them for up to 30 A . Appearantly used widely for solarpanels also.<br />

# 2)freezing after powerup esp module<br />

Appearantly when the powerup of your esp is to slow it can freeze. <br />
Pushing reset button helps each time. But no soft will resolve this issue.<br />
kda75330 protection for esp32 or es8266? <br />

When powering up the esp32 or esp8266 sometimes it does not start and is frozen.<br />
At first i was puzzled. resetting  via the rest button and  it was back ok. I digged somewhat deeper  because i noticed it was recurring many times and each time at powerup .<br />
It appears and proven by the great youtuber andreas spiess., when power is supplied and it is somewhat slow the esp starts with unsufficient power and freezes. <br />
Using a kda75330  (3.3v voltage level guard)connected to enable esp32 prevents the freezing, and hardware wise resets it for you.<br />
Links:<br />
#315 How to use Voltage Supervisors to protect ESP32, Raspberry Pi, and Batteries<br />
https://lnkd.in/eFT33rRH<br />

or #436 How to use Voltage Supervisors to protect ESP32, Raspberry Pi, and Batteries" (or the earlier version, "#315").<br />

I hope this info helps for the many esp32 fans. :) <br />
