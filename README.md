# Automatic Height Measuring Device (AHMD)

A prototype embedded system to measure a person's height using an ultrasonic sensor and display the result on an LCD. The project includes two variants:

- With DHT11: adjusts speed-of-sound estimation using temperature and humidity.
- Without DHT11: uses a fixed speed-of-sound approximation.

This project is also referred to as AHMD (Automatic Height Measuring Device).

## Project Goal

Measure human height quickly and with minimal manual effort, suitable for repeated measurements (for example, community checkups).

## Problem It Targets

- Conventional manual methods (measuring tapes and wall charts) can be slower and may require assistance.
- In high-throughput settings (health camps, institutions), a quick and repeatable digital method is preferred.

## Deployment Notes

- Intended for wall mounting (2-screw installation concept in project notes).
- Designed to show reading within a few seconds.
- Project notes mention powering via a 12V adapter (12V 1A or 12V 2A) based on the assembled hardware design.

## How It Works

1. The ultrasonic sensor sends a pulse and measures echo return time.
2. Distance from sensor to head is computed.
3. A reference distance to the ground is captured during early loop cycles.
4. Height is estimated as:

   `height = ground_reference - current_distance`

5. Height is shown on a 16x2 I2C LCD in cm and ft/in.

## Main Hardware

- Arduino Uno
- HC-SR04 ultrasonic sensor
- 16x2 LCD with I2C backpack (commonly address 0x27)
- 2x LEDs (status indication)
- Optional DHT11/DHT22 sensor (depending on sketch variant)
- Jumper wires

The DHT-enabled variant uses ambient temperature and humidity to calibrate ultrasonic distance estimation.

## Folder Guide

- `height_measuring_device_returns/`
  - Baseline folder containing a DHT-enabled sketch and text copy.
- `With DHT11/`
  - DHT11-aware implementation and required library zip bundles.
- `Without DHT-11/`
  - Ultrasonic + LCD implementation without environmental compensation.
- `HMD SYNOPSIS.md`
  - Original project synopsis.

## Notes From Existing Sketches

- Sensor pins are generally:
  - Trig: D9
  - Echo: D10
  - LEDs: D8 (red), D7 (green)
  - DHT pin: A0 (DHT variants)
- LCD uses I2C via SDA=A4 and SCL=A5 on Arduino Uno.
- A threshold is used to detect whether a person is present under the sensor.
- LED behavior is used as a stand/wait status indicator.

## Project Context (From IDEANEST 2.0 Notes)

- Stage: Prototype
- Sector: Health
- Positioning: low-cost digital alternative for practical height measurement workflows
- Team note in submitted form: described as solo-built prototype

## Typical Upload Steps

1. Open the preferred `.ino` file in Arduino IDE.
2. Install required libraries:
   - `LiquidCrystal_I2C`
   - `DHT sensor library` (+ Adafruit Unified Sensor for DHT builds)
3. Select board: Arduino Uno.
4. Select the correct COM port.
5. Upload and open Serial Monitor (9600 baud) for debug output.

## Calibration Tips

- Mount sensor vertically and keep it stable.
- Ensure clear line-of-sight to the subject's head.
- Capture ground reference with no person present.
- Keep ambient airflow low to reduce ultrasonic noise.
- Recheck calibration across seasons if using the non-DHT variant.

## License

MIT. See `LICENSE`.
