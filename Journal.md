---
title: "PANDA-V2"
author: "Evan Le"
description: "Another, Foldable high-speed printer for hackathons"
created_at: "2025-07-30"
---

<img width="467" height="465" alt="image" src="https://github.com/user-attachments/assets/a5023d66-918e-47a1-ac26-c1803365f793" />

Total Hours: 25
# June 8th: Got the screen to work!

[actual journal content - what did you do?]

[insert pictures of what you're working on!]

**Total time spent: 2h**
## Day one (7/28/25) (5 Hours) ##

I began with sitting in my room, bored. I had no idea what to do. And then, my little sibling asks if i could 3d print something, a complex, flexidragon with many overhangs, bridges, and Print-In-Place parts, to which, I reply no. 
I explain that my infill printer simply did not have the capability required, as it lacked the cooling, the shapers, and the quality. He of course, called me a loser, which got me thinking. 
I decided that to keep on printing, I would need a better machine, yet I didn't want to lose the ability to take my printer anywhere, and I also did not want to sacrifice any speed or quality. 

### PANDA v1 ###

So, to produce a spiritual sucessor to this printer, let's talk about *why* i would develop a sucessor, and what I would need to change. 
#### Resonances ####

PANDA v1 was fast. Groundbreakingly fast at producing prototypes and "functional" prints. Capable of 70,000 mm/s acceleration at a movement speed at 900mm/s, it was great for hackathons. Simple parts,
Simple prints came out quickly and in a timely manner.
One of it's major problems is the resonances however. The CoreXZ motion system enacts an extreme amount of torque in the Y direction, on the TOOLHEAD. That means, Input shaper is completely INCAPABLE of canceling it out as the toolhead is incapable of moving in the Y-direction, meaning that a massive amount of ringing, smoothing, and resonation slips through the cracks as the shaper desperately tries to compensate for a frequency/direction it will never come close to even fixing.
That's why, PANDA v2's frame must be designed stiff, with a focus on eliminating non-compensatable toolhead motion. 

#### The toolhead ####

PANDA v1 was somewhat reliable, though I made several insanely large mistakes when considering the hardware chosen. The e3d volcano was a terrible choice, even if it was 5 bucks off of aliexpress. It did however push enough flowrates for the time being. Another problem, is the EDDY probe. The eddy probe is incredibly sensitive to enviromental factors such as magnetic interference, temperature drifts, and more. At a hackathon with god knows how much hardware, or moving on the go, even things like the earth's magnetic fields can shift and the weather can change, meaning that every place I took panda, I would have to recalibrate the probe. 
PANDA v2 must be designed with a probe that relies on a much less sensitive medium of measurement. Some good examples are strain gauges, optical switches, and microswitches. The problem is, strain gauges are relatively proprietary and require some sort of compliance. In a COREXY machine, this can be put in the bed. However when it comes to a bedslinger meant to print with extreme amounts of speeds and accels, any sort of compliance is completely unacceptable. Same thing with toolheads like voron TAP. They're heavy, and compliant. The next choice is a touch probe, such as a CRtouch or Microprobe. 
The toolhead also lacked cooling. In most printers, 2 5020s is way overkill, however I sourced low performance ones, and even then, at 600+ mm/s in common materials like PLA, cooling is a massive requirement. 

#### The motion system ####

PANDA v1's corexz system enacted a huge amount of torsion that was unisolated in an optimal way and also contributed to the wobbling of the cantilevered beam. It also was powered by weaker drivers like tmc 2209 and at a measly 24v.
PANDA v2 will adopt a cartesian motion system, sponsored by LDO 2504/or2804 motors running at 60V. It also adopts double shear and an AWD Y axis to improve shaper scaling and increase the window of performance panda V2 will be able push.
This machine will also be constructed out of polymaker PET-CF17 as it is incredibly stiff and can withstand the motor operating temperatures. 

## Day Two (7/30/25) (10 Hours) ##

With all of this in mind, i got to work. 

<img width="994" height="983" alt="image" src="https://github.com/user-attachments/assets/7dd1949b-8bfb-44d2-99a6-9d8905a8f4e4" />

I constructed the frame to adopt much stiffer 4040 Extrusions to reduce the amount of resonation and it's propogation
The Z axis was designed with 2 MGN9H rails to reduce slop and increase the translation of any torque into panda v2's incredibly stiffer frame. It still retain's panda v1's belted nature.
The Y axis was designed based off of the LH stinger and the Kevender. It adopts an AWD system and double shear prevent resonation. 
There's also a nifty little handle in the Z tensioner to make PANDA v2 easier to carry around. 

## Day Three (7/31/25) (10 Hours) ##

The final day. 
<img width="1201" height="576" alt="image" src="https://github.com/user-attachments/assets/a5f04bd6-238e-4bdc-a06f-fb4195a93bbb" />

Due to strain issues on the X axis, I cannot make it AWD, however shaper behaviour at AWD performance in the toolhead will likely be unacceptable.
The Toolhead is a much cleaner design and adopts protoXtruder, a lightweight, yet HGX lite based extruder as I still firmly stand by the advantage of large gears when it comes to grip on filaments like TPU. 
The X axis is going to be made out of 2, 5mm CNC steel parts to increase rigidity and reduce torsion. 
The toolhead also adopts a CPAP to both increase airflow and reduce weight on the toolhead.

<img width="666" height="522" alt="image" src="https://github.com/user-attachments/assets/df8c3de6-954e-48d0-a7cf-1b6e080a1355" />

As you can see, I'm using a biqu Microprobe and a lancer standard hotend. The ducts are optimized both to provide direct and sheetcooling. 

