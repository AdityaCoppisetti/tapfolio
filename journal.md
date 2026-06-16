
title: "tapfolio"
author: "(dhruv) adtiya coppisetti"
description: " A handheld NFC device for developers, makers, and creators."
created_at: "2026-06-7"

hour - 1  i am making the build plan and how it will function :) 


 5. Project Goals

 Portable and rechargeable
 Dynamic NFC link sharing
 Product-like user experience
 Compact handheld form factor
 Easy profile switching
 Reliable Android NFC compatibility
 Open-source hardware and firmware


JUNE-16 2026
7:34 pm

yesterday i worked on making the schematic and thought once i would do that i would be done. but ofcourse there is the routing of everything.
i had started the schematic by placing the seed studio MCU first but then i realised that there wouldnt be enough pins.
and so i had recently used a raspberry pi pico in a keyboard project on mine and so i was familiar with that and so i did that. 
kicad didnt have the symbols for the nfc module nor the display i was using but i knew the pins both the modules were using so i just added a pinconnector to which i can either solder the modules directly to or make it swapable. i will be soldering them direcly as i need more practice soldering stuff and i need to make this as thin as i can.
i suggest the people trying to make this would first try the guides that hackclub has provided like a keyboard or a devboard or a macropad.

<img width="673" height="414" alt="image" src="https://github.com/user-attachments/assets/aac68272-aba4-4038-892d-4b86fdf81839" />


here is me placing the components needed. i have to say im getting better at using kicad and other softwares, perhaps its the practice ive been getting.

this is me connecting the pins to the display module. i kept messing up the layout so i used the amazon picture i had and i saw how the pins where on the module. 
im not entirely sure about it but i think on different variation or sizes? the pins are switched out so make sure thats not the case. ( mine is the st7735 1.8inch)

<img width="362" height="300" alt="image" src="https://github.com/user-attachments/assets/64c57e53-f306-47e9-8414-2426a7a511d9" />

<img width="405" height="218" alt="Screenshot From 2026-06-16 19-38-12" src="https://github.com/user-attachments/assets/dff96e4f-ac56-4e60-82e8-41f7ad6924b1" />

the exact display module that im using- 
<img width="1349" height="626" alt="image" src="https://github.com/user-attachments/assets/3c58f224-343e-47fa-aadc-caaa4c69c1cf" />


now onto the nfc module - 

<img width="612" height="792" alt="image" src="https://github.com/user-attachments/assets/3160a99f-8d23-4c57-91d1-dfd3da48b52b" />

this is the nfc module im using and this picture is kinda important depends on you.

<img width="323" height="306" alt="image" src="https://github.com/user-attachments/assets/1e222b18-8261-4092-a1f9-bb5c0d8b19f8" />

the image states exactly why im using it. its small compact and easy to use. 
this is exactly how i pinned it with the raspberry pico 
this is the schematic for the raspberrry pico and how ive connected everything to it using labels.

The PN532 is a highly integrated transmission module for contactless communication at 13.56 MHz including microcontroller functionality based on an 80C51 core with 40 Kbytes of ROM and 1 Kbytes of RAM. The PN532 combines a modulation and demodulation concept completely integrated for different kinds of contactless communication methods and protocols at 13.56 MHz with an easy-to-use firmware for the different supported modes and the required host controller interfaces.

Note : HW-147 on board working remains same .
Features:
Support II2, SPI and HSU (High-Speed UART)
I2C / UART: 3.3V ~ 24V TTL
SPI: 3.3V TTL with 100-ohm resistors in series
Communication distance: 5cm~7cm
On-board level shifter, Standard 5V TTL for I2C and UART, 3.3V TTL SPI
Work in NFC Mode or RFID reader/writer Mode
RFID reader/writer supports:
Plug and play, compatible
Built-in PCB Antenna, with 4cm~6cm communication distance
On-board level shifter, Standard 5V TTL for I2C and UART, 3.3V TTL SPI
Work as an RFID reader/writer
Work as a 1443-A card or a virtual card
Exchange data with other NFC devices such as a smartphone


