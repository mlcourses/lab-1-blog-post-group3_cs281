# Lab 01 : Doing stuff with hardware - A Beginner's Guide to Building and Controlling Digital Circuits

## Overview and Motivation

In this lab, we will explore the environment that we will use for the hardware lab sequence of the course. We will learn about the PB-503 breadboard prototyping stations and about the Arduino, a microcontroller system for supporting embedded processor control. We will start by exploring the features of the breadboard and then will integrate the use of the Arduino with the breadboard. By the end, you'll have hands-on experience with a breadboard, LEDs, and the Arduino, learning how these elements can be combined to create simple but powerful systems.


## Materials 

-  PB-503
-  LED'S
-  Wires
-  330 Ohm transistor 
-  Arduino kit
-  Arduino controller with the USB adapter
-  computer for the Arduino IDE
-  7404 chip
-  7408 chip g 


## Project Steps

### Breadboard Basics

We start with a PB-503 breadboard prototyping station and an Arduino kit. 
- **Understanding the PB-503**: This integrated device includes switches, LEDs, power supplies, and a function generator, all centered around a breadboard.
- **Power Supply**: The PB-503 is equipped with a +5 Volt power supply located in the upper right corner. This is the only power supply we'll use, as our circuits are designed for 5 volts. Remember, never connect to any voltage other than +5 Volts to avoid damaging your circuits.
  - **Terms for +5v**: high, hot, on, 1, Vcc.
  - **Terms for Ground**: 0 (volts), low, off, 0 (logic 0), GND.
  - In Boolean algebra, +5 is TRUE, and Ground is FALSE.

- **Safety First**: Always turn off the breadboard's power before constructing or modifying circuits to prevent damage. 

### Exploring the Breadboard

1. **Initial Stage**: First, we initiate our breadboard setup by connecting a red wire from the power supply (+5V) to the topmost row, and a black wire from the ground to the second row from the top on the breadboard.
2. **Logic Indicators**: We used the onboard Logic Indicators (eight on the right-hand side) to test for HIGH or LOW voltage across the board. Connecting a wire from a point on the breadboard to a Logic Indicator shows red for +5V (HIGH) and green for Ground (LOW).

#### We can see red for High:
<img src="https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/20240118_135514.jpg" alt="alt text" width="450"/>

#### We can see green for Low:
<img src="https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/20240118_135542.jpg" alt="alt text" width="450"/>

3. **Observations**: We observed that pins within the same column are electrically connected, sharing the same voltage. However, pins located in adjacent columns are not voltage-bearing by default. Conversely, by introducing electricity to any pin within a row—such as connecting it to a +5 Volt source—all pins in that same row become energized, carrying same voltage levels.


### Step 1: Building our first digital circuit

- Get two LEDs and two 330 Ohm resistors (or any other type of resistors). 
- We will wire the resistor to the GND side, and connect a wire to the +5V onto the breadboard. 
- The LED is direction dependent. In the LED there are two pins, with one longer than the other. The “long” end must be connected to the +5V (the same row with the wire connected to +5V) while the “short” end will be connected to the GND side (the same row with the resistor). 

#### One LED: 
<img src="https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/20240118_140202.jpg" alt="alt text" width="450"/>

**Remember**, the current only flows in one direction through an LED, so the circuit will only operate if the LED is connected properly and correctly.

### Step 2: Using the function generator

Locate the function generator on the left side of your breadboard.

- Get one LED and repeat the steps from step 1, but this time, use a long wire. 
- Connect one end of this wire to one of the six non-TTL pins located below the function generator. 
- Then, connect the other end to the high (+5V) input of your LED circuit as the positive connection.
- After that, we will set the switch to a square wave, the top switch to 1, the other top switch to Hz.
- Then, we will “play” with the left and right sliders on the function generator to see how it impacts the frequency. 

