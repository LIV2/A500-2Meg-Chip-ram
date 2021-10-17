# A500/2000 2MB Chip RAM Mod

This is an adapter board to retrofit a 2MB Agnus into an Amiga 500/2000 and also includes 2MB of chip ram

### A version that uses an (expensive!) PLCC plug instead of pinheaders is available [Here](https://github.com/LIV2/A500-2Meg-Chip-ram/tree/PLCC)

![PCB Top](Images/top.png?raw=True)
![PCB Bottom](Images/bottom.png?raw=True)

## Assembly Steps
1. Solder the DRAM, U4, U3
2. Solder the Capacitors & Resistor (Only fit VBB capacitor if your Agnus says VBB on the top!)
3. Solder the PLCC Socket making sure that the socket aligns exactly with the outline on the top of the PCB!
4. After soldering the socket, you may want to trim the joints down to the PCB to make soldering the pin headers easier. <br/>**Be careful when trimming the leads that you don't scratch the PCB solder mask!**
5. Prepare the pin headers by removing a pin from this corner of each as indicated here:<br/>
![remove](Images/header.png?raw=True)
6. Insert one of the pin headers just far enough for it to hold, making sure that it is level.<br/>
The side with the removed pin goes where indicated by the yellow arrow<br/>
I recommend doing them one by one in the order indicated:<br/>
If you will be soldering to the Amiga rather than using sockets, I would recommend soldering the long side of the pins to the adapter<br />
![locations](Images/pins.png?raw=True)
![insert](Images/insert.png?raw=True)
​
7. Solder in each pin, don't use too much solder!
8. Repeat for each pin header<br/>
![solder](Images/solder.png?raw=True)
9. Solder a wire to A20 and connect the other end at one of the following locations:
   * Gary pin 36
   * CPU pin 48
   * JP5 Top left pad (A500 Rev 6)
10. Make sure that JP2 is set as shown:<br/>
![jp2](Images/JP2.png?raw=True)
11. Carefully desolder & remove the Agnus socket
12. Remove the same corner pin from each pin socket and solder them in replacing the agnus socket
13. Insert the adapter
**To make sure it is installed the correct way, pay attention to the marking of "1" on the PCB and on the Amiga they must match**<br />
On a Rev 6A Amiga 500 this means that the ram will be on the right hand side, on a Rev 5 it will be pointing downwards instead.<br />
look from the sides to make sure the pins are going in to the headers<br />
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
|74AHCT158 Quad 2-input Multiplexer, SOIC-16|U4|1|[Mouser](https://www.mouser.com/ProductDetail/595-SN74AHCT158D) |Optional, set J1 to "28M" to bypass|
|PLCC-84 Socket, Through-hole|U1|1|[Mouser](https://www.mouser.com/ProductDetail/437-5408808424008) ||
|5V, 1Mx16 EDO/FPM DRAM, SOJ-42<br>- K4F151611<br>- K4E151611<br>- GM71C18163C<br>- AS4C1M16E5|U2|1|eBay, Aliexpress etc||
|22-Pin, 2 Row Female header||4|[Mouser](https://www.mouser.se/ProductDetail/517-929975-01-11-RK)||
|22-Pin, 2 Row Male header||4|[Mouser](https://www.mouser.se/ProductDetail/649-77313-118-22LF)||
