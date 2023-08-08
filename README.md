# Sun Tracking Solar Panel System

This repository contains the code and resources for a Sun Tracking Solar Panel System that utilizes light-dependent resistors (LDRs), Arduino, and a servo motor to optimize solar energy absorption by orienting the solar panel towards the sun.

## Table of Contents

- [Introduction](#introduction)
- [Demo](#demo)
- [Circuit Diagram](#circuit-diagram)
- [Simulation](#simulation)
- [Setup Instructions](#setup-instructions)
- [Contributing](#contributing)

## Introduction

The Sun Tracking Solar Panel System is designed to automatically adjust the orientation of a solar panel based on the position of the sun. By utilizing LDRs to sense light intensity and an Arduino-controlled servo motor, the system optimizes solar energy collection throughout the day, enhancing overall energy efficiency.

## Demo

[Will upload the working demo of the project on youtube very soon]

## Circuit Diagram

![Circuit Diagram](https://github.com/adityakanu/Sun-Tracking-Solar-Panel/blob/896c4a3b6a25a4ba0e80dc1312ee1bad53d73ed2/Solar%20tracker%20.png)

Also Look upon: [Schematic View](https://github.com/adityakanu/Sun-Tracking-Solar-Panel/blob/896c4a3b6a25a4ba0e80dc1312ee1bad53d73ed2/Solar%20tracker%20.pdf)

The circuit diagram showcases the integration of Light-Dependent Resistors (LDRs), an Arduino board, and a servo motor to create a Sun Tracking Solar Panel System. This system aims to optimize solar energy absorption by dynamically orienting the solar panel to face the sun, maximizing its exposure throughout the day.

LDR Connections and Functions:

   - Two LDRs (R4 and R5) are strategically placed on the solar panel assembly. These LDRs act as light sensors that detect variations in light intensity caused by the sun's movement across the sky.
   - Each LDR is connected in a voltage divider configuration with a fixed resistor (R2 and R6, respectively). The varying resistance of the LDR due to changing light conditions affects the voltage at the junction of the LDR and the resistor.
   - The analog output of each LDR is connected to analog input pins of the Arduino (A0 and A1). The Arduino reads the analog values from the LDRs to determine the relative intensity of light falling on them.

Arduino Connections and Functions:

   - The Arduino (U1) serves as the central control unit. It reads the analog values from the LDRs and processes this information to calculate the sun's position relative to the solar panel.
   - Based on the LDR readings, the Arduino determines whether one LDR is receiving more light than the other. This imbalance indicates the sun's direction.
   - The Arduino then generates control signals for the servo motor (SERVO1) to adjust the solar panel's orientation. If one LDR is receiving more light, the servo motor rotates the panel to equalize the light on both LDRs, effectively aligning the panel with the sun.

Servo Motor Connections and Functions:

   - The servo motor (SERVO1) is connected to the Arduino using digital pins. Servo motors are commonly used for precise angular control.
   - The Arduino generates Pulse Width Modulation (PWM) signals to control the servo motor's angle. By changing the duty cycle of the PWM signal, the Arduino instructs the servo motor to rotate to a specific position.
   - As the Arduino receives data from the LDRs, it calculates the required angle of adjustment based on the sun's position. It then sends the appropriate PWM signal to the servo motor, causing it to rotate the solar panel to face the sun.

## Simulation

You can simulate the Sun Tracking Solar Panel System using [Tinkercad](https://www.tinkercad.com/). Click [here](https://www.tinkercad.com/things/ekbVjKxLrGj) to access the simulation.

1. Start the simulation.
2. Change the amount of light on the ldrs such that there's a difference between the amount of light on them.
3. Observe the rotation of the servo motor.

## Setup Instructions

Follow these steps to set up and run the Sun Tracking Solar Panel System:

1. Hardware Connections and Initial Setup:
   - Connect the LDRs (R4 and R5) in a voltage divider configuration with the fixed resistors (R2 and R6, respectively).
   - Connect the analog output pins of the LDRs to analog input pins (A0 and A1) on the Arduino (U1).
   - Attach the servo motor (SERVO1) to the Arduino using digital pins capable of generating PWM signals (e.g., D9).
   - Ensure proper power supply to the components, considering voltage requirements and current ratings.

2. Software Installation and Code Uploading:
   - Install the Arduino IDE on your computer if not already installed.
   - Connect the Arduino to your computer via USB and open the Arduino IDE.
   - Download and load the appropriate code for the Sun Tracking Solar Panel System onto the Arduino.
   - Ensure that you have the necessary libraries installed to support analog input reading and servo motor control.

3. LDRs and Arduino Processing:
   - The LDRs continuously monitor light intensity. As the sun's position changes, the LDRs produce varying analog voltages proportional to the light they receive.
   - The Arduino reads the analog values from the LDRs using the analogRead() function. These values are indicative of the relative brightness of each LDR.
   - Based on the readings, the Arduino calculates the difference in light intensity between the two LDRs. This difference helps determine the direction of the sun.

4. Servo Motor Control:
   - The Arduino generates PWM signals to control the servo motor's position. The servo library provides functions to facilitate this control.
   - Depending on the LDR readings, the Arduino calculates the angle by which the solar panel needs to be adjusted to face the sun optimally.
   - The Arduino sends the appropriate PWM signal to the servo motor, commanding it to move to the calculated angle. The servo motor adjusts the solar panel's orientation accordingly.

5. Calibration for Optimal Sun Tracking:
   - Power on the system and observe the servo motor's movement as it adjusts the solar panel's position based on changing sunlight.
   - Initially, the system might require fine-tuning for optimal performance. Observe the solar panel's movement throughout the day and note any discrepancies in tracking accuracy.
   - Adjust calibration parameters in the code, such as angle calculations and servo speed, to improve tracking precision.
   - Test the system over multiple days and make gradual adjustments as needed to achieve consistent and accurate sun tracking.

By following these steps, you'll be able to set up, operate, and calibrate the Sun Tracking Solar Panel System to efficiently harness solar energy by optimizing the solar panel's alignment with the sun's position.

## Contributing

Contributions are welcome! If you'd like to contribute to the project via documentation or better circuit design and improvements, please follow these steps:

1. Fork the repository.

2. Create a new branch for your feature or enhancement: `git checkout -b feature-name`.

3. Make your changes and commit them: `git commit -m 'Description of your changes'`.

4. Push to the branch: `git push origin feature-name`.

5. Open a pull request.
