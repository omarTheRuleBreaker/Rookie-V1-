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

Today I started making my first keyboard schematic in KiCad. First, I added all the symbols from the symbol library, like the switches, diodes, SK6812 RGB LEDs, Raspberry Pi Pico, OLED, and the joystick so it will look cool                           
<img width="22" height="22" alt="image" src="https://github.com/user-attachments/assets/5d66d161-8bd5-44ad-8ee7-96906f66c585" />.
.
I started with the matrix and made a lot of nice progress with tracing and connecting the other components. I also fixed some wiring and checked that everything was connected properly.
<img width="1057" height="370" alt="image" src="https://github.com/user-attachments/assets/82570bed-373c-4c8e-8002-317c12303986" />

                                             

### Adding the Other Components

After the main keyboard matrix was done, I added the extra features I wanted. I added an OLED for displaying information and a joystick that I can use for mouse control. I also added resistors and capacitors for the RGB . I considered adding some other things during the project, but I removed or changed a few ideas to keep the keyboard manageable.                                     
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

<img width="675" height="437" alt="image" src="https://github.com/user-attachments/assets/939c21b6-cff7-426c-b35e-6d89d0860a57" />

### UPDATE: I have removed the Rotary Encoder due to less GPIO pins

## Assigning Footprints
The schematic is mostly finished, I started assigning footprints to the components. This was a little confusing at first because I learned that the symbol in the schematic and the actual footprint on the PCB are different things. I used the KiCad libraries and the ai03 keyboard library (Downloaded from GitHub) to find suitable footprints for the switches, stabilizers and other components.

# Okay it's me after many  hours later :- 
Wasup people !  I am  glad to announce that I have FINISHED my PCB SCHEMATIC after working Continuously on it  , LETS GO! 
After spending a lot of time checking connections and making sure every component was placed correctly ,  I made tremendous progress with the Schematic and was able to complete it , everything went extremely well this session. 
I implemented resistors and capacitors wherever I needed them I was able to complete the entire schematic. I also assigned footprints to all the components. Along the way I learned a lot about how different parts connect together and fixed several small mistakes that were causing errors.
HERE ARE SOME PIC OF FINAL LOOK :- 
###### *TOTAL HOURS FOR LAYOUT* : 15 hr
<img width="1037" height="366" alt="image" src="https://github.com/user-attachments/assets/7caafe6a-a66c-4d30-a9d9-e0d3e020938f" />

Seeing the schematic finally come together feels really satisfying and everything went extremely well this session. 

#### NOW  IT'S READY FOR THE PCB LAYOUT  , ( BUT FIRS I NEED SOME REST, MY BACK IS PAINING)

## Entry 3 — MAKING my PCB

##  Arranging the PCB
After assigning the footprints, I moved everything from the schematic into the PCB Editor. At first there were components everywhere with ratsnest lines connecting each other it was very confusing at first when I started arranging the components neatly on the PCB manually according to my Alice layout. So, first I placed the switches according to my Alice layout  because they were the most important parts. After that I arranged the OLED, Rotary encoder, Joystick, Micro controller ( Raspberry Pi Pico ) and the smaller components around them (stabilizer, mounting holes).
<img width="1073" height="465" alt="image" src="https://github.com/user-attachments/assets/7b749477-4d4e-48d5-9fdc-d83849447b36" />


## Routing the PCB :-

After arranging all the components on the PCB, I started working on routing the traces.
The ratsnest lines showed me which components still needed to be electrically connected. My goal was to route these connections while keeping the PCB neat and avoiding unnecessary overlaps.

#### Keyboard Matrix :-
So I first focused on the keyboard matrix connections, routing the traces between the switches and diodes. Since there were many connections it took me some time to get there.
Now for the Oled display, Joystick, RGB LEDs and Raspberry Pi Pico
After routing the matrix, I worked on the connections for the Oled display, Joystick, RGB LEDs and **Raspberry Pi Pico. **
OLED and Joystick were easy but the       RGB Leds took me a lot of time to complete

#### RGB LED Routing :-
The RGB LEDs required additional routing because each LED needed connections for power, ground, data input, and data output.
I connected the LEDs in sequence so that the RGB data signal could travel from one LED to the next.

