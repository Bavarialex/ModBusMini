# ModB mini


Nettes Tool, um Modbus Daten (z.B. von einem PV-Wechselrichter) anzuzeigen.

![image](https://github.com/Bavarialex/ModBusMini/blob/main/pics/m502.jpg)

Was braucht's:
- M5Stack core2
- SD Karte, formatiert mit FAT32, 
  darauf die font (.vlw)-Dateien
- ESPHomeFlasher tool <https://github.com/esphome/esphome-flasher/releases>
- Das Config file (config.txt) für das Modbus-Gerät

Um selbst ein config.txt für das eigene Gerät zu bauen, nimmt man das Simple modbus tool <https://www.simplymodbus.ca/SMT812.zip>. Hiermit kann getestet werden, über welches Protokoll (modbusRTUoverTCP oder modbusTCP) sich das Gerät ansprechen lässt und bei welchen Registern plausible Werte übertragen werden.

Config - files gibt's schon für:
- EPEver with Wifi01

Wie's geht::
- SD Karte in fat32 formatieren.
- 2 font-files (.vfw) auf die Karte kopieren.
- Config.txt in einem Textdeitor öffnen.
- WLAN-Daten eintragen (SSID und password - ohne Anführungszeichen!).
- Host-ip mit der IP vom Modbus-client/server (je nach Betriebsart) überschreiben.
- Port mit dem Port des Modbus-client/server überschreiben.
- Config.txt auf SD-Karte speichern.

- firmware.bin runterladen
- ESPHomeFlasher tool runterladen und starten. Den richtigen com-port und die firmware.bin auswählen.
- M5stack an den PC anschliessen.
- Firmware flashen.
- SD-Karte in M5stack core2 einlegen.
- Reboot drücken (vorne unten).
- Freuen!

Tipp:
- Der linke Button schaltet auf die zweite Bank, nun können auch die Werte ID12, ID22 und ID32 angezeigt werden...
