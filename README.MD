



here is how the pcb looks like - 


<img width="585" height="498" alt="image" src="https://github.com/user-attachments/assets/3ded33da-83c2-46f2-b200-da848829ddf7" />



<img width="585" height="498" alt="image" src="https://github.com/user-attachments/assets/2ac28925-283d-40db-9242-f28b612e9ab7" />


<img width="646" height="600" alt="image" src="https://github.com/user-attachments/assets/edaaef9e-0b70-4085-bb2c-0f273c337079" />



HEY! So im dhruv coppisetti and im a fellow hackcluber like you guys! Ive been the cameraman for hack club Delhi for the past 3 events- daydream, campfire and build guild. 
Every person i meet and every event i go to, people think i am just a cameraman, AS IF I DONT KNOW ANYTHING IN ROBOTICS!!!bahahaha  
 
in build guild delhi my team did this incredibly creative thing where we 3d printed badges and put nfc tags behind them and we would program then to show anything we want like our insta profiles so we could connect with people in a fun way or show people our graphic designing portfolios. For me it was my photography portfolio - 

 https://portraitmode.io/profile/dhruv-coppisetti/ 

And so shortly after that event i was doing this marketing internship where i was setting up stalls in places in other cities and in my home city aswell. I would meet tons of people! Even customers that wanted to buy products would be great for networking as i would set up stalls in tech company buildings. Even the people in their own stalls beside mine would be extremely beneficial to network!  

 
after build guild i took a nfc fob I got with my robotics kit and programmed it to open my portfolio link. But that was just one portfolio out of – robotics, psychology, poetry, filmmaking and photography. And so thus began the ponder “ do i carry 6 different key fobs with me or what” i ended up with the conclusion that i need a creative and cool nfc portfolio badge that could be good to start conversations and impress the people im networking with ( basically make a lasting impression). And so, i decided – i would make something wearable around my neck, add a screen to it and buttons and make it look like a built it in a cave. 

 
LIKE COME ON GITHUB FOLLOWS THE SAME THING WITH THEIR E INK BADGES (only, that badge is incredibly expensive to get, but not to make. 
 
here is my vision for the badge ( i can't draw for shit so ill describe it, you’ll have to use your imaginations for this one) -   
 
for the nfc reader and writer i thought that the “blue PN5180 Nfc Rf Sensor Iso15693 Rfid High Frequency IC Card Icode2” would do my work and it would look cool but i later found  
“PN532 NFC RFID Reader Writer Module V0.0.1” and it was small, compact and good with reading and writing.  
 
so thats our nfc reader and writer module secured. 
 
now onto the official microcontroller. 
 
for this  
For this specific project, im leaning with the raspberry pi pico 

okay so here is the schematic + components im using!

<img width="826" height="835" alt="image" src="https://github.com/user-attachments/assets/773b8ae4-4856-4b1c-a78a-bb5338dab076" />

i also want this to be battery powered and so my plan is - 

Power System 

This device is powered by a single 3.7V 500mAh lithium-polymer battery, chosen for its compact size and ease of integration into a handheld enclosure. 

Battery charging is handled by a TP4056 charging module, allowing the device to be recharged through USB while also providing battery protection features such as overcharge and overdischarge protection. 

Since the battery voltage varies during operation, a dedicated ME6211 low-dropout regulator is used to provide a stable 3.3V supply for the ESP32, OLED display, and PN532 NFC module. 

The design intentionally prioritizes simplicity and portability, using a minimal power architecture that keeps component count low while providing sufficient runtime for everyday use. 

however i wanted to use the tp4056 , i couldnt find the symbol in the kicad library , now i could just download it from somewhere but whats the fun in that so i decided to make my own , you can find the documentation for that in the journal.md


 here how the lithium battery charging module i made!

the components- 

<img width="1022" height="529" alt="image" src="https://github.com/user-attachments/assets/1ca15466-6af5-4f68-ae6b-fad0be63a700" />



and how my pcb looks like - 

<img width="733" height="628" alt="image" src="https://github.com/user-attachments/assets/f9d9710b-2eb9-478f-9481-f5f18f588534" />

it is really really compact

 this project has taught me:-
 
 1) schematics
 2) pcb making 
 3) the evil task of routing 
 4) cad (this is also evil i just cant prove it)
 5) and then documentation
 6) the rest i kinda already knew but i did become better at it
 
