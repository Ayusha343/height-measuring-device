## Core Aim

Build a hassle-free system to measure a person's height with an ultrasonic sensor and Arduino.

Common name used in project material: Automatic Height Measuring Device (AHMD).

## Theory Used

- Ultrasonic waves are transmitted and reflected from the target.
- Echo travel time is converted to distance.
- Person height is estimated from sensor mounting reference minus measured head distance.

## Materials Mentioned

- 1x Arduino Uno
- 1x Ultrasonic sensor
- 1x 16x2 LCD with I2C
- 2x LEDs
- Jumper wires

## Working Summary

- Sensor computes head-distance using time-of-flight.
- With a known mounting/reference distance (200 cm stated in synopsis), person height is computed.

## Claimed Advantages

- Potentially more accurate than traditional manual methods in favorable conditions.
- Faster and easier to use.
- Useful for repeated mass-check scenarios.

## Applications Mentioned

- Hospitals/medical centers
- Old age homes and orphanages
- Small object measurement after calibration

## Additional Context From IDEANEST Notes

- Stage of operation: Prototype
- Sector: Health
- Installation concept: wall-mounted unit (2-screw mounting)
- Display format: centimeters, feet, and inches on 16x2 LCD
- Power note: 12V adapter is mentioned in submission notes
- Team note in form: described as a solo-built project

## Alignment With Current Sketches

- The codebase includes both fixed-speed and environment-compensated (DHT-based) variants.
- LCD output and LED status feedback are implemented in all variants.
