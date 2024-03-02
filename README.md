# Potentiometer with Servo Motor Task

Welcome to the Potentiometer with Servo Motor task! This task demonstrates how to use a potentiometer to control the position of a servo motor. By turning the knob of the potentiometer, you can adjust the angle of the servo motor's shaft. This task is a great way to learn about analog input and servo motor control with a microcontroller.

## Introduction

The Potentiometer with Servo Motor task aims to provide a practical example of using a potentiometer to control the position of a servo motor. Servo motors are commonly used in robotics and automation for precise control of angular position. By combining a potentiometer with a servo motor, we can create a simple yet effective control mechanism.

## How it Works

The task works by using the potentiometer to generate an analog voltage that corresponds to a desired angle for the servo motor. The Arduino reads this voltage and maps it to a specific angle range for the servo motor. As the knob of the potentiometer is turned, the Arduino continuously updates the servo motor's position to match the desired angle.

## Getting Started

### Components Required

To build this task, you will need the following components:

- Arduino board (e.g., Arduino Uno)
- Servo motor
- Potentiometer
- Breadboard
- Jumper wires

### Steps

Follow these steps to set up the circuit:

1. Connect one leg of the potentiometer to the 5V pin on the Arduino.
2. Connect the other leg of the potentiometer to the ground (GND) pin on the Arduino.
3. Connect the wiper (middle pin) of the potentiometer to analog pin A0 on the Arduino.
4. Connect the signal wire of the servo motor to digital pin 9 on the Arduino.
5. Connect the power (VCC) and ground (GND) wires of the servo motor to the 5V and GND pins on the Arduino, respectively.
6. Ensure all components are securely connected to the breadboard.


| Arduino       | Potentiometer  | Servo Motor   |
| ------------- | -------------- | --------------|
| 5V            | Left           | VCC           |
| A0            | Wiper          |               |
| GND           | GND            | GND           |
|               |                | Signal        |

## Connection

A visual representation of the circuit connection is provided in the circuit diagram below:

![screen-gif](https://github.com/ItsRawanMoha/Potentiometer-with-servo-motor/blob/main/Potentiometer%20with%20servo%20motor.png)

## Output

Once the circuit is set up and the code is uploaded to the Arduino board, you can turn the knob of the potentiometer to adjust the angle of the servo motor's shaft.

## Code
```
#include <Servo.h>  // add servo library

Servo myservo;  // create servo object to control a servo

int potpin = 0;  // analog pin used to connect the potentiometer
int val;    // variable to read the value from the analog pin

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
}

void loop() {
  val = analogRead(potpin);            // reads the value of the potentiometer (value between 0 and 1023)
  val = map(val, 0, 1023, 0, 180);     // scale it to use it with the servo (value between 0 and 180)
  myservo.write(val);                  // sets the servo position according to the scaled value
  delay(15);                           // waits for the servo to get there
}
```
## Pictures

<img src="https://github.com/ItsRawanMoha/Potentiometer-with-servo-motor/blob/main/Potentiometer%20with%20servo%20motorP.jpeg" alt="Alt text" width="400" height="400">  ![screen-gif](https://github.com/ItsRawanMoha/Potentiometer-with-servo-motor/blob/main/Potentiometer%20with%20servo%20motorG.gif)

## Conclusion

The Potentiometer with Servo Motor task provides a practical demonstration of using a potentiometer to control the position of a servo motor. It showcases the versatility of servo motors in robotics and automation applications.
