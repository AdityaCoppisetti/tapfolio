
title: "tapfolio"
author: "(dhruv) adtiya coppisetti"
description: " A handheld NFC device for developers, makers, and creators."
created_at: "2026-06-7"

hour - 1  i am making the build plan and how it will function :) 

Build Plan (v1)

 1. Hardware Wiring

 seed studio xiao

Main microcontroller responsible for the user interface, NFC payload management, and device logic.
PN532 NFC Module (SPI Mode)

Connections:
 SCK
 MOSI
 MISO
 SS (Chip Select)
 3V3
 GND
The PN532 operates in card emulation mode and dynamically serves NFC URL records based on the selected profile.

2.8" SPI TFT Display

Connections:

 SCK
 MOSI
 CS
 DC
 RST
 3V3
 GND

Used to display the active profile, navigation menu, and device status.

Buttons

Three tactile buttons:

 Up
 Down
 Select

Configuration:

  GPIO input
 INPUT_PULLUP enabled
 Button connected to GND

 Power System

Power Architecture:

LiPo Battery
- TP4056 Charger & Protection
- Power Switch
- ME6211 3.3V Regulator
- ESP32 + PN532 + TFT

Battery:

 3.7V 500mAh LiPo

Charging:

 TP4056 Li-ion charging module

Regulation:

 ME6211C33M5G-N 3.3V LDO regulator



 2. Firmware Architecture

 Device States

BOOT

 Initialize peripherals
 Load profile data
 Build initial NFC payload

MENU_NAV

 Navigate between stored profiles
 Update display

EMULATION_READY

 Active profile selected
 Waiting for NFC interaction

EMULATION_ACTIVE

 Phone detected
 NDEF record served

ERROR

 Display error message
 Attempt recovery or restart



 3. Data Model

Each profile contains:

 Label
 URL
 NDEF payload

Example:

Portfolio
 https://yourportfolio.com

GitHub
 https://github.com/username

Resume
 https://yourresume.com

The active NFC payload is rebuilt whenever the selected profile changes.



 4. User Experience Flow

Power On
↓
Load Saved Profile
↓
Display Active Profile
↓
Navigate Using Buttons
↓
Select Profile
↓
Generate NFC Payload
↓
Display "Tap Phone"
↓
Phone Reads NFC Tag
↓
Open URL
↓
Display "Sent!"

Optional Feedback:

 Status LED flash
Short buzzer notification



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

<img width="323" height="306" alt="image" src="https://github.com/user-attachments/assets/1e222b18-8261-4092-a1f9-bb5c0d8b19f8" />

the image states exactly why im using it. its small compact and easy to use. 
this is exactly how i pinned it with the raspberry pico 
this is the schematic for the raspberrry pico and how ive connected everything to it using labels.

<img width="430" height="658" alt="image" src="https://github.com/user-attachments/assets/47b5a41b-ec2a-4eec-a82e-e41f3788261c" />


everyhting put together looks like this-

<img width="790" height="844" alt="Screenshot From 2026-06-16 00-03-54" src="https://github.com/user-attachments/assets/614d55bd-76f4-44db-bf62-b43c36229ab4" />














