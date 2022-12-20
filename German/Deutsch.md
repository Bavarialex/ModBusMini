# ModBusMini


Nettes Tool, um Modbus Daten (z.B. von einem PV-Wechselrichter) anzuzeigen.

![image](https://github.com/Bavarialex/ModBusMini/blob/main/pics/m502.jpg)

Was braucht's:
- M5Stack core2
- SD Karte, formatiert mit FAT32, 
  darauf die font (VLW)-Dateien
- ESPHomeFlasher tool <https://github.com/esphome/esphome-flasher/releases>
- Das Config file (config.txt) für das Modbus-Gerät

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
- Flash firmware.
- Insert SD-card in M5stack.
- Press reboot.
- Enjoy!