[LED blinking using function generator](https://drive.google.com/file/d/1hobldXbfavqi0o4JsadhW_ytkaj0Q4Lk/view?usp=sharing)

### Step 3: Using the 7404 chip - the NOT logic gate

- Obtain a 7404 IC and examine the data sheet for the 7404 inverter. Place your inverter so that it spans one of the troughs on the breadboard.  

#### It looks like this
<img src="https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/Not_gate.png" alt="alt text" width="450"/>

- By examining the data sheet, you will notice that the right hand corner is to be connected to Vcc or +5V and the lower left corner is to be connected to GND i.e. you need to place the chip so that the pin on the upper right hand corner is on the same row connected to +5V while the pin on the lower left hand corner is on the same row connected to GND.
- The IC has six inverters, organized into input/output pairs. We will be using pins 1 and 2 which are 1A and 1Y respectively (1A is input 1 and 1Y is output 1). It doesn’t matter which pins are used as long as they are of the same pair.
- The input should come from the function generator, so the wire should be connected from the function generator onto the same row of pin 1A. On this same row, connect another wire to one of the logic probe LEDs on the top right of your breadboard.
- The output will be connected to another logic probe. Make sure the switch on the logic probe is at +5. 
- The logic probes are each a pair of LEDs that will light up high or low depending on the signal connected to it. One probe is wired to show the input to the 7404 inverter and the other to its output.

[Testing with NOT gate](https://drive.google.com/file/d/1ho4uJNYNZBxblJtPAvjG2H1vwuKb77kp/view?usp=sharing) 

### Step 4: Using the 7408 chip - the AND logic gate

- Obtain a 7408 IC and examine the data sheet for the 7408 chip. We will place this chip so that it spans one of the troughs on the breadboard.

#### It looks like this
<img src="https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/AND_gate.png" alt="alt text" width="450"/>

- Similar to the 7404 inverter, the right hand corner is to be connected to Vcc or +5V and the lower left corner is to be connected to GND
- Since the chip is built in a way that it has two inputs and then output, we will have two wires from the logic switches that will be connected into the input pins.
- Then we will have another wire connected to the logic probe from the 7408 chip’s output pin. 
- This step examines the AND logic gate. 

[Testing with AND gate](https://drive.google.com/file/d/1hgFkk98tifWOTf-YGGIOQmUQYs7ThiY-/view?usp=sharing) 

### Step 5: Using the Arduino controller 

- Using a laptop, go to the website www.arduino.cc/en/software to download the Arduino IDE.

- Using the USB adapter, connect the Arduino to your laptop. Start the Arduino IDE.

- Create a new “sketch” and save it as “Lab 1”. Type in the following code:

```c
const int P = 13;
const int A = 1000;
const int B = 1000;

void setup() {
  pinMode(P, OUTPUT);
}

void loop() {
  digitalWrite(P, HIGH);
  delay(A);
  digitalWrite(P, LOW);
  delay(B);
}
```

- Code explanation: 

  - Variable `P` is responsible for holding the value of the port number on the Arduino. The value must match the port we will be using. In this case, we will be using port 13, so our P is going to be 13, holding constant.

  - Variables `A` and `B` are the tick delay in milliseconds.

  - The setup() function is setting the output to the port we chose for `P`, in this case, port 13.

  - The loop() function is a loop alternating between true and false (HIGH and LOW) and outputting it to port `P`. Each output is accompanied by a 1-second or 1000-millisecond delay.

- After finishing writing the code, hit the “verify” button to compile your code and check that it is syntactically correct. If everything is correct, hit the “upload” button on the IDE to load your program to the Arduino. It will recompile your sketch and then connect to the Arduino. You should notice some of the lights on the Arduino blink rapidly as it is receiving data from the laptop.

- Before we move forward, here are some things you should know about wiring and powering Arduinos:

  - The Arduino can be powered in 3 ways: Connecting to the laptop, connecting to the breadboard, or connecting to the battery.

  - For the sake of convenience, we will keep the Arduino connected to the laptop instead of unplugging it.

  - If you want your Arduino to be mobile, you must use the battery.

  - Once you download a program to the Arduino, it stays there in the flash memory. You will not lose the program if the Arduino loses power.

  - Wire pin 13 on the Arduino to the first input pin on the AND gate from the previous step and replace the input from the first switch. The second AND input should remain connected with the second switch.

  - Wire GND from the breadboard to GND on the Arduino. You can use any of the GND pins on the Arduino. This step is necessary so that Ground on the Arduino is at the same voltage as Ground on the breadboard.

  - Make sure that the second switch (the one still connected to the IC) is set to high.

  - Turn the switch back on, you can experiment with your program by changing the values of `A` and `B`.

  [Testing with Arduino Control](https://drive.google.com/file/d/1heHwvtChfNHoktCQ_a65qY_GDRveShxH/view?usp=sharing)


## Testing

**For the first step:** After following the instructions for building our first digital circuit to light a LED, we turned on the breadboard and found out that the red light is lit, which means the process was correct. 

#### Testing two LEDs: 
<img src="https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/20240118_140915.jpg" alt="alt text" width="350"/>

**For the second step:** After following the instructions for using the function generator, we found out that the function generator is alternating between true (high) and false (low) in such a way that the LED light is blinking in accordance with the frequency of the freq slider. The higher the slider, the faster the light blinks. In addition, we found out that the AMP slider changes the brightness of the LED in such a way that the higher it is the brighter the LED.

https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/20240118_143326.mp4


**For the third step:** After following the instructions for using the 7404 chip, the NOT logic gate, we found out that the out that the function generator is alternating between true (high) and false (low) in such a way that the logic probe’s light of the input is changing and switching output (low to high, high to low). The second logic probe (connected to the output) is also alternating between high and low, however, it is not the same as the first logic probe e.g if the 1st logic probe is high then the 2nd logic probe is low, and vice versa. This occurs because we are using the inverter as the NOT logic gate, so inputs from the function generator will be inverted, thus leading to the two logic probes not showing the same lights together. 

**For the fourth step:** After following the instructions for Using the 7408 chip - the AND gate, we found out that when the two logic switches are on, the red light turns on (true). In the other cases where either one of the switches is off or both of them are off, the green light turns on (false). By that, we know that this step operates correctly the AND logic gate. 

**For the fifth step:** After following the instructions for using the Arduino controller, we witnessed to the fact that the Arduino controller looping on the inputs with True and False, making the output to be either False (when the switch is off) or alternating between True and False (when the switch is on). That result is indicating that the step operates correctly since it follows the AND gate: when the switch is off, no matter what happens with p, the whole output is false, and when the switch is on, the output is alternating between true and false since that’s how the program loops on the inputs.


## Conclusion




