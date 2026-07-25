

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

this is the wiring i did w the rasp pico.


<img width="516" height="782" alt="image" src="https://github.com/user-attachments/assets/efcb0142-06ac-41ca-bcf3-5890cea2ee9c" />


and the switches to select are like this- 



<img width="708" height="508" alt="image" src="https://github.com/user-attachments/assets/7ce481c0-5d6f-46a6-a014-ca69858fe348" />





everyhting put together looks like this-


<img width="816" height="890" alt="image" src="https://github.com/user-attachments/assets/1bb39306-4e99-4867-8840-aa25bf2cf09c" />




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


oh yeah almost forgot! here are the footprints for the main pcb board!



<img width="713" height="203" alt="image" src="https://github.com/user-attachments/assets/a56e8654-645a-4107-aeab-74506795e432" />



work still required to do-

make a case for it ( what if i dont make a case and let it be out there? would be intresting lowk but idk.
i might actually design the main board pcb again.
 and then i have to assemble it 



title: "tapfolio"
author: "(dhruv) adtiya coppisetti"
description: " A handheld NFC device for developers, makers, and creators."
created_at: "2026-06-30"


so basically previously i did mention that i might have to make the main pvb again
why? 
my reasoning is that if the pcb is indeed that big then i why not use the nfc module on your phone? like if its that big it doesnt serve the small form factor quality 
and i really want it to be as small and compact as possible.


here i what i think i did wrong with the previous pcb design.

1- there is no reason for me to have a fancy switch layout 
if i put them in a line thats works good aswell


<img width="265" height="198" alt="image" src="https://github.com/user-attachments/assets/16ec003e-48dc-4333-bad9-095931971d1d" />


i lowkey dont know why have so many switches , 2 switches work fine- up down and select because like what else am i even going to do?
i had plans of making this a music player aswell but i would prefer not to as i have that saved as a entirely different project called mp3pod.


2- okay so im learning kicad as i go and i had completely butchered the layout on the components as i had sent
the switches on the back of the pcb as i thought they would still work which they wont because then the switches wont be connect w the
first layer where it should be.
so i had to this time not do that and lay it all out cleanly.

<img width="402" height="625" alt="image" src="https://github.com/user-attachments/assets/588a04ee-8fd0-4dab-9fbc-cd2c22b700f9" />


like just looking at the pcb its so big and the way ive placed pin headers is weird.

so i began working today and i fixed the pcb.

here is the new design


<img width="574" height="626" alt="Screenshot From 2026-06-30 16-28-40" src="https://github.com/user-attachments/assets/9565194e-079e-425d-8e44-b25936eb5da5" />


i lowkey really wanted to leave some space in the bottom and add silly pictures using the image converter thingy but i couldnt figure it out and it was justt way too lil space
HOWEVER IT IS CLICKING TO ME I COULD PUT THE IMAGES ON THE BACK LAYER OF THE PCB. 

but if i am to be honest i dont think im going to get a pcb made as im trying to save up my points and get something from the shop.
i might make it without like a custom made pcb,


i might just get a perfboard and make it myself.


there is another design i saw on pintrest which look incredibly intresting i might make it as v2 at the next hackclub hardware event.


<img width="1060" height="707" alt="image" src="https://github.com/user-attachments/assets/53f06a33-3e30-4942-aae8-bf5dc1151276" />


what i find incredibly intriguiging is that they are using keyboard switches which is more cool in my opinion.

also that display works aswell i dont know why im using this fancy disply if my goal is just to share the portfolio via nfc.
maybe something i could do later on. 



here is how the pcb looks like in 3d view-



<img width="340" height="373" alt="Screenshot From 2026-06-30 16-28-50" src="https://github.com/user-attachments/assets/6d8065aa-3bed-41b0-a0c7-ae19d3ed5711" />

i think this is compact enough lowk.







## **july-23** 
**11.53 PM**
**Thursday**

i got a review back when i submitted my prioject which pointed out a few flaws-
1) i should design a case for it as it would not look good without a case
2) i need to make the BOM in .csv format
3) wouldnt i need like a lanyard to wear it? yes i would and i already had that so i didnt feel like mentioning that

JUST TO CLARIFY THIS ISNT A NECKLACE THIS IS A BADGE.


i had no clue what a .csv file means so i asked chatgpt for help but that was pointless as it kept getting shit wrong. 
but it did make me a layout and i could open it with libreoffice ( i use linux) and so i just edited that and made the final BOM file. 
the file looks like this- 



<img width="1544" height="732" alt="image" src="https://github.com/user-attachments/assets/0e9686c4-8f0b-4bc4-9312-4f6aa1121f47" />

and then i moved onto the case- 


