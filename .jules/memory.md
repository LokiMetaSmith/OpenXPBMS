## Archived: 2026-10-31
* OpenXPBMS repository context:
  * OpenXPBMS is an Open Source BMS (Battery Management System) for Valence XP Batteries.
  * It communicates with built-in modules over factory communication cables to read data (voltage, temperature) and determine if batteries should remain connected.
  * It does not make write changes; it only listens.
* Repository structure:
  * `BMS/`: Arduino sketch to run the actual BMS. Implements monitoring and CRC.
  * `PCB/`: KiCad schematic and PCB design files showing how modules are connected together.
  * `Utilities/`: Python scripts (`Valence.py`) for diagnostic/research to obtain voltage/temperature readings from batteries.
* Protocol:
  * Modbus-like protocol over RS485.
  * Broadcasts a wake-up command, followed by a request to specific batteries to read holding registers for voltage/temp.
