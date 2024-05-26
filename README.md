# CommonSlotPowerSupply_ESPHome

PMBus/i2c custom component for Common Slot HP Server Power Supplies with SSD1306 OLED display.
Built with Arduino Framework for ESP8266.

Exposes:
  - Embedded information about the PSU ("Name", Manufacturer, Manufactured Date, "Spare Part" Number, "Option Kit" Number, and "CT" Barcode)
  - Fan speed reporting and control
  - Intake Air Temperature and Internal PSU Temperature
  - AC Input Voltage, Current, and Power
  - DC Output Voltage, Current, Power, and "Peak" Current (A value that resets after AC power is removed) 
    

Usage: Copy the full repo to ESPHome directory, maintaining folder structure. Modify yaml with appropriate api, ota, and wifi creds.
 - During compile, there are warnings that can be ignored. (The result of code being manipulated and forced to work with ESPHome)
 - Due to i2c/PMBus limitations, the working bus speed is not quite fast enough to avoid warnings/errors about OLED display "taking too long". These do not affect functionality and can be ignored.

Note: Current and Power reporting is questionable at low load. The PSU seems unable to report values lower than 3 amps or 20 watts.
