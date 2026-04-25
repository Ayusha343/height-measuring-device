# Baseline Variant (height_measuring_device_returns)

This folder contains a height measurement sketch that uses:

- Ultrasonic sensor for distance
- I2C LCD for display
- DHT sensor support in the provided sketch copy
- LED status outputs

## Files

- `height_measuring_device_returns.ino`: Arduino sketch.
- `height_measuring_device_returns .txt`: text copy of sketch.
- STL and zip assets are present for enclosure/display and libraries.

## Behavior Summary

- Captures a reference (`ground`) after startup loops.
- Computes current distance and derives person height.
- Displays cm and ft/in on LCD.
- Uses LED indication based on occupancy/threshold logic.

## Dependencies

- `LiquidCrystal_I2C`
- `DHT sensor library`
- `Adafruit Unified Sensor` (for DHT builds)
