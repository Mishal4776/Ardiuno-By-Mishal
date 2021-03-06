Kerala-IoT-Challenge
====================

> Foxlab Makerspace in association with GTech - Group of Technology Companies in Kerala is launching our prestigious program “Kerala IoT Challenge 2021”, with a vision to mould 100 IoT experts in Kerala, hosting on the µLearn platform. Kerala IoT Challenge is a program designed in 4 levels followed by a hackathon to identify and train quality industry leaders in the IoT domain, while any novice learner can start with layer 1 and others can enter laterally to the desired layer after an evaluation.
> 
> About Me
> ========
> 
> Hey guys, I am Muhammed Mshal K.A, Second year ELECTRONICS AND COMMUNICATION DEPLOMA student from [**Govt POLYTECHNIC COLLEGE KALAMASSERY**](https://gptckalamassery.ac.in/) KOCHI. I like to study and explore new dimensions in the electronics field. Eventhough I am beginner to all these fields,I expect myself to be upgraded in the coming days through IOT challenge.For the better view of myself,I am a normal boy from a middleclass family with ambitions to fly high and achieve more. I like to travel and explore the world to know its oppertunities to evolve with coming generation technology. also i like to read, listen music,and to keep my brain and mind fresh. I like to eat and i do it very often since it keep me happy. Also I am well aware of my cons such as I talk to much,overthink a lot(This causes me to have day dreams which is good to a particular extent).

Table of Contents
=================

1.  [Level 1](#level1)
    
    In this Section I am going to show you my works I have done for the IOT challenge which includes 12 experiments.I am using Arduino whic is an Open-source electronic prototyping platform enabling users to create interactive electronic objects.You can visit the Arduino website throuh [**Here**](https://www.arduino.cc/) , Where you can see a hundreds of works and documentations and even you can do it using their tutorials .The 12 experiments that I have done are as follows;
   
    1.  [Hello World LED Blinking](#exp1)
    2.  [Traffic Light](#exp2)
    3.  [LED Chasing Effect](#exp3)
    4.  [Button Controlled LED](#exp4)
    5.  [Buzzer](#exp5)
    6.  [RGB LED](#exp6)
    7.  [LDR Light Sensor](#exp7)
    8.  [Flame Sensor](#exp8)
    9.  [LM35 Temperature Sensor](#exp9)
    10.  [IR Remote Control Using TSOP](#exp10)
    11.  [Potentiometer analog Value Reading](#exp11)
    12.  [7 Segment Display](#exp12)
    
    ASSIGNMENTS
    ===========
    
    1.  [Automatic Night Lighting System](#assign1)

  

* * *

* * *

LEVEL 1
=======

* * *

Experiment 1 - Hello World LED Blinking
=======================================

> A basic Program similar to printing “_Hello World_ “ in any programming language. The Aim is to blink an LED using **Arduino Uno Board**.

> Arduino Uno is an open-source microcontroller board developed by Arduino.cc. It has several advantages over the conventional microcontrollers. It comes with a pre-tested software and hardware libraries and has its own integrated development environment (IDE). Also it is less expensive & beginner friendly.

Components Required
-------------------

*   Arduino Uno Board
*   USB Cable
*   LED (Any Color) x 1 Nos
*   220 OHM Resistor X 1 Nos
*   Breadboard
*   Jumper Wires (Male to Male ) X 2 Nos

Circuit Diagram
---------------

![circuit diagram](https://user-images.githubusercontent.com/91405741/137279765-8a82a34f-1dc0-4afc-9bd3-a31d7f62c428.png)

Code
----

    
   int ledPin=2;
void setup()
{
     pinMode(ledPin,OUTPUT);
}
void loop()
{
    digitalWrite(ledPin,HIGH);
    delay(500);
    digitalWrite(ledPin,LOW);
    delay(500);
}
    
    

Output
------

![Task 1](https://user-images.githubusercontent.com/94855061/153758670-e722be74-35f7-49cf-b72c-26ee6a943d53.png)

> The LED blinked with a time interval of 0.5 second


https://user-images.githubusercontent.com/94855061/153759242-16f7bd41-59d2-46f2-bd4c-b5d5b569b58e.mp4


  
* * *

Experiment 2 : Traffic Light
============================

> In the previous program, we have done the LED blinking experiment with one LED. Now, it’s time to up the stakes and do a bit more complicated experiment-traffic lights. Actually, these two experiments are similar. While in this traffic lights experiment, we use 3 LEDs with different colors rather than 1 LED.

Components Required
-------------------

*   Arduino board \*1
*   USB cable \*1
*   Red M5 LED\*1
*   Yellow M5 LED\*1
*   Green M5 LED\*1
*   220Ω resistor \*3

Circuit Diagram
---------------

![circuit diagram](https://user-images.githubusercontent.com/91405741/137288387-e85f8db9-ae97-49d0-888d-a2fc15e4c496.png)

Code
----

    
    int redled =2; // initialize digital pin 8.
    int yellowled =3; // initialize digital pin 7.
    int greenled =4; // initialize digital pin 4.
    int DELAY_GREEN = 5000;
    void setup()
    {
    pinMode(redled, OUTPUT);// set the pin with red LED as “output”
    pinMode(yellowled, OUTPUT); // set the pin with yellow LED as “output”
    pinMode(greenled, OUTPUT); // set the pin with green LED as “output”
    }
    void loop()
    {
    digitalWrite(greenled, HIGH);//// turn on green LED
    delay(5000);// wait 5 seconds
    
    digitalWrite(greenled, LOW); // turn off green LED
    for(int i=0;i<3;i++)// blinks for 3 times
    {
    delay(500);// wait 0.5 second
    digitalWrite(yellowled, HIGH);// turn on yellow LED
    delay(500);// wait 0.5 second
    digitalWrite(yellowled, LOW);// turn off yellow LED
    } 
    delay(500);// wait 0.5 second
    digitalWrite(redled, HIGH);// turn on red LED
    delay(5000);// wait 5 seconds
    digitalWrite(redled, LOW);// turn off red LED
    }
    
    

Output
------

> In Traffic light the green LED blink about 5 second, then it is turnoff. Then the yellow LED blinks 3 times with a time interval of 0.5 second.Then the red LED blink about 5 seconds. This process continues.

  

* * *

Experiment 3 : LED Chasing Effect
=================================

> We often see billboards composed of colorful LEDs. They are constantly changing to form various light effects. In this experiment, we compile a program to simulate LED chasing effect. The long lead of LED is the positive side; short lead is negative.

Components Required
-------------------

*   Led \*6
*   Arduino board \*1
*   220Ω resistor \*6
*   Breadboard \*1
*   USB cable\*1
*   Breadboard wire \*13

Circuit Diagram
---------------

![circuit diagram](https://user-images.githubusercontent.com/91405741/137292096-feb60c91-1a9a-474b-a596-300285f7b011.png)

Code
----

    
    int BASE = 2;  // the I/O pin for the first LED
    int NUM = 6;   // number of LEDs
    void setup()
    {
       for (int i = BASE; i < BASE + NUM; i++) 
       {
         pinMode(i, OUTPUT);   // set I/O pins as output
       }
    }
    void loop()
    {
       for (int i = BASE; i < BASE + NUM; i++) 
       {
         digitalWrite(i, LOW);    // set I/O pins as “low”, turn off LEDs one by one.
         delay(200);        // delay
       }
       for (int i = BASE; i < BASE + NUM; i++) 
       {
         digitalWrite(i, HIGH);    // set I/O pins as “high”, turn on LEDs one by one
         delay(200);        // delay
       }  
    }
    
    

Output
------

> The LEDs starts turning ON from one end in a sequential manner & after all the LEDs are turned ON, they starts to turn OFF the same way.

  

* * *

Experiment 4: Button Controlled LED
===================================

> An experiment to light an LED using a Push Button.

Components Required
-------------------

*   Arduino Uno
*   Button switch\*1
*   Red M5 LED\*1
*   220ΩResistor\*1
*   10KΩ Resistor\*1
*   Breadboard\*1
*   Breadboard Jumper Wire\*6
*   USB cable\*1

Circuit Diagrams
----------------

![Ztk6E_3102_1628160172](https://user-images.githubusercontent.com/91405741/137344162-7149dfcf-836c-43ec-a01c-177d48958d12.png)

Code
----

    
    int ledpin=11;// initialize pin 11
    int inpin=7;// initialize pin 7
    int val;// define val
    void setup(){
        pinMode(ledpin,OUTPUT);// set LED pin as “output”
        pinMode(inpin,INPUT);// set button pin as “input”
    }
    void loop(){
        val=digitalRead(inpin);// read the level value of pin 7 and assign if to val
        if(val==LOW)// check if the button is pressed, if yes, turn on the LED
        { 
            digitalWrite(ledpin,LOW);
        }
    else{ 
        digitalWrite(ledpin,HIGH);}
    }
    
    

Output
------

> When the push button is pressed the LED is turned on otherwise it is off.

  

* * *

Experiment 5 : Buzzer
=====================

> An experiment to understand the working of a buzzer.

Components Required
-------------------

*   Arduino Uno
*   Buzzer\*1
*   Breadboard\*1
*   Breadboard Jumper Wire\*2
*   USB cable\*1

![BBr05_3102_1628160460](https://user-images.githubusercontent.com/91405741/137346830-1fa2408c-2a1d-4fdf-a049-5736aeb803ec.png)

Code
----

    
    int buzzer=8;// initialize digital IO pin that controls the buzzer
    void setup() 
    { 
      pinMode(buzzer,OUTPUT);// set pin mode as “output”
    } 
    void loop() 
    {
    digitalWrite(buzzer, HIGH); // produce sound
    }
    
    

Output
------

> The Buzzer makes sound.

  

* * *

Experiment 6 : RGB LED
======================

> An experiment to understand the working of a RGB LED.

Components Required
-------------------

*   Arduino Uno
*   USB Cable \* 1
*   RGB LED \* 1
*   Resistor \*3
*   Breadboard jumper wire\*5

Circuit Diagrams
----------------

![xX9cw_3102_1628160649](https://user-images.githubusercontent.com/91405741/137347719-6966c0b1-021d-471c-b0a7-48d0441752d0.png)

Code
----

    
    int redpin = 11; //select the pin for the red LED
    int bluepin =10; // select the pin for the blue LED
    int greenpin =9;// select the pin for the green LED
    int val;
    void setup() {
      pinMode(redpin, OUTPUT);
      pinMode(bluepin, OUTPUT);
      pinMode(greenpin, OUTPUT);
      Serial.begin(9600); //passes the value 9600 to the speed parameter. This tells the Arduino to get ready to exchange messages with the Serial Monitor at a data rate of 9600 bits per second. That's 9600 binary ones or zeros per second, and is commonly called a baud rate.
    }
    void loop() 
    {
    for(val=255; val>0; val--)
      {
       analogWrite(11, val);
       analogWrite(10, 255-val);
       analogWrite(9, 128-val);
       delay(1); 
      }
    for(val=0; val<255; val++)
      {
       analogWrite(11, val);
       analogWrite(10, 255-val);
       analogWrite(9, 128-val);
       delay(1); 
      }
     Serial.println(val, DEC); //DEC specifies the format base 10 (decimal)
    }
    
    

Output
------

> The RGB LED blinks.

  

* * *

Experiment 7 - LDR Light Sensor
===============================

> An experiment to understand the working of an LDR light Sensor.

LDR : Light Dependent Sensor
----------------------------

> Photo Resistor (Photovaristor) is a resistor whose resistance varies from different incident light strength. It’s based on the photoelectric effect of semiconductor. If the incident light is intense, its resistance reduces; if the incident light is weak, the resistance increases.

![L5Iw9_3102_1628755894](https://user-images.githubusercontent.com/91405741/138436746-d1cfb008-0d90-4754-b4c4-fe133329c8b5.png)

Components Required
-------------------

*   Arduino Uno Board
*   Photo Resistor\*1
*   Red M5 LED\*1
*   10KΩ Resistor\*1
*   220Ω Resistor\*1
*   Breadboard\*1
*   Breadboard Jumper Wire\*7
*   USB cable\*1

Circuit Diagrams
----------------

![InShot_20211022_104012830](https://user-images.githubusercontent.com/91405741/138436635-60cb2ec4-091d-4f24-bf96-b0289e06fa00.png)

Procedure
---------

*   Connect the 3.3v output of the Arduino to the positive rail of the breadboard
*   Connect the ground to the negative rail of the breadboard
*   Place the LDR on the breadboard
*   Attach the 10K resistor to one of the legs of the LDR
*   Connect the A0 pin of the Arduino to the same column where the LDR and resistor is connected (Since the LDR gives out an analog voltage, it is connected to the analog input pin on the Arduino. The Arduino, with its built-in ADC (Analog to Digital Converter), then converts the analog voltage from 0-5V into a digital value in the range of 0-1023). - Now connect the other end of the 10K resistor to the negative rail
*   And the the second (free) leg of the LDR to the positive rail Pretty much this is what we need for the light sensing. Basic circuits like this can be done without an Arduino aswell. However, if you want to log the values and use it to create charts, run other logics etc. I will recomend an Arduino or ESP8266 or may be a ESP32 for this. Now, as we want our circuit to do something in the real world other than just displaying the values on the computer screen we will be attaching a LED to the circuit. The LED will turn on when its dark and will go off when its bright. To achieve this we will:
*   Place the LED on the breadboard
*   Connect the 220ohm resistor to the long leg (+ve) of the LED
*   Then we will connect the other leg of the resistor to pin number 13 (digital pin) of the Arduino
*   and the shorter leg of the LED to the negative rail of the breadboard

Code
----

    
    const int ledPin = 13;
    const int ldrPin = A0;
    void setup() {
    Serial.begin(9600);
    pinMode(ledPin, OUTPUT);
    pinMode(ldrPin, INPUT);
    }
    void loop() {
    int ldrStatus = analogRead(ldrPin);
    if (ldrStatus <= 200) {
    digitalWrite(ledPin, HIGH);
    Serial.print("Its DARK, Turn on the LED : ");
    Serial.println(ldrStatus);
    } else {
    digitalWrite(ledPin, LOW);
    Serial.print("Its BRIGHT, Turn off the LED : ");
    Serial.println(ldrStatus);
    }
    }
    
    

Output
------

> When the incident light on the LDR is weak, the LED is bright.

  

* * *

Experiment 8 : Flame Sensor
===========================

> An experiment to understand the working of an Flame sensor.

Flame Sensor
------------

**Usage**:These types of sensors are used for short range fire detection and can be used to monitor projects or as a safety precaution to cut devices off / on.

**Range**:I have found this unit is mostly accurate up to about 3 feet.

**How it works**:The flame sensor is very sensitive to IR wavelength at 760 nm ~ 1100 nm light.

**Analog output (A0)**: Real-time output voltage signal on the thermal resistance.

**Digital output (D0)**: When the temperature reaches a certain threshold, the output high and low signal threshold adjustable via potentiometer.

**Pins:**

*   VCC - Positive voltage input: 5v for analog 3.3v for Digital.
    
*   A0 - Analog output
    
*   D0 - Digital output
    
*   GND - Ground
    

Components Required
-------------------

*   Arduino UNO
*   Flame Sensor
*   LED
*   Buzzer
*   BreadBoard
*   Jumper

Circuit Diagrams
----------------

![1636554036921 1](https://sci-copath.github.io/Kerala-IoT-Challenge/assat/image/exp8.png)

Code
----

    
    int flame=0;// select analog pin 0 for the sensor
    int Beep=9;// select digital pin 9 for the buzzer
    int val=0;// initialize variable
     void setup() 
    {
      pinMode(Beep,OUTPUT);// set LED pin as “output”
     pinMode(flame,INPUT);// set buzzer pin as “input”
     Serial.begin(9600);// set baud rate at “9600”
     } 
    void loop() 
    { 
      val=analogRead(flame);// read the analog value of the sensor 
      Serial.println(val);// output and display the analog value
      if(val>=600)// when the analog value is larger than 600, the buzzer will buzz
      {  
       digitalWrite(Beep,HIGH); 
       }else 
       {  
         digitalWrite(Beep,LOW); 
        }
       delay(500); 
    }
    
    

Output
------

> When a flame is shown to the flame sensor, the buzzer makes sound.

  

* * *

Experiment 9 : LM35 Temperature Sensor
======================================

> An experiment to understand the working of an LM35 Temperature Sensor.

LM35 Temperature Sensor
-----------------------

> LM35 is a common and easy-to-use temperature sensor. LM35 is a widely used temperature sensor with many different package types. At room temperature, it can achieve the accuracy of ±1/4°C without additional calibration processing. LM35 temperature sensor can produce different voltage by different temperature When temperature is 0 ℃, it outputs 0V; if increasing 1 ℃, the output voltage will increase 10 mv.

Components Required
-------------------

*   Arduino Uno Board\*1
*   LM35\*1
*   Breadboard\*1
*   Breadboard Jumper Wire\*5
*   USB cable\*1

Circuit Diagrams
----------------

![1636557270585 1](https://sci-copath.github.io/Kerala-IoT-Challenge/assat/image/exp9.png)

Code
----

    int potPin = 0; // initialize analog pin 0 for LM35 temperature sensor
    void setup()
    {
    Serial.begin(9600);// set baud rate at”9600”
    }
    void loop()
    {
    int val;// define variable
    int dat;// define variable
    val=analogRead(0);// read the analog value of the sensor and assign it to val
    dat=(125*val)>>8;// temperature calculation formula
    Serial.print("Temperatuture");// output and display characters beginning with Tep
    Serial.print(dat);// output and display value of dat
    Serial.println("C");// display “C” characters
    delay(2000);// wait for 2 second
    }
    
    

Output
------

> Temperature readings are shown in the serial monitor.

  

* * *

Experiment 10:IR Remote Control Using TSOP
==========================================

> An experiment to understand the working of IR Remote Control using TSOP.

Components Required
-------------------

*   Arduino Uno Board\*1
*   Infrared Remote Controller(You can use TV Remote or any other remote) \*1
*   Infrared Receiver \*1
*   LED \*6
*   220ΩResistor \*6
*   Breadboard Wire
*   USB cable\*1

Circuit Diagrams
----------------

![Tsop 1](https://content.instructables.com/ORIG/FRB/3S7X/IIG9WV8P/FRB3S7XIIG9WV8P.png?auto=webp&frame=1&width=320&md=c05dcaf43ecec095cde9d68c352c8807)

Code
----

    
    #include <IRremote.h> 
    int RECV_PIN = 3;              
    int c=0;                      
    IRrecv irrecv(RECV_PIN);
    decode_results results;
    void setup()
    {
       pinMode(8, OUTPUT);
       pinMode(9, OUTPUT);
       pinMode(10, OUTPUT);
       pinMode(11, OUTPUT);
       pinMode(12, OUTPUT);
    
       Serial.begin(9600);
      irrecv.enableIRIn();                     
    }
    void loop() {
      if (irrecv.decode(&results)) {
        Serial.println(results.value);
        irrecv.resume();                        
      if(results.value==16773645)      //Up                            
      {
                 digitalWrite(8,HIGH);
      }
      else if(results.value==4294967295)
      {
                 digitalWrite(8,LOW);
      }
       if(results.value==16763445)  //Down                                     
      {
                 digitalWrite(9,HIGH);
      }
      else if(results.value==4294967295)
      {
                 digitalWrite(9,LOW);
      }
        if(results.value==16769565) //left                                       
      {
                 digitalWrite(10,HIGH);
      }
      else if(results.value==4294967295) 
      {
                 digitalWrite(10,LOW);
      }
        if(results.value==16771605) //right                                       
      {
                 digitalWrite(11,HIGH);
      }
      else if(results.value==4294967295)
      {
                 digitalWrite(11,LOW);
      }
        if(results.value==16714485) //ok                                       
      {
                 digitalWrite(12,HIGH);
      }
      else if(results.value==4294967295)
      {
                 digitalWrite(12,LOW);
      }
      }
    }
    
    

Output
------

  

* * *

Experiment 11 :Potentiometer analog Value Reading
=================================================

> An experiment to understand the working of Potentiometer.

Components Required
-------------------

*   Arduino Uno Board\*1
*   10K Potentiometer \*1
*   Breadboard\*1
*   Breadboard Jumper Wire\*3
*   USB cable\*1

Circuit Diagrams
----------------

![Pot 1](https://docs.arduino.cc/static/10842b0499a5e4e370aedcd222b52e2c/5a190/circuit.png)

Code
----

    
    int potpin=0;// initialize analog pin 0
    int val=0;// define val, assign initial value 0
    void setup(){
        Serial.begin(9600);// set baud rate at 9600
    }
    void loop(){
        val=analogRead(potpin);// read the analog value of analog pin 0, and assign it to val 
        Serial.println(val);// display val’s value
    }
    
    

Output
------

> The potentiometer readings are shown in the serial monitor.

  

* * *

Experiment 12 : 7 Segment Display
=================================

> An experiment to understand the working of 7 Segment Display.

Components Required
-------------------

*   Arduino Uno Board\*1
*   digit LED Segment Display\*1
*   220Ω Resistor\*8
*   Breadboard\*1
*   Breadboard Jumper Wires \*several
*   USB cable\*1

Circuit Diagrams
----------------

![7segment 1](https://sci-copath.github.io/Kerala-IoT-Challenge/assat/image/exp12.png)

Code
----

    
    int a=7;// set digital pin 7 for segment a
    int b=6;// set digital pin 6 for segment b
    int c=5;// set digital pin 5 for segment c
    int d=10;// set digital pin 10 for segment d
    int e=11;// set digital pin 11 for segment e
    int f=8;// set digital pin 8 for segment f
    int g=9;// set digital pin 9 for segment g
    int dp=4;// set digital pin 4 for segment dp
    void digital_0(void) // display number 5
    {
    unsigned char j;
    digitalWrite(a,HIGH);
    digitalWrite(b,HIGH);
    digitalWrite(c,HIGH);
    digitalWrite(d,HIGH);
    digitalWrite(e,HIGH);
    digitalWrite(f,HIGH);
    digitalWrite(g,LOW);
    digitalWrite(dp,LOW);
    }
    void digital_1(void) // display number 1
    {
    unsigned char j;
    digitalWrite(c,HIGH);// set level as “high” for pin 5, turn on segment c
    digitalWrite(b,HIGH);// turn on segment b
    for(j=7;j<=11;j++)// turn off other segments
    digitalWrite(j,LOW);
    digitalWrite(dp,LOW);// turn off segment dp
    }
    void digital_2(void) // display number 2
    {
    unsigned char j;
    digitalWrite(b,HIGH);
    digitalWrite(a,HIGH);
    for(j=9;j<=11;j++)
    digitalWrite(j,HIGH);
    digitalWrite(dp,LOW);
    digitalWrite(c,LOW);
    digitalWrite(f,LOW);
    }
    void digital_3(void) // display number 3
    {digitalWrite(g,HIGH);
    digitalWrite(a,HIGH);
    digitalWrite(b,HIGH);
    digitalWrite(c,HIGH);
    digitalWrite(d,HIGH);
    digitalWrite(dp,LOW);
    digitalWrite(f,LOW);
    digitalWrite(e,LOW);
    }
    void digital_4(void) // display number 4
    {digitalWrite(c,HIGH);
    digitalWrite(b,HIGH);
    digitalWrite(f,HIGH);
    digitalWrite(g,HIGH);
    digitalWrite(dp,LOW);
    digitalWrite(a,LOW);
    digitalWrite(e,LOW);
    digitalWrite(d,LOW);
    }
    void digital_5(void) // display number 5
    {
    unsigned char j;
    digitalWrite(a,HIGH);
    digitalWrite(b, LOW);
    digitalWrite(c,HIGH);
    digitalWrite(d,HIGH);
    digitalWrite(e, LOW);
    digitalWrite(f,HIGH);
    digitalWrite(g,HIGH);
    digitalWrite(dp,LOW);
    }
    void digital_6(void) // display number 6
    {
    unsigned char j;
    for(j=7;j<=11;j++)
    digitalWrite(j,HIGH);
    digitalWrite(c,HIGH);
    digitalWrite(dp,LOW);
    digitalWrite(b,LOW);
    }
    void digital_7(void) // display number 7
    {
    unsigned char j;
    for(j=5;j<=7;j++)
    digitalWrite(j,HIGH);
    digitalWrite(dp,LOW);
    for(j=8;j<=11;j++)
    digitalWrite(j,LOW);
    }
    void digital_8(void) // display number 8
    {
    unsigned char j;
    for(j=5;j<=11;j++)
    digitalWrite(j,HIGH);
    digitalWrite(dp,LOW);
    }
    void digital_9(void) // display number 5
    {
    unsigned char j;
    digitalWrite(a,HIGH);
    digitalWrite(b,HIGH);
    digitalWrite(c,HIGH);
    digitalWrite(d,HIGH);
    digitalWrite(e, LOW);
    digitalWrite(f,HIGH);
    digitalWrite(g,HIGH);
    digitalWrite(dp,LOW);
    }
    void setup()
    {
    int i;// set variable
    for(i=4;i<=11;i++)
    pinMode(i,OUTPUT);// set pin 4-11as “output”
    }
    void loop()
    {
    while(1)
    {
    digital_0();// display number 0
    delay(1000);// wait for 1s
    digital_1();// display number 1
    delay(1000);// wait for 1s
    digital_2();// display number 2
    delay(1000); // wait for 1s
    digital_3();// display number 3
    delay(1000); // wait for 1s
    digital_4();// display number 4
    delay(1000); // wait for 1s
    digital_5();// display number 5
    delay(1000); // wait for 1s
    digital_6();// display number 6
    delay(1000); // wait for 1s
    digital_7();// display number 7
    delay(1000); // wait for 1s
    digital_8();// display number 8
    delay(1000); // wait for 1s
    digital_9();// display number 9
    delay(1000); // wait for 1s
    }
    }
    
    

Output
------

Assigenment
===========

Assigenment 1- Night lighting system
------------------------------------

### Components

*   Arduino Uno
*   Breadboard
*   RED,GREEN LED
*   Jumper wire
*   Restsor 220 ohm 10 k
*   LDR Sensor

### Circuit

![Expriment 3](https://sci-copath.github.io/Kerala-IoT-Challenge/assat/image/ass1.png)

### Video

### Code

    #define LDR A0// LDR CONNECT A0
    #define LED 11 // LED CONNECT 11
    int readData=0;
    void setup(){ 
      pinMode(LED,OUTPUT);
      pinMode(LDR,INPUT);
      Serial.begin(9600);
    } 
    void loop(){
      readData=analogRead(LDR);
      Serial.println(readData);
      if(readData>200)
        digitalWrite(LED,HIGH);
      else
        digitalWrite(LED,LOW);
    }
