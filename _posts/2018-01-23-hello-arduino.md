---
layout: post
title: "Hello Arduino"
description: "This workshop introduces the the basics of physical computing: using a microcontroller to sense and respond to the physical world. We will utilize the Sparkfun Redboard to explore the relationship between software, hardware and human interaction. Together we will walk through the process of building a circuit and programming it to read sensor values and control LEDs. You will leave with a clear understanding of how to get started working with Arduino to build interactive hardware projects."
date: 2018-01-24
permalink: /hello-arduino
---

**Workshop by Arielle Hein** <br>
Thursday, January 25th 2018

**BLDG61 Workshop**<br>
Boulder, Colorado

## History & Context
Arduino is an open-source electronics platform based on easy-to-use hardware and software. Arduino boards are able to read **inputs** - light on a sensor, a finger on a button, or a Twitter message - and turn it into an **output** - activating a motor, turning on an LED, publishing something online. You can tell your board what to do by sending a set of instructions to the microcontroller on the board. To do this, you use the [Arduino programming language](https://www.arduino.cc/en/Reference/HomePage), and the [Arduino Software (IDE)](https://www.arduino.cc/en/Main/Software), based on [Processing](https://processing.org/). Read more about Arduino [here](https://www.arduino.cc/en/Guide/Introduction).

[Watch](https://www.youtube.com/watch?v=UoBUXOOdLXY) Massimo Banzi, co-founder of Arduino, explain this easy-to-use open-source microcontroller that's inspired thousands of people around the world to make the coolest things they can imagine -- from toys to satellite gear.

When I talk about Arduino, I think of it in three different ways. First, Arduino is a piece of the **hardware**. There is a line of Arduino boards that can be used as the brains of a project. Second, Arduino is a **programming language** and development environment that makes working with inputs and outputs extremely accessible. Finally, Arduino is a **community** of engineers, artists, designers and makers of all types. The vibrant community is partly what makes Arduino so special.

<!-- ## Example Projects
+ Jen Lewin, [Sidewalk Harp](https://www.youtube.com/watch?v=jXBtkfPY2D0 )
+ Danny Rozin, [Wooden Mirror](https://vimeo.com/101408845)
+ Yingjie Bei and Yifan Hu, [Moon Phases](http://www.yingjiebei.com/Moon-Phases)
+ Rebecca Leiberman and Nick Bratton, [RootNote](https://www.rebeccalieberman.com/root-note/)
+ Ella Dagan, [The Coatroom](https://www.elladagan.com/the-cloakroom)
+ Jingwen Zhu, [Heart on my dress](http://www.jingwen-zhu.com/#/my-heart-on-my-dress/)
+ Simone Giertz, [Useless Robots](https://www.youtube.com/watch?v=UlP4Z_pWhKo)
+ [Opentrons](https://www.kickstarter.com/projects/932664050/opentrons-open-source-rapid-prototyping-for-biolog)

<br> -->

## Setup & Resources
In this workshop, we will get up and running with the basics of Arduino. If you want to learn more about physical computing on your own time, here are several helpful links to get you going.

### Helpful Resources
+ The [ITP Physical Computing Blog](https://itp.nyu.edu/physcomp) is packed with labs, write-ups, videos, and tutorials for everything p-comp (incluing both electronics and programming).
+ The [Physical Computing Videos](https://itp.nyu.edu/physcomp/videos/videos-digital-and-analog-input-and-output/) from the brilliant folks at ITP are especially helpful for beginners.
+ Both [Adafruit](https://www.adafruit.com/) and [Sparkfun]() have huge collections of tutorials and resources on their websites. Both have Learn and Blog sections that feature projects and examples. [Instructables](https://www.instructables.com/) is another place to check for Arduino project guides.
+ [Electronics Club](https://electronicsclub.info/) is a site written by beginners but used my many as a reference for anyone wishing to learn about electronics or build simple projects.
+ [Adafruit's Guide to Soldering](https://learn.adafruit.com/adafruit-guide-excellent-soldering) is very helpful for fabrication things!

### Workshop Components
+ [Sparkfun Redboard](https://www.sparkfun.com/products/13975) or [Arduino Uno](https://www.sparkfun.com/products/11021) and USB
+ [Breadboard](https://www.sparkfun.com/products/12002)
+ [Jumper Wires](https://www.amazon.com/Solderless-Flexible-Breadboard-Jumper-100pcs/dp/B005TZJ0AM/ref=sr_1_5?ie=UTF8&qid=1516833877&sr=8-5&keywords=jumper+wires)
+ [Momentary push button](https://www.sparkfun.com/products/9190)
+ [LEDs](https://www.sparkfun.com/products/12062)
+ [Resistors](https://www.sparkfun.com/products/10969) (we'll be using 220ohm and 10Kohm)
+ [Potentiometer](https://www.sparkfun.com/products/9939)
+ Other variable resistors ([photocell](https://www.sparkfun.com/products/9088), [fsr](https://www.sparkfun.com/products/9376), [flex sensor](https://www.sparkfun.com/products/10264), etc..) - *optional*

<br>

Another great option if you are starting out with physical computing would be to purchase the [Sparkfun Inventor's Kit](https://www.sparkfun.com/products/14265), that kit includes parts for everything we're doing in this workshop.

## Hardware Setup
Today, we are using the Sparkfun Redboard, which is Sparkfun's equivalent of the Arduino Uno. Read more about the [Arduino Uno vs. Redboard here](https://learn.sparkfun.com/tutorials/redboard-vs-uno?_ga=2.63984172.2074834900.1509591674-603825142.1485451985).

![redboard](images/redboard.png "Sparkfun Redboard")

We will be building our circuit on a **breadboard**. A breadboard is a helpful tool for prototyping circuits without the need for soldering. It's a bit abstract at first, but once you understand the structure, it makes building circuits simple and fast! Sparkfun has an extremely helpful, more in-depth tutorial on [How to use a breadboard](https://learn.sparkfun.com/tutorials/how-to-use-a-breadboard).

![breadboard](images/breadboard.jpg "Prototyping Breadboard")

Before beginning any project, the first thing we want to do is setup our breadboard so that it is live with power and ground.

Use Jumper Wires to connect 5V on your Redboard to the red rail on the breadboard, and connect GND to the black rail. Then connect the red rails on your board to each other, also connect the blacks - this allows us to utilize both sides of the breadboard. Your setup will look like this:

![breadboard-setup](images/breadboardsetup.png "Breadboard Setup")

Next, we'll get set up with the programming environment, them we'll return to building our circuit.

## The Arduino Programming Environment

### The Arduino IDE
Visit the [Arduino Software Page](https://www.arduino.cc/en/Main/Software) and find the link to Download the Arduino IDE. Download and install for your specific platform.

![arduino](images/arduinoIDE.png "Arduino IDE")

+ **Compile** - is used to compile your code before uploading to the board.
+ **Upload** - transfers your program to the mircocontroller. Once the upload is complete, you will receive feedback in the bottom of the window.
+ **setup()** - this functions executes once when your program starts.
+ **loop()** - this runs continually as long as your program is running. this is where you will read and write data.
+ **serial mintor** - useful for debugging, reading sensor values, and for sending and receiving serial data. in order to use the serial monitor, you must initialize serial communication in the setup function.

### Test Upload to the Board
Before we start writing our own code, let's make sure that we are able to upload code to our board. We'll use the **Blink Example**.

Built into the Arduino IDE is a large collection example code. To access this, click **File > Examples**. Choose **01.Basics** and inside that is an option for **Blink**.

![examples](images/examples.png "Arduino Examples")

You don't need to edit this code at all, we just need to select our board and port. Be sure that your Redboard is connected to your computer via USB, then go to **Tools > Board** and confirm that **Arduino Uno/Genuino** is selected. Next go to **Tools > Port** and select whichever port your Redboard is connected to (on Windows it will be COM... on MAC it will be usbmodem...).

![board and port](images/board-port.png "Board and Port")

## Inputs and Outputs
Inputs are our **sensors** - components that read a signal from the physical world and translate that into something that our microcontroller or computer can read. There are two kinds of inputs that we use with Arduino: *digital* and *analog*.

Outputs are our **actuators** - these components take electricity and turn it into another form of energy such as light, sound, movement, etcetera. Outputs also fall into two categories, digital and *"analog"* (we'll talk about *"analog"* output more later on).

### Digital Inputs
A digital input has a discreet number of possible inputs. In the world of Arduino, a digital input has a value of either 0 or 1. We will use a momentary push button to demonstrate this. The button has two possible states, on and off.

To read a digital input, we use the Arduino function [`digitalRead()`](https://www.arduino.cc/en/Reference/DigitalRead)

### Digital Outputs
Like inputs, digital outputs have a finite number of possible values. In the context of Arduino, the signal will be either on or off. A good example of this would be turning an LED on or off. To program a digital output, use the function [`digitalWrite()`](https://www.arduino.cc/en/Reference/DigitalWrite). You can pass the `digitalWrite()` function a value of 0 or 1, or also the word HIGH or LOW.

### Analog Inputs
An analog input has an infinite number of possible input values within a particular range. Analog inputs represent changing voltages. When we're using Arduino, we're working with a 5V system, so an incoming analog sensor can offer any possible value between 0V and 5V. A slider is a good example of an analog input.

The Arduino Uno and Sparkfun Redboard, the boards that we are using, are inherently digital. So these boards include a component called an *Analog-to-Digital Converter* (or ADC) that allow us to read incoming analog signals. The Arduino uses a 10-bit ADC, which means that we will receive incoming analog sensor values between 0-1023.

To read an analog input, we use the Arduino function [`analogRead()`](https://www.arduino.cc/en/Reference/AnalogRead)

### Analog Outputs
Because our microcontroller is inherently digital (it operates on discreet signals), it cannot output a true analog voltage. Fortunately, there is a technique that we can use to 'fake' it, and produce a pseudo-analog output. The principle is called PWM, and you can read more about it [here](https://learn.sparkfun.com/tutorials/pulse-width-modulation). PWM is very useful if we want to dim an LED, or if we wanted to move a servo motor. The range of possible values that we can output using PWM is limited to an 8-bit number, which means a range of 0-255.

To use PWM, you must use a pin on your microcontroller that is marked with a this sympol `~`. This includes pins 3, 5, 6, 9, 10, and 11. To use PWM, use the function [`analogWrite()`](https://www.arduino.cc/en/Reference/AnalogWrite)


## Workshop Circuits

### Digital In / Out
We are going to start by building a circuit with a digital input (button) and digital outputs (LEDs).

Connect a momentary pushbutton to digital pin 2. You must use a 10Kohm pulldown resistor with your switch to provide a reference to ground. Connect an LED to digital pin 3 and another to digital pin 4, both LEDs need a current limiting resistor around 200ohm.

Here is the circuit:

![digitalio](images/digital_io.png "Digital I/O")

Next, we need to program the microcontroller. In this example we will use conditional statements with the switch to toggle which LED is illuminated. Here is the finished Arduino code.

<br>

<pre>
// constants won't change
// these are used to set pin numbers
const int buttonPin = 2;       // the number of the pushbutton pin
const int redLedPin =  3;      // the pin number of red led
const int yellowLedPin = 4;    // the pin number of yellow led

// variables will change:
int buttonState = 0;         // variable for reading the pushbutton status

void setup() {
  // initialize the LED pins as an output:
  pinMode(redLedPin, OUTPUT);
  pinMode(yellowLedPin, OUTPUT);

  // initialize the pushbutton pin as an input:
  pinMode(buttonPin, INPUT);
}

void loop() {
  // read the state of the pushbutton value:
  buttonState = digitalRead(buttonPin);

  // check if the pushbutton is pressed.
  // if it is, the buttonState is HIGH:
  if (buttonState == HIGH) {
    // turn red on and yellow off
    digitalWrite(redLedPin, HIGH);
    digitalWrite(yellowLedPin, LOW);
  } else {
    // turn red off and yellow on
    digitalWrite(redLedPin, LOW);
    digitalWrite(yellowLedPin, HIGH);
  }
}
</pre>

<br>

Upload your code to the board and test it out!


<div class="emph">

<h3>The Serial Monitor</h3>
<p>It is extremely helpful to be able to print the sensor values we're receiving, so that we can test if things are working and so that we can figure out what kind of sensor values we're able to work with. The <strong>Serial Monitor</strong> is helpful for this.</p>

<p>In order to use the Serial Monitor, we first need to initialize serial communication. Do that by adding the following line in your setup function:</p>

<p><span class="code">Serial.begin(9600)</span></p>

<p>Then, after you have read your sensor value, you can print that to the serial monitor, using <a href="https://www.arduino.cc/en/Serial/Println"><span class="code">Serial.println()</span></a>. If you would like to print multiple values, you may find it useful to format your message using <a href="https://www.arduino.cc/en/Serial/Print"><span class="code">Serial.print()</span></a> which does not print your message on a new line.</p>

</div>


### Analog In/Out
Next, we'll explore analog sensors! These input a range of values between 0-1023.

Here is the wiring for a potentiometer, with the middle signal wire connected to pin A0.

![potentiometer](images/potentiometer.png "Potentiometer wiring")

Here is the wiring for connecting an FSR (pressure sensor) to A1. This is the same wiring setup you would use for a photoresistor, or other analog input with two leads. You must use a pulldown resistor that provides a reference to ground, use 10kOhm resistor here.

![fsr](images/fsr.png "FSR wiring")

The first thing we need to do whenever we connect an analog sensor is to determine our range of values that our sensor is reading. We will use the serial monitor to do this. Here is the code for reading an analog input and printing the value to the serial monitor.

<br>


<pre>
int sensorPin = A0;    // select the input pin for the potentiometer
int sensorValue = 0;   // variable to store the value coming from the sensor

void setup() {
  Serial.begin(9600); // initialize serial communication
}

void loop() {
  // read the value from the sensor:
  sensorValue = analogRead(sensorPin);

  //print the value to the serial monitor so that we can see it
  Serial.println(sensorValue);
}

</pre>

Upload the code to your board and determine what range of values you're receiving. A potentiometer should give a full resolution (0-1023), while other sensors may give a smaller range of values.

Next, we'll use our analog sensor to change the brightness of our LED.

**One important thing to note:**

<span class="bright">Analog input reads a range between **0-1023** but analog output reads a range between **0-255**. </span>

So, if we want to use our analog input value to determine the brightness of our LED (an analog output), then we need to condense the range. Arduino has a very helpful function for this, called [`map()`](https://www.arduino.cc/reference/en/language/functions/math/map/). The `map()` function takes one range of values and converts it to a different range of values.


### Putting It All Together

Now, let's set up our circuit to change the brightness of the LEDs based on the analog sensor value, while also using the button to toggle which LED is on or off.

Here is the circuit:

![putting it together](images/everything.png "Puttin git together")

Here is the code:

<pre>
int sensorPin = A0;    // select the input pin for the potentiometer
int sensorValue = 0;  // variable to store the value coming from the sensor

const int buttonPin = 2;       // the number of the pushbutton pin
const int redLedPin =  3;      // the pin number of red led
const int yellowLedPin = 5;    // the pin number of yellow led

int brightness; //variable for led brightness

void setup() {
  Serial.begin(9600);

  // initialize the LED pins as an output:
  pinMode(redLedPin, OUTPUT);
  pinMode(yellowLedPin, OUTPUT);

  // initialize the pushbutton pin as an input:
  pinMode(buttonPin, INPUT);
}

void loop() {
  // read the value from the sensor:
  sensorValue = analogRead(sensorPin);

  //print the value to the serial monitor so that we can see it
  Serial.println(sensorValue);

  //change the brightness of an LED based on sensor input
  /* REMINDER:
   *  analog input is a value between 0-1023
   *  but analog output is a value between 0-255
   *  either divide by 4 or use the map() function
   *  
   *  also, you must use analogWrite on a PWM ~ pin*/

   brightness = map(sensorValue, 0, 1023, 0, 255);

   //light the leds
   if (buttonState == HIGH) {
     digitalWrite(redLedPin, brightness);
     digitalWrite(yellowLedPin, LOW);
   } else {
     //toggle
     digitalWrite(redLedPin, brightness);
     digitalWrite(yellowLedPin, HIGH);
   }

}

</pre>

<!-- ### Going Further

One fun next-step is to switch out your LEDs for an RGB LED. These are great components because they let us mix color and create a much more dynamic output. RGB LEDs have 4 leads, the longest one is ground.

Here is the wiring:

![RGB LED](images/rgb.png "RGB LED")



<br>

<br>

<br> -->
