# Week 1 - Counter

## Task 1 - Simulating a basic 8-bit binary counter

The following waveforms were observed when simulating the counter:
<img width="954" alt="image" src="https://user-images.githubusercontent.com/107804218/196924562-cec689aa-e295-49a9-a285-f2d2639c5de7.png">

#### Challenge 1 - Stopping the counter at 0x09 for 3 cycles
The following waveforms were observed when changing the reset and enable flags:
<img width="631" alt="Screenshot 2022-10-20 at 14 56 03" src="https://user-images.githubusercontent.com/107804218/196968758-7343c1ae-e066-45cb-85a5-4edab94679b6.png">

To do this, the en flag was set to low for two cycles as they are only computed in the next cycle, resulting in the count stopping for three cycles.

#### Challenge 2 - Implementing an asynchronous reset
The following waveforms were observed when changing the reset flag to be recognised asynchronously:
<img width="875" alt="image" src="https://user-images.githubusercontent.com/107804218/196978499-641f22fd-702f-4220-b88b-6b9937b5f20f.png">

From the above image, it can be seen that the counter resets immediately when a reset signal is sent.

## Task 2 - Linking Verilator simulation with Vbuddy

#### Observations when first linked: 
- Not counting, reason: incorrected code.
- Worked once corrected

#### Linking rotary encode push button
- Works - vbdFlag() is now a stimulus to the counter.

#### Test Yourself - Modifying the counter to count up when vbdFlag() is 1, and down when it is 0.
To complete this task, I changed the behaviour of the en signal, and the following else statement was changed in the counter code from:
```else     count <= count + {{WIDTH-1{1'b0}}, en};```  
...to:  
```else count <= count + {{WIDTH-1{1'b0}}, en} - {{WIDTH-1{1'b0}}, !en};```  
What this essentially does is count up when en is 1, and down when en is 0.

## Task 3 - Vbuddy parameter & flag in one-shot mode
#### Step 1
- Changed counter to have inputs ```ld``` and ```v```, being the load parameter and value repsectively.
- Changed the testbench to set ```ld``` equal to the ```vbdFlag()``` and ```v``` equal to the ```vbdValue()```.

Observations:
- The counter was set to the value of the EC-11 rotary encoder when it was pressed.





