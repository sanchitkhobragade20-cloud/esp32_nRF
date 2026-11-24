# esp32_nRF
A customized DIY 4-button edition of nRFBox for ESP32. Multi-tool for Wi-Fi, BLE, and 2.4GHz RF testing with an OLED display, standalone mode, and bug fixes.
# ESP32 nRFBox — 4-Button DIY Edition

An optimized DIY edition of **nRFBox** designed for the **ESP32 Dev Module** with a **0.96" SSD1306 OLED** display and a simplified **4-button navigation system**. This portable multi-tool is built for experimenting with **Wi-Fi**, **Bluetooth Low Energy (BLE)**, and **2.4 GHz RF (nRF24)** protocols.

### 🚀 Key Improvements & Fixes
* **4-Button Navigation:** Redesigned UI control to work with 4 simple tactile push buttons (UP, DOWN, SELECT, BACK), eliminating the need for custom 5-button PCBs.
* **Standalone Wi-Fi & BLE:** Wi-Fi and Bluetooth tools function completely out-of-the-box without requiring an external nRF24L01 radio module attached.
* **Display Fix:** Resolved the initial black screen bug on fresh ESP32 chips by initializing default EEPROM brightness.
* **Core 2.0.17 Fixes:** Cleaned up duplicate linker definitions and symbol clashes for smooth compilation in the Arduino IDE.

### 📌 Hardware Pinout
Component	Module Pin	ESP32 (30-Pin)	Signal Function & Notes
SSD1306 OLED	GND	GND	Ground
SSD1306 OLED	VCC	3V3	3.3V Power
SSD1306 OLED	SCL	GPIO 22 (D22)	I2C Clock
SSD1306 OLED	SDA	GPIO 21 (D21)	I2C Data
nRF24L01 Module	Pin 1 (GND)	GND	Ground
nRF24L01 Module	Pin 2 (VCC)	3V3	⚠️ 3.3V ONLY (Never connect to 5V or VIN!)
nRF24L01 Module	Pin 3 (CE)	GPIO 5 (D5)	Chip Enable
nRF24L01 Module	Pin 4 (CSN)	GPIO 26 (D26)	★ Chip Select (30-Pin Fix)
nRF24L01 Module	Pin 5 (SCK)	GPIO 18 (D18)	SPI Clock
nRF24L01 Module	Pin 6 (MOSI)	GPIO 23 (D23)	SPI Master Out
nRF24L01 Module	Pin 7 (MISO)	GPIO 19 (D19)	SPI Master In
nRF24L01 Module	Pin 8 (IRQ)	Disconnected	Leave empty / unconnected
Button UP ⬆️	Terminal 1 / 2	GPIO 32 (D32) & GND	Internal pullup active LOW
Button DOWN ⬇️	Terminal 1 / 2	GPIO 33 (D33) & GND	Internal pullup active LOW
Button SELECT 🔘	Terminal 1 / 2	GPIO 25 (D25) & GND	Internal pullup active LOW
Button BACK ↩️	Terminal 1 / 2	GPIO 4 (D4) & GND	Internal pullup active LOW

### ⚙️ Arduino IDE Setup
1. **Board:** Select **ESP32 Dev Module** (using **ESP32 Core v2.0.17**).
2. **Partition Scheme:** Set to **`Huge APP (3MB No OTA/1MB SPIFFS)`**.
3. **Libraries Needed:** Install `U8g2` and `RF24` via Arduino Library Manager.

### ⚠️ Disclaimer & Credits
*This project is created strictly for educational, experimental, and authorized cybersecurity testing purposes only.*
* **Original Project:** [nRFBox](https://github.com/cifertech/nrfbox) by **CiferTech**.
* **4-Button Edition & Fixes:** Maintained by **Sanchit Khobragade** ([@sanchitkhobragade20-cloud](https://github.com/sanchitkhobragade20-cloud)).
* **License:** Distributed under the permissive **MIT License**.
