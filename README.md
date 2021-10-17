# A500/2000 2MB Chip RAM Mod

This is an adapter board to retrofit a 2MB Agnus into an Amiga 500/2000 and also includes 2MB of chip ram

![PCB Top](Images/top.png?raw=True)
![PCB Bottom](Images/bottom.png?raw=True)

## Assembly Steps
1. Solder the DRAM, U4, U3
2. Solder the Capacitors & Resistor (Only fit VBB capacitor if your Agnus says VBB on the top!)
3. Solder the PLCC Socket making sure that the socket aligns exactly with the outline on the top of the PCB!
4. Solder the PLCC Plug, make sure the orientation matches the silkscreen on the PCB!
5. Make sure that JP2 is set as shown: (A500 only)<br/>
![jp2](Images/JP2.png?raw=True)
6. Insert the adapter, ensure that the adapter is oriented correctly by checking that the pin 1 marking matches the location on your motherboard<br />
![installed](Images/installed.jpg?raw=True)

## A20 Connection
### A500
Solder a wire to A20 and connect the other end at one of the following locations:
   * Gary pin 36
   * CPU pin 48
   * JP5 Top left pad (A500 Rev 6)

### A2000
Solder a wire to A20 and connect the other end at one of the following locations:
   * Gary pin 36
   * CPU pin 48
   * Also available from a via next to the power connector as indicated here:  
   ![a20_via](Images/A2000_A20_VIA.png?raw=True)

## Jumper Settings
The default jumper settings do not need to be changed and will work on all systems. 

The multiplexer at U4 is optional, if you decide not to fit this you can cut & set the 28M/MUX jumper to 28M.

Rev 6A Amiga 500's have jumpers that can be used to provide the A20 signal on pin 35 instead of XCLK
This allows us to use this adapter without having to add the wire to A20 but note **this will mean you cannot use a genlock on this Amiga!**

In this case you must set J1 to 28M to bypass the XCLK/28M Mux then set J2 of the adapter to A20<br />
If you wish to do this then you will also need to change the jumper settings at J5 on your A500 motherboard<br />
![jp5](Images/JP5.png?raw=True)

## Bill of materials
|Component|Location|QTY|Link|Notes|
|---------|--------|---|----|-----|
|Ceramic Capacitor, 0.1uF, 0805|C1-5,C7|6|[Mouser](https://www.mouser.com/ProductDetail/710-885012207098)||
|Ceramic Capacitor, 22pF, 0805|C6|1|[Mouser](https://www.mouser.com/ProductDetail/710-885012007053) ||
|Resistor, 150 Ohm, 0805|R1|1|[Mouser](https://www.mouser.se/ProductDetail/652-CR0805JW-151ELF)||
|74AHC1G08 Single 2-Input AND Gate, SOT-23-5|U3|1|[Mouser](https://www.mouser.com/ProductDetail/595-SN74AHC1G08DBVR)||
|74AHCT158 Quad 2-input Multiplexer, SOIC-16|U4|1|[Mouser](https://www.mouser.com/ProductDetail/595-SN74AHCT158D)|Optional, set J1 to "28M" to bypass|
|PLCC-84 Socket, SMD|U1|1|[Mouser](https://www.mouser.com/ProductDetail/517-8484-21B1-RK-TP)||
|PLCC-84 SMD Plug||1|[Adapt-Plus](https://www.adapt-plus.com/products_html/apw9328-zc160.html)<br>[RS-Components](https://uk.rs-online.com/web/p/ic-socket-adapters/7419684/)||
|5V, 1Mx16 EDO/FPM DRAM, SOJ-42<br>- K4F151611<br>- K4E151611<br>- GM71C18163C<br>- AS4C1M16E5|U2|1|eBay, Aliexpress etc||
