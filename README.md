# Banksia ESPHome module

This project has all the config required to easily set up a Banksia sensor/display/button board for home automation with ESPHome!

Check out the example configs below to get started! 


### Example 1: 6-button, no display, SHT31D temp/humidity.

````yaml
substitutions:
  deviceName: "Living Room Banksia"
  deviceId: banksia-livingroom

packages:
# This is how I import my network settings, but you could also add it directly to the file.
  wifi: !include _wifi.yaml
  
  banksia:
    url: https://github.com/cortices/banksia-esphome
    files:
# Base processor version
      - base-esp32c6.yaml
# Buttons and Display
      - buttons.yaml
      - backlight.yaml
# Sensors Equipped
      - ld2420.yaml
      - bh1750.yaml
      - sht3xd.yaml
      - sgp30.yaml

````

### Example 2: 4-button, e-paper display, BME680 temp/humidity/pressure.

````yaml
substitutions:
  deviceName: "Bedroom Banksia"
  deviceId: banksia-bedroom

packages:
  wifi: !include _wifi.yaml

  banksia:
    url: https://github.com/cortices/banksia-esphome
    files:
# Base processor version
      - base-esp32c6.yaml
# Buttons and Display
      - buttons.yaml
      - backlight.yaml 
      - display.yaml
# Sensors Equipped
      - ld2420.yaml
      - bh1750.yaml
      - bme680.yaml
      - sgp30.yaml
````