<img width="430" height="658" alt="image" src="https://github.com/user-attachments/assets/47b5a41b-ec2a-4eec-a82e-e41f3788261c" />


everyhting put together looks like this-

<img width="790" height="844" alt="Screenshot From 2026-06-16 00-03-54" src="https://github.com/user-attachments/assets/614d55bd-76f4-44db-bf62-b43c36229ab4" />

so you could power your tapfolio by the raspberry pico and a wire thats connected to a power bank or your phone but that kinda defeats the pupose of not using a phone to share your portfolio.
and so im putting liPo bateries in my project and for that i need a tp4056 module. but kicad didnt have the module , just the ic of the module and so i thought here's another learning experience and made my own tp4056 module. 


i used this diagram to my reference- 


<img width="584" height="326" alt="image" src="https://github.com/user-attachments/assets/bf3b02da-83ac-41c8-a4d4-4f4030f35f1c" />


i wanted to put a c type port because i always have c type cables around me but its totally upto you.


<img width="468" height="422" alt="image" src="https://github.com/user-attachments/assets/82eb55e0-4e38-493d-abe8-0af307b82b8e" />

MAKE SURE YOURE USING - USB_C_Receptacle_PowerOnly_24P because we want this device to be compact and not have any extra useless pins.
according to me this is how it looks like 


<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/498aa16b-f369-4d72-b7dd-ad61d17dcffb" />

now onto the charging circuit. - 


<img width="514" height="358" alt="image" src="https://github.com/user-attachments/assets/02550b95-146a-4627-9c43-f9eab99b009d" />

this is what i made with reference to the diagram 
and then im using this to connect the board to the battery-


<img width="236" height="364" alt="image" src="https://github.com/user-attachments/assets/056c0a63-269d-4936-b70f-694805d9bfea" />


everything together looks like this- 


<img width="1200" height="360" alt="image" src="https://github.com/user-attachments/assets/3d522f5b-4e90-4504-b1b8-61cb3b366657" />

i lowk thought that i hadnt assigned footprints and made design the tp4056 pcb but apparently i have so here it is 


<img width="715" height="301" alt="image" src="https://github.com/user-attachments/assets/69c3ae51-1195-4f2f-9c8a-f1124b43580d" />

this are the footprints of everything in the tp4056 module.

apparently i hadnt done the routing in my pcb so i did that and i fucking lost my mind doing that. i got ragebaited so i just removed the led i will figure some other way out later for now this is okay.


<img width="564" height="709" alt="image" src="https://github.com/user-attachments/assets/f1693893-6fbc-47de-9f6e-cbe32d842ec8" />

i have made my pcb like such but you can make it much better.

this is how my pcb looks like when its rendered.

front- 


<img width="409" height="463" alt="Screenshot From 2026-06-16 22-22-08" src="https://github.com/user-attachments/assets/a0c99202-379d-436f-b75f-fb4b2fd7ee53" />

and then the back is like this- 


<img width="409" height="463" alt="Screenshot From 2026-06-16 22-22-13" src="https://github.com/user-attachments/assets/8ba10cf0-e663-4ba3-b659-2440b3f9a452" />


i should probably integrate this into the main pcb besides having it yk , not in the main board. but i figured i will be using this for other projects so i can just take it out any time.



now lets get onto the main board pcb. 
i had very minimal trouble in routing , i feel as i go i will get better at it.


<img width="402" height="625" alt="image" src="https://github.com/user-attachments/assets/bb73970c-8a97-4536-acff-21683061304e" />


this is after all the wiring i think it could be smaller and more compact but for the version one this is okay.


this is the front

<img width="402" height="625" alt="image" src="https://github.com/user-attachments/assets/7ac3c284-6ce2-4765-a1c0-020c192eaafe" />


and the back looks like this 



<img width="402" height="625" alt="image" src="https://github.com/user-attachments/assets/69fca494-2b38-4eee-92b0-3c36fc7172f7" />


now this , unlike the tp4056 module was really fun to route.


work still required to do-

make a case for it ( what if i dont make a case and let it be out there? would be intresting lowk but idk.
i might actually design the main board pcb again.
 and then i have to assemble it 




















