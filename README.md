# Banksia ESPHome module

This project has all the config required to easily set up a Banksia sensor/display/button board for home automation with ESPHome!

Check out the example configs below to get started! 


### Example 1: 6-button, no display, SHT31D temp/humidity.

````yaml
substitutions:
  deviceName: "Living Room Banksia"
  deviceId: banksia-livingroom

packages:
  # This is how I set up my network parameters -- otherwise you can add them right in this file
  wifi: !include _wifi.yaml
  
  # The base config has the main juicy bits!
  base: !include banksia/base-esp32c6.yaml
  
  # Buttons and button backlighting
  buttons: !include banksia/buttons.yaml
  backlight: !include banksia/backlight.yaml
  
  # Sensors galore! Some have multiple variations, check the folder for which are available.
  radar: !include banksia/ld2420.yaml
  #illuminance: !include banksia/bh1750.yaml
  temphum: !include banksia/sht3xd.yaml
  airqual: !include banksia/sgp30.yaml
````