i made it sqaure in shape although i did aim for something curved.
anyways i used onshape to make the case and i have saved them in my repository as "tapfolio.x_t" ( parasolid) and then "tapfolio case.stl" (stl)

here is how the case looks like 



https://github.com/user-attachments/assets/977d31d9-c725-4749-b979-902cc5812be8



i hate when there isnt space for the lanyard hook to fit into and it always kinda bent thats why i put a small hole at the top, i wanted 2 beams and a small cylinder
but i couldnt really extrude that for some weird reason.

<img width="570" height="510" alt="image" src="https://github.com/user-attachments/assets/5c751b52-64b0-42ee-8a63-a68133ce599e" />


and then i put holes so i can put the screws in. i already have screws and you can even use zipties instead of screws ( just because you can doesnt mean you should)




and then i put a tiny square hole for the usb to pass thru 

<img width="570" height="510" alt="image" src="https://github.com/user-attachments/assets/66e7975a-2643-4fc1-a575-f02d8c8ecfce" />





<img width="1535" height="440" alt="image" src="https://github.com/user-attachments/assets/39a0ec4e-487f-45d5-b8b8-803b9f36d540" />



oh and i made the sqaure hole at the back so the nfc module can send the info without a problem and plus its cool to look at 





<img width="911" height="811" alt="image" src="https://github.com/user-attachments/assets/e330117c-efcc-469e-a39a-9e3f8144f076" />


july 25th 2026
time- 6:53AM 

i thought about it and indeed this would be too large to wear around yourself so im redesigning the pcb. 
starting off in the morning with a fresh mind and im already doing better than before.

also i realised that the wiring for the pn532 module wasnt right 

so i corrected it- 

<img width="516" height="506" alt="image" src="https://github.com/user-attachments/assets/0ec547d8-6c47-4062-a242-05ce857e371c" />


im redesigning the pcb which means redesigning the case which is fun tbh. 

oh and i uploaded the pcb to jlcpb and when i saw it i realised i could change the pcb hehe.

<img width="516" height="506" alt="image" src="https://github.com/user-attachments/assets/322bd17d-d569-46e9-8c6f-71811d56a350" />


i am saving space by sending the pi pico to the other side and then using that free extra space in the middle to put the buttons, 
this should be fun


time is 7:14 
i just realised why the fuck are there so many buttons,
technically all i need is up down and select right?
its not like im going to be adding any animations or smth, maybe a smiley face but i can make the middle button multifunctional. 
right?

so i changed the schematic a lil-

<img width="778" height="561" alt="image" src="https://github.com/user-attachments/assets/0d9d6d97-3456-4416-a98c-2cbb904013e7" />

i realised this while routing btw that why the litral fuck are there so many button man. 

i forgot to change the label name and they all said they were switch 1 which once again confused me during routing. here is how it should look like

<img width="778" height="561" alt="image" src="https://github.com/user-attachments/assets/33480401-c618-4727-8bdc-e8addf2fd022" />


time 7:45 
i realised that the wiring for the display was also wrong so stupid of me man.
according to the module picture here is how to wire it 

<img width="455" height="395" alt="image" src="https://github.com/user-attachments/assets/f8bb7d0c-cd5b-4f5e-8b2c-bba57017f211" />


<img width="928" height="746" alt="image" src="https://github.com/user-attachments/assets/4f91f46d-5134-443e-b6ce-fbb3576a72ab" />


and then due to that i had change the entire wiring in the rasp pico, the display and the nfc module are now sharing some common pins 

<img width="557" height="756" alt="image" src="https://github.com/user-attachments/assets/82b01317-82c7-4a29-a58a-8c8b209a5d6a" />

this is how it should look like

i made ALOT OF SILLY LIL MISTAKES which are not so silly when they are so much bahahha
after rerouting and everything this is what i ended up with. i wrote texts and put on silkscreen because by the time the pcb arrives i wouldve have forgotton what ive done.

<img width="1038" height="702" alt="image" src="https://github.com/user-attachments/assets/235e217a-62b6-4c8e-9217-63318eac3eb7" />


this is what it looks like in 3d view from the front-

<img width="628" height="542" alt="image" src="https://github.com/user-attachments/assets/c8a29058-64bf-48bd-8623-8bed2152c5d2" />

and then the back- 

<img width="628" height="542" alt="image" src="https://github.com/user-attachments/assets/70a40e25-f902-42c0-bf3c-83f58a1c45d2" />

actually ykw screw the case , i want it to look like that rugdy engineering that grabs a normal persons attention.

i added these holes so i could put the lanyard hooks through that. 

<img width="1046" height="437" alt="image" src="https://github.com/user-attachments/assets/ae0037d2-3848-4b1f-85e4-53fd3386544e" />

