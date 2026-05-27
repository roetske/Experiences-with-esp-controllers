# Experiences-with-esp-controllers
#purpose share experiences 
#power issues
Destroyed esp32? Backcurrent due to voltage difference powersupplies.

Using the usb connection and external power 5v  together can destroy your esp32!!

When there is a voltage difference between the power 5v usb and external power ,current will flow to the lowest V power. 

Sadly destroyed regulator on nodemcu on one and then completely ruined another one.

It does not always happen luckily but is really annoying. Disconnect powersupply when using usb cable or use usb cable where 5v is disconnected  and use wires tx rx and gnd only usb cable. then you can use the external 5v on.

I use a lot serial com for debugging. 

Another solution is ideal diode circuit in series with power this prevents backcurrent to your powersupply or esp but then you have  to use 2 of these bloody things. The ideal diode is a mosfet module that you put in series at output power (drop is max 0.05v).  You can order them for up to 30 A . Appearantly used widely for solarpanels also.
