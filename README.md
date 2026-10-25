# SALLEN KEY LOW PASS FILTER 793474
The goal of this project was to apply what ive learned over the past few months while studying the khan academy elec e course. But more than that, i wanted to try to create and debug a kind of analog circuit since that is the kind of thing i want to do in college. My focus with the project was to teach myself how to do something akin to an engineering project. Becasue of this, i chose easy resistors and capacitor values of 10 (units) so i could focus purely on design and making sure that the output of my circuit matched the projected value of the target cutoff frequency equations. The text below details the versions of the project and my process.
.
. 
.
My first version was just an attempt to get the basic filter design with my element values into the program and working. It did not work. The amplitude in dB for all componments was completely flat, meaning that the current simply wasnt flowing; if the current was flowing then the existence of the resistors and cutoff frequency of the op-amp would have surely created some kind of curve otherwise 
![Initiatal try](images/V1.note.png)
.
.
.
In my second version i had realized why the current wasnt flowing. My voltage sources had no ground, meaning that they werent connected to anything outside of the confines of the circuit. This of course creates the issue of where the current is supposed to go. The answer was originally nowhere and thus the circuit simply did not have flowing current. This second version had curves, so i knew that it was now doing something, but the amplitude (dB) graph was super far in the negative. I knoq from the math that the dB should be -6 at 1.6kHz, when in this version the dB was at -66 at 1.6 kHz. 
![Second try](images/V2.note.png)
.
.
.
In my third version i was able to get it to work, but i honestly didnt know why at first. I tried a few different things to get it to work. I tried making the cirucits current input and ouput into designated input and output ports in the LTspice interface thing. Adding the input completely messed up the graph is of all of my wires in a way that i dont understand, and adding the output did nothing. Cool. So i changed the input back into a ground and then tried to probe through the wires to see where the current was going before hitting the op-amp. this was fruitless as there where multiple points where the current diverged from the 0 line where it should have been. FInally i switched my more complicated op-amp with an ideal one that didnt feature power input and output pins, and this for some reason fixed everything. After looking online for a while i found out that it was because my non previous non-ideal op-amp was powered wrong, and because it was powered wrong, the C1 (which otherwise is supposed to push current back through the circuit) was just pushing the dB lower and lower as the kHz increased.
![Success](images/V3final.note.png)
