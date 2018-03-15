---
layout: post
title: "Bike Light"
description: "In this special workshop for Bike Week, participants will learn to program, assemble, and solder their own custom made LED bike light. This hands-on session will be an opportunity to learn how to build an interactive circuit from scratch using an ATtiny85 and Neopixel LEDs. The workshop focuses on building skills in hardware, software, and fabrication.
"
date: 2018-03-14
permalink: /bike-light
---

**Workshop by Arielle Hein** <br>
Thursday, March 15th 2018

**BLDG61 Electronics Workshop**<br>
Boulder, Colorado


<hr>

In this special workshop for Bike Week, participants will learn to program, assemble, and solder their own custom made LED bike light. This hands-on session will be an opportunity to learn how to build an interactive circuit from scratch using an ATtiny85 and Neopixel LEDs. The workshop focuses on building skills in hardware, software, and fabrication.

<br>

## Programming the ATtiny85



<br>

## Assembly Instructions

#### **Step 1: Add DIP Socket**

The DIP Socket will hold our 8-pin ATtiny chip, we'll add it to the circuit once everything has been soldered. Be sure to position the socket so that the notch at the top is closest to the end of the prototyping board.

![step 1](images/step1-1.png "Add DIP Socket")

<br>
#### **Step 2: Add 2 Resistors**

You will be adding 2 resistors, one is 470Ω for the neopixel strip and connects to pin 2 on the ATtiny. The other is 10KΩ and connects between pin 1 (reset) and pin 8 (5V) on the ATtiny.

Trim the leads ***after*** soldering them to the board. 

![step 2-1](images/step2-1.jpg "Add 470 ohm")

![step 2-2](images/step2-2.jpg "Add 10K ohm")

![step 2-3](images/step2-3.jpg "Add 10K ohm")

<br>
#### **Step 3: Add Capacitor**

Next, add a 100uF capacitor between pin 4 (GND) and pin 8 (5V) of the ATtiny. Bending the leads 90 degrees allows the capacitor to lay flat against the board.

![step 3-1](images/step3-1.png "Bend the cap")

![step 3-2](images/step3-2.png "Capacitor")

![step 3-3](images/step3-3.png "Capacitor")

![step 3-4](images/step3-4.png "Cap position")

![step 3-5](images/step3-5.jpg "Bend the cap")

<br>
#### **Step 4: Add Battery Holder**

Add the battery holder. Be sure to position it so that the positive side of the battery holder is on the same side of the board as ATtiny pins 5,6,7,8. Solder the battery on the back of the board. You will also add a wire connecting the ground pin of the battery holder to pin 4 (GND) on the ATtiny.

![step 4-1](images/step4-1.jpg "Position battery holder")

![step 4-2](images/step4-2.jpg "Solder battery to ground")