#### Power and Ground :-
I paid extra attention to the power connections because the RGB LEDs can draw significantly more current than the other components.
I also had to think about the different power connections, especially the 5V, 3.3V, and l also kept the size of the power line (5v,3v3) a bit thicker 0.3 or 0.4 cause it prevents the melting of the copper
 If l am right
I tried to keep the power routing clean and make sure the traces had suitable paths 
And for the GND (Ground Plate) l did not connect it manually thanks to an friend l got to know if we add GND plate it will connect all the GND's all by itself, So that saved me some time rather than  doing it manually 
<img width="1056" height="447" alt="image" src="https://github.com/user-attachments/assets/4c08cdeb-8cc4-4430-9f74-943f243f5e17" />


- PCB Layers :-
- F.cu  (Red)
- B.cu (Blue)
- Vias (Dots kinda thing that lets u use both layers)
This made routing much easier,and thees are the layers l used  
Keyboard Matrix , Rgb , Joystick  , Display -} u can check out my file from folder called  PCB theres a file called PCB Editor downloadit and clear ur doubts

##### Routing All Connections To  Raspberry Pico PI :-
Well this was preety easy , l just need to route the  connections of Keyboard Matrix (Rows and Columns) , Rgb  to  there GPIO pins on the Pico Pi
( Joystick and OLED was already done) 

#### DRC Errors for PCB :-
After completing most of the routing, I ran the Design Rules Checker (DRC) in KiCad to look for problems such as:
Unconnected connections
Clearance violations
Overlapping or conflicting tracks

I then went back and fixed the errors that appeared It was no sweat just some text were intersecting with dome part and some layer like dots that l mistakenly added just delete those 
At this point, the PCB was starting to look GREAT 👍🏻 
<img width="662" height="524" alt="image" src="https://github.com/user-attachments/assets/9213d0af-47b2-4bdf-aa21-928f8f199b56" />

#### Next step: To add its shape

#### SHAPE OF THE PCB :-
Like this was preety much easy to just selected the layer Edge Cut and put lines accordingly to my reference pic at top , l can also just make it an rectangular box but i just chose that cause while l design my case it will give me an idea for the perimeter ig
And after that it was good to go 
3D (keycaps , hotswapp , display , Joystick )
I added there 3d models from GrabCAD so l can get a preety good look how my Keyboard going to look and it also helps me to know  how much height should be the walls (boarders) of the case. 
<img width="1061" height="474" alt="image" src="https://github.com/user-attachments/assets/87549082-058a-4c85-8c9d-9cad6780b664" />
###### *TOTAL HOURS FOR LAYOUT* :  18hr
####  Last look of the PCB
<img width="1050" height="480" alt="image" src="https://github.com/user-attachments/assets/faf2e541-6268-4f27-9ddd-df7d07e9a735" />
## Okay it's me after many  hours later (AGAIN) :- 
HOWDY FELAS!, I am here to proudly state that I have have FINISHED my PCB  after working Continuously on it well, HURRAY!
I am not gonna lie it took a lot lot lot of time bruh (MOST WITH THE GD ERROR) , I was about to quit but I am glad that I Didn't. Overall, everything went extremely well this session, and I’m really happy with how much progress I made. Completing the PCB feels like a big step forward for my keyboard project
Well , l am relieved and the last step is just to make an CASE for it 
Cant wait to finish it  and look how it turns out, supper dupper excited.      
SO LETS GET GOING ,BYE    

## Entry 3 — THE CASE
Well I got to pick a MOUNT first cause there's a lot,
                                                                                                                                       
<img width="1080" height="896" alt="image" src="https://github.com/user-attachments/assets/38117efe-1d2c-481f-8601-7db5a8cde2fd" />
                                                                                                                                      
I will go with The GASKET MOUNT cause it helps the switches to sound better while typing ig. What's the points of having an Mechanical Keyboard if u don't have the fell while typing , ANYWAYS, TO THE DESIGNIG PART 
 ### - DESIGNIG THE CASE :-
 For making the case I am using software called ____________  u may be familiar with it cause and I know some basics of it and also I am following the guide (DOCS) of HACKPAD just the CASE part
