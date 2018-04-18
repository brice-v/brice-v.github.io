[Home](https://brice-v.github.io)

Projects
---

  1. [Safer Stoves](#safer-stoves)
  2. [Equalizer](#design-simulation-implementation-of-an-8-band-equalizer)
  3. [Audio Power Amplifier](#simulation-and-implementation-of-audio-power-amplifier)
  4. [8-bit Data Latch Memory Module](#8-bit-data-latch-memory-module)
  5. [Instruction Set Simulator](#instruction-set-simulator)
  6. [Web App with PSEG](#web-app-with-pseg)
 
---
### Safer Stoves

In my sophomore year of school, a group project tasked the students with building a device that would benefit the safety of an elderly population.

My group and I decided to make a device that would take the worry out of potentially having a kitchen fire. And so Safer Stoves was born!
This little device was made using an Arduino, as the brains, and a motion sensor combined with a gas valve / relay for the sensors.

The device had a display that could set the timer to the length of the cooking, and if the user was inattentive to their food, it would shut off the stove.

Safer Stoves made it to the top 10 of all the sophomore engineers!

### Design, Simulation, Implementation of an 8-Band Equalizer

Junior year in my Electronics Class, the students were all tasked of creating an equalizer of at least 4-bands that would span the human hearing frequency range (20Hz to 20kHz).  

My partner and I decided to design an 8-band equalizer using second order bandpass filters.  This meant that overall their would be less components per band and it would allow for easier implementation. (As well as being cheaper!)

The equalizer was designed using OrCAD PSpice and simulated using Allegro  Simulator.  Everything was made sure to be working properly and then all components were assembled onto a breadboard!

### Simulation and Implementation of Audio Power Amplifier

Sophomore year in my Electronic Circuit Analysis class, we were told to simulate and construct a given audio power amplifier circuit.  

The design was constructed within OrCAD PSpice and simulated using Allegro Simulator. We were all asked to find the crucial values that distinguish a good Audio Power Amplifier from a bad one such as it's frequency response, the distortion at different levels, and the power gain.

Then the circuit was constructed on a breadboard and tested thoroughly to ensure that it was working and amplifying the signal.  We learned a lot about how to handle heat that day!

### 8-bit Data Latch Memory Module

During my senior year in my System Design and Implementation class, we were tasked with designing a circuit that could be simulated, and later implemented onto a PCB.  The entire project was done within OrCAD PSpice and simulated using the Allegro AMS Simulator.  

The reason I chose to do a 8-bit Data Latch was primarily due to my interest in computer systems.  The 8-bit Data Latch was done using NAND gates and each bit was stored in its own D-Latch. Using the NAND gates furthered my understanding of the memory system complexity that is used in all of today's computers.  

When it was decided that the circuit was in functioning order the board was designed within OrCAD PCB editor on two layers and sent out for manufacturing.  

Finally when the board was delivered all of the components were soldered onto the board and testing could begin.  With the design their were DIP switches used to control the enable of the latch as well as input data to each bit.  Then LED's would display the binary value that was being stored within the module.  

With everything working the project was deemed a success.

[Link to my paper (PDF)](https://brice-v.github.io/docs/8bitdlatch_bv.pdf)

### Instruction Set Simulator

For my senior capstone project I am building a complete microcontroller from the ground up.  To start from the very beginning I would need an instruction set that could handle all the possible operations I would want to carry out while using the microcontroller.

Using an instruction set simulator(ISS) would ease the design of the actual microprocessor because all of the necessary registers and addressing modes could be figured out in a high level language that abstracted the complexities of the internal design.

The entire ISS was written in Python 3.  This was mostly due to the ease of use of programming and the benefit of using built in data structures to accomplish the tasked that would need to be done.  

This proved to be very successful and also allowed me to design the assembly syntax that would be used for the processor.  The code itself is currently now being used to convert the assembly language into machine readable code for the microprocessor that was built.

[Link to project](https://github.com/brice-v/InstructionSetSimulator)

### Web App with PSEG

During my internship over the summer I worked on a web application using Adobe ColdFusion.  This application was used to track the repairs and maintenance on parts in the field.

Overall the project as a whole taught me a lot about web programming and the use of databases in a work environment.

My knowledge of databases has furthered this year by taking a class specifically for the design of databases.
