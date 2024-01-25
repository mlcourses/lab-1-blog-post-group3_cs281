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
![alt text](https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/20240118_135514.jpg) 

#### We can see green for Low:
![alt text](https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/20240118_135542.jpg) 
3. **Observation**: We observed that pins within the same column are electrically connected, sharing the same voltage. However, pins located in adjacent columns are not voltage-bearing by default. Conversely, by introducing electricity to any pin within a row—such as connecting it to a +5 Volt source—all pins in that same row become energized, carrying same voltage levels.


### Step 1: Building our first digital circuit

- Get two LEDs and two 330 Ohm resistors (or any other type of resistors). 
- We will wire the resistor to the GND side, and connect a wire to the +5V onto the breadboard. 
- The LED is direction dependent. In the LED there are two pins, with one longer than the other. The “long” end must be connected to the +5V (the same row with the wire connected to +5V) while the “short” end will be connected to the GND side (the same row with the resistor). 

#### One LED: 
![alt text](https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/20240118_140202.jpg) 

#### Two LEDs: 
![alt text](https://github.com/mlcourses/lab-1-blog-post-group3_cs281/blob/main/assets/20240118_140915.jpg) 

**Remember**, the current only flows in one direction through an LED, so the circuit will only operate if the LED is connected properly and correctly.

### Step 2: Using the function generator

Locate the function generator on the left side of your breadboard.

- Get one LED and repeat the steps from step 1, but this time, use a long wire. 
- Connect one end of this wire to one of the six non-TTL pins located below the function generator. 
- Then, connect the other end to the high (+5V) input of your LED circuit as the positive connection.
- After that, we will set the switch to a square wave, the top switch to 1, the other top switch to Hz.
- Then, we will “play” with the left and right sliders on the function generator to see how it impacts the frequency. 

[LED blinking using function generator](https://drive.google.com/file/d/1hobldXbfavqi0o4JsadhW_ytkaj0Q4Lk/view?usp=sharing)





## Testing

## Conclusion




