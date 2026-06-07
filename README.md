HEY! So im dhruv coppisetti and im a fellow hackcluber like you guys! Ive been the cameraman for hack club Delhi for the past 3 events- daydream, campfire and build guild. 
Every person i meet and every event i go to, people think i am just a cameraman, AS IF I DONT KNOW ANYTHING IN ROBOTICS!!!!bahahaha i always prove them wrong by showing my projects and accomplishments.  
 
in build guild delhi my team did this incredibly creative thing where we 3d printed badges and put nfc tags behind them and we would program then to show anything we want like our insta profiles so we could connect with people in a fun way or show people our graphic designing portfolios. For me it was my photography portfolio - 

 https://portraitmode.io/profile/dhruv-coppisetti/ 

And so shortly after that event i was doing this marketing internship where i was setting up stalls in places in other cities and in my home city aswell. I would meet tons of people! Even customers that wanted to buy products would be great for networking as i would set up stalls in tech company buildings. Even the people in their own stalls beside mine would be extremely beneficial to network!  
 
after build guild i took a nfc fob I got with my robotics kit and programmed it to open my portfolio link. But that was just one portfolio out of – robotics, psychology, poetry, filmmaking and photography. And so thus began the ponder “ do i carry 6 different key fobs with me or what” i ended up with the conclusion that i need a creative and cool nfc portfolio badge that could be good to start conversations and impress the people im networking with ( basically make a lasting impression). And so, i decided – i would make something wearable around my neck, add a screen to it and buttons and make it look like a built it in a cave. 

 
LIKE COME ON GITHUB FOLLOWS THE SAME THING WITH THEIR E INK BADGES (only, that badge is incredibly expensive to get, but not to make. 
 
here is my vision for the badge ( i can't draw for shit so ill describe it, you’ll have to use your imaginations for this one) -   
 
for the nfc reader and writer i thought that the “blue PN5180 Nfc Rf Sensor Iso15693 Rfid High Frequency IC Card Icode2” would do my work and it would look cool but i later found  
“PN532 NFC RFID Reader Writer Module V0.0.1” and it was small, compact and good with reading and writing.  
 
so thats our nfc reader and writer module secured. 
 
now onto the official microcontroller.  i wanted something compact and workable so i thought i would use the xiao seed studio rp2040 microcontroller but the esp 32 seemed like a better choice.  
 
for this  
For this specific project, I'd lean toward ESP32 over the XIAO RP2040. 

  

Why? 

 Advantages of using an ESP32: 

1. Web Dashboard 

   - Edit portfolio links from a browser 

   - No need to reflash firmware 

2. Wi-Fi Configuration Mode 

   - Device creates its own hotspot 

   - Configure links from a phone or laptop 

3. Analytics 

   - Track number of scans per link 

   - Store statistics in flash memory 

4. Dynamic Content 

   - Change which link is active remotely 

   - Schedule different links for different situations 

Recommended Board: 

  

1. ESP32(Best Choice) 

   - Wi-Fi + Bluetooth 

   - USB-C 

   - Plenty of GPIO 

   - Easy PCB integration 

 

2. XIAO RP2040 

   - Simpler 

   - Lower power consumption 

   - No wireless features 

  

My recommendation: Use the ESP32. 

 

For the screen i was thinking i would maybe the “0.96 Inch I2C/IIC 4-Pin OLED Display Module” that everyone these days are using in their projects and people seem to be really satisfied with it. But no. I dont just want it to look common i want it to be special so im using a different screen. im using the - 2.8 inch SPI Screen Module TFT Interface 240 x 320 without Touch  cause its tiny and reasonably priced. 
 
I found this incredibly great deal. This esp23 in dollars is- 2.04 US Dollar lmaooo bahahhahaha ( should i be concerned? Probably) 
( i will be funding for my project on my own so you may find other deals in your area/region I am allotting about 1300 rupees for this project which is roughly - 13.69 US Dollars) 
 
 
i also want this to be battery powered and so my plan is - 

USB-C 

  │ 

  ▼ 

TP4056 Charger 

  │ 

  ▼ 

3.7V 500mAh LiPo 

  │ 

  ▼ 

Power Switch 

  │ 

  ▼ 

ME6211 3.3V Regulator 

  │ 

  ▼ 

ESP32 + PN532 + OLED 

 
Power System 

This device is powered by a single 3.7V 500mAh lithium-polymer battery, chosen for its compact size and ease of integration into a handheld enclosure. 

Battery charging is handled by a TP4056 charging module, allowing the device to be recharged through USB while also providing battery protection features such as overcharge and overdischarge protection. 

Since the battery voltage varies during operation, a dedicated ME6211 low-dropout regulator is used to provide a stable 3.3V supply for the ESP32, OLED display, and PN532 NFC module. 

The design intentionally prioritizes simplicity and portability, using a minimal power architecture that keeps component count low while providing sufficient runtime for   everyday use. 

 

The cost of everything is-  

ESP32 Module ₹194 

PN532 NFC Module ₹285 

2.8" TFT Display ₹521 

3x Tact Switches ₹18 

TP4056 Charger ₹25 

ME6211 Regulator ₹10 

500mAh LiPo Battery ₹130 

Slide Switch ₹10 

JST-PH Connector ₹5 

Capacitors ₹5  
 
total- ₹1203 
 
i will be getting the custom pcb from my local vendor so it’ll cost me less than usual. 
