# With DHT11 Variant

This variant compensates ultrasonic calculations using environmental readings from DHT11.

In project notes, this variant aligns with the AHMD concept for higher consistency across changing weather conditions.

## Why DHT11 Here

Speed of sound changes with temperature and humidity. This sketch computes:

`speed = 331.3 + 0.606 * temperature + 0.01243 * humidity`

and uses it for distance/height estimation.

## Folder Contents

- `height_measuring_device_returns .txt`: text copy of DHT11 sketch.
- `height_measuring_device_returns/height_measuring_device_returns.ino`: sketch file.
- Library archives:
  - `DHT_sensor_library.zip`
  - `Adafruit_Sensor-master.zip`
  - `LiquidCrystal_I2C-1.1.2.zip`

## Notes

- DHT pin is configured at A0 in the current sketch.
- LCD I2C address is set to 0x27.
- Presence threshold currently uses distance checks around 150 cm.
- LED signaling is used for stand/wait indication (green/red behavior).
- Project notes mention wall-mount use and adapter-based power for deployment builds.
