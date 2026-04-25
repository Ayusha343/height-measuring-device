# Without DHT-11 Variant

This variant estimates distance with a fixed speed-of-sound constant and does not use temperature/humidity compensation.

## Distance Model

The sketch uses a standard approximation:

`distance_cm = duration_us * 0.0343 / 2`

## Folder Contents

- `height_measuring_device_returns.ino`: sketch file.
- `height_measuring_device_returns .txt`: text copy of sketch.
- `LiquidCrystal_I2C-1.1.2.zip`: LCD library archive.

## Notes

- Simpler setup than DHT variant.
- Good for stable room conditions where compensation is less critical.
- Threshold logic determines vacancy/presence and display state.
