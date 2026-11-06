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
* **OLED Display (SSD1306 I2C):**
  * SDA → **GPIO 21** | SCL → **GPIO 22** | VCC → 3.3V | GND → GND
* **Tactile Buttons (Connect to GND):**
  * UP: **GPIO 32** | DOWN: **GPIO 33**
  * SELECT: **GPIO 25** | BACK: **GPIO 4**
* **Optional nRF24L01+ Module (SPI):**
  * CE: **GPIO 5** | CSN: **GPIO 17** | SCK: **GPIO 18**
  * MOSI: **GPIO 23** | MISO: **GPIO 19**

### ⚙️ Arduino IDE Setup
1. **Board:** Select **ESP32 Dev Module** (using **ESP32 Core v2.0.17**).
2. **Partition Scheme:** Set to **`Huge APP (3MB No OTA/1MB SPIFFS)`**.
3. **Libraries Needed:** Install `U8g2` and `RF24` via Arduino Library Manager.

### ⚠️ Disclaimer & Credits
*This project is created strictly for educational, experimental, and authorized cybersecurity testing purposes only.*
* **Original Project:** [nRFBox](https://github.com/cifertech/nrfbox) by **CiferTech**.
* **4-Button Edition & Fixes:** Maintained by **Sanchit Khobragade** ([@sanchitkhobragade20-cloud](https://github.com/sanchitkhobragade20-cloud)).
* **License:** Distributed under the permissive **MIT License**.
