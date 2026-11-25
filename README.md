# Dual-Axis-Solar-Tracker

2.Project Overview

This project is a Dual-Axis Solar Tracking System developed using an Arduino Uno to automatically adjust the position of a solar panel according to the direction of sunlight.

The system uses Light Dependent Resistors (LDRs) to detect the intensity of sunlight from different directions. Based on the sensor readings, the Arduino controls MG995 servo motors to adjust the solar panel's horizontal and vertical positions.

The main objective of this project is to keep the solar panel aligned with the direction of maximum sunlight exposure, improving the efficiency of solar energy collection compared to a fixed-position solar panel.

3.Hardware Components

Arduino Uno

MG995 Servo Motor

Power Supply

LM2596 Buck Converter

LDR Sensors

Solar Panel

L7805 Voltage Regulator

Metal Servo Horns

4.Working Principle

The system operates using light intensity measurements from LDR sensors positioned in different directions.

Sunlight Detection: LDR sensors detect the intensity of sunlight from different directions.

Signal Processing: The Arduino Uno reads the LDR sensor values and compares the light intensity readings.

Horizontal Tracking: The Arduino adjusts the horizontal position of the solar panel using a servo motor.

Vertical Tracking: Another servo motor adjusts the vertical position of the solar panel.

Continuous Tracking: This process repeats continuously, allowing the solar panel to follow the direction of maximum sunlight.

5.Technologies Used

Arduino Uno

Embedded C/C++ (Arduino programming)

LDR-based light sensing

Servo motor control

DC power regulation
