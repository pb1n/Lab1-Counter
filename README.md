# Week 1 - Counter

## Task 1 - Simulating a basic 8-bit binary counter

The following waveforms were observed when simulating the counter:
<img width="954" alt="image" src="https://user-images.githubusercontent.com/107804218/196924562-cec689aa-e295-49a9-a285-f2d2639c5de7.png">

At first, the waveform is 
*Write up to follow -- see Goodnotes waveform annotation*

#### Challenge 1 - Stopping the counter at 0x09 for 3 cycles
The following waveforms were observed when changing the reset and enable flags:
<img width="631" alt="Screenshot 2022-10-20 at 14 56 03" src="https://user-images.githubusercontent.com/107804218/196968758-7343c1ae-e066-45cb-85a5-4edab94679b6.png">

*Write up to follow -- had to see that 2 cycles does the trick and that when flags are set to high they are only computed in the next cycle.*

#### Challenge 2 - Implementing an asynchronous reset
The following waveforms were observed when changing the reset flag to be recognised asynchronously:
<img width="875" alt="image" src="https://user-images.githubusercontent.com/107804218/196978499-641f22fd-702f-4220-b88b-6b9937b5f20f.png">

## Task 2 - Linking Verilator simulation with Vbuddy

#### Observations when first linked: 
Not counting, reason: incorrected code.
Worked once corrected

#### Linking rotary encode push button
Worked. vbdFlag() is now a stimulus to the counter.

## Task 3 - Vbuddy parameter & flag in one-shot mode

