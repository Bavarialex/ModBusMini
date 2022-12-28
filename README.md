# ModB mini


This is for displaying PV inverter Data on a M5stack core2.

Deutscher Text: <https://github.com/Bavarialex/ModBusMini/blob/main/German/Deutsch.md>

![image](https://github.com/Bavarialex/ModBusMini/blob/main/pics/m502.jpg)

You need:
- M5Stack core2
- SD card, formatted with FAT32, 
  already containing the font (VLW)-files
- ESPHomeFlasher tool <https://github.com/esphome/esphome-flasher/releases>
- Config file for your PV inverter

For unsupported inverters use Simple modbus tool <https://www.simplymodbus.ca/SMT812.zip> to transfer registers to needed codes for config-file.

Config - files already available for:
- EPEver with Wifi01

HOW TO:
- Format SD card in fat32 format.
- Copy 2 font-files (.vfw) to SD-card.
- Open config.txt in any text-editor.
- Insert you WiFi-Data (SSID and password - without "!).
- Overwrite Host-ip with ip of your Modbus-client/server.
- Overwrite Port with the port of your Modbus-client/server.
- Save config on SD-card.

- Download firmware.bin
- Download ESPHomeFlasher tool. Check for right com-port and open firmware.bin.
- Connect M5stack to pc.
- Flash firmware.
- Insert SD-card in M5stack.
- Press reboot.
- Enjoy!

Hint:
- Left button switches to second bank for displaying parameters ID12, ID22 and ID32
- Once flashed with cable, next time use browser: IPofModBmini/update and upload and update from there!
