# Keyboard Build Journal
## Entry 1 — Figuring out hardware and layout
Date: 7/25/2026

I started planning out the layout for my keyboard. I really didn't want a  keyboard where your hand are kept TOO close and become sweaty, So I found a layout that have some space between, but at the same time, I wanted to maintain most of the function that I would have on a conventional laptop. So, I settled with a 65% layout, I used the reference picture below. its called the ALICE LAYOUT.
I also made my  layout in https://www.keyboard-layout-editor.com/                                                                            
  HERE'S THE KEYBORAD **RAW DATA** :- IT WILL BE IN FOLDERS ON LEFT U CAN CHECK IT OUT OR DO SOME ExERIMENT WITH IT .
###### *TOTAL HOURS FOR LAYOUT* :  1hr-75min

<img width="1080" height="607" alt="image" src="https://github.com/user-attachments/assets/d08eb092-acad-4209-be25-c966cc5bad15" />
<img width="432" height="189" alt="layouut" src="https://github.com/user-attachments/assets/d36e256b-bb1d-48da-ae0b-e1364ab0c700" />
                                                                                                                
## Entry 2 — MAKING my SCHEMATIC
Date: 7/26/2026

Today I started making my first keyboard schematic in KiCad. First, I added all the symbols from the symbol library, like the switches, diodes, SK6812 RGB LEDs, Raspberry Pi Pico, OLED, and the joystick so it will look cool                             <img width="22" height="22" alt="image" src="https://github.com/user-attachments/assets/5d66d161-8bd5-44ad-8ee7-96906f66c585" />
.
I started with the matrix and made a lot of nice progress with tracing and connecting the other components. I also fixed some wiring and checked that everything was connected properly.
<img width="1002" height="563" alt="Screenshot 2026-07-02 200518" src="https://github.com/user-attachments/assets/bf523c0f-eae4-4e9e-9f60-8de163b7509a" />                                               

### Adding the Other Components

After the main keyboard matrix was done, I added the extra features I wanted. I added an OLED for displaying information, a rotary encoder for things like volume or scrolling, and a joystick that I can use for mouse control. I also added resistors and capacitors for the RGB . I considered adding some other things during the project, but I removed or changed a few ideas to keep thekeyboard manageable.                                     
It's easily subject to change after I add the rotary encoder. I'm not exactly sure how I'm supposed to incorporate the encoder right now. All of the other components are pretty simple it just took me some time to connect other componets see
see u later, bye                                                                                    

I have finished my RGB light matrix thingyy , and I was having some  ERRORS while arranging my RGB BACKLIGHT (Matrix) called the   "Input power pin not driven by any Output power pins" and its telling to  Add  PWR_FLAG (its purely a schematic validation tool) ,  near +5v power net line and it  WORKED  (Cleared all the Errors)    
(UPDATE FOR THiS PROBLEM:- It can also be solved after I connected my 5v to VBUS on Raspberry Pi poco so there was no need for PWR_flag )
<img width="824" height="565" alt="image" src="https://github.com/user-attachments/assets/d199213e-dd65-445d-975f-5bd75159b55b" />
<img width="623" height="384" alt="image" src="https://github.com/user-attachments/assets/83f04c98-e525-4b72-b055-d60e63be806a" />
  AND TIME TO GET BACK TO KICAD , SEE U IN A MINUTE
                                                                                                                        
Wired up the EC11 encoder (A/B/C for rotation, S1/S2 for the click). Also connected the joystick analog it was preety simple to connect then, Spent a while figuring out OLED options — I wanted A looong screen put apparently 4 pin OLEDs don't come in 256x32, so I had to settle for a 128x32 display,  which gave a me a bit more surface area. here's a LOOK!
<img width="769" height="582" alt="image" src="https://github.com/user-attachments/assets/cc9e7f90-6eb1-41f3-a087-e7e7c042cb34" />
I still need to connect all the components (some parts like :- key matrix, RGB matrix thingyy and etc.) and almost  forgot add  stabilizer and mounting holes and also need to assign the footprints for the components
OKAY! the only things I need to do is assign footprints and solve some ERC ERRORS ( Electric Rules Checker ) , 
heres how my schematic looks 
<img width="1257" height="489" alt="SVHEMATIC FULL PIC" src="https://github.com/user-attachments/assets/345f3c25-c65e-4a40-9b5f-2f7fb21d440c" />

## 🔧 Assigning Footprints
The schematic is mostly finished, I started assigning footprints to the components. This was a little confusing at first because I learned that the symbol in the schematic and the actual footprint on the PCB are different things. I used the KiCad libraries and the ai03 keyboard library (Downloaded from GitHub) to find suitable footprints for the switches, stabilizers and other components.


# Okay it's me after many  hours later :- 
Wasup people !  I am  glad to announce that I have FINISHED my PCB SCHEMATIC after working continuousley on it  , LETS GO! 
After spending a lot of time checking connections and making sure every component was placed correctly ,  I made tremendous progress with the Schematic and was able to complete it , everything went extremely well this session. 
I implemented resistors and capacitors wherever I needed them I was able to complete the entire schematic. I also assigned footprints to all the components. Along the way I learned a lot about how different parts connect together and fixed several small mistakes that were causing errors.
HERE ARE SOME PIC OF FINAL LOOK :- 
###### *TOTAL HOURS FOR LAYOUT* : 15
<img width="1257" height="489" alt="SVHEMATIC FULL PIC" src="https://github.com/user-attachments/assets/0d420072-a74a-4920-b8ff-eec13bcdfa16" />
Seeing the schematic finally come together feels really satisfying and everything went extremely well this session. 

#### NOW  IT'S READY FOR THE PCB LAYOUT  , ( BUT FIRS I NEED SOME REST, MY BACK IS PAINING)

## Entry 3 — MAKING my PCB

### 📐 Arranging the PCB
After assigning the footprints, I moved everything from the schematic into the PCB Editor. At first there were components everywhere with ratsnest lines connecting each other it was very confusing at first when I started arranging the components neatly on the PCB manually according to my Alice layout. So, first I placed the switches according to my Alice layout  because they were the most important parts. After that I arranged the OLED, Rotary encoder, Joystick, Micro controller ( Raspberry Pi Pico ) and the smaller components around them (stabilizer, mounting holes).

