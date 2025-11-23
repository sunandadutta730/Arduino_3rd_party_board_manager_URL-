# 📚 Arduino Boards Manager — Quick Reference & Install Guide

Add these Boards Manager URLs to your Arduino IDE to unlock popular cores (ESP8266, ESP32, STM32, ATmega variants, Seeeduino XIAO, DigiSpark, and more).

---

## 🔗 Board / Platform — URLs

| Board / Platform                          | Boards Manager URL                                                                               |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **ESP8266**                               | `http://arduino.esp8266.com/stable/package_esp8266com_index.json`                                |
| **ESP32**                                 | `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json`    |
| **STM32 (STM32Duino)**                    | `https://github.com/stm32duino/BoardManagerFiles/raw/main/package_stmicroelectronics_index.json` |
| **ATmega32 (MCUdude / MegaCore)**         | `https://mcudude.github.io/MegaCore/package_MCUdude_MegaCore_index.json`                         |
| **MiniCore (ATmega8/168/328, etc.)**      | `https://mcudude.github.io/MiniCore/package_MCUdude_MiniCore_index.json`                         |
| **MightyCore (ATmega16/32/64/128, etc.)** | `https://mcudude.github.io/MightyCore/package_MCUdude_MightyCore_index.json`                     |
| **Seeeduino XIAO**                        | `https://files.seeedstudio.com/arduino/package_seeeduino_boards_index.json`                      |
| **Digistump (DigiSpark)**                 | `http://digistump.com/package_digistump_index.json`                                              |

---

# 🚀 How to install — step-by-step (attractive & copyable)

> These steps work for **Arduino IDE 1.8.x** and **Arduino IDE 2.x** (the UI wording differs slightly).
> You can add *multiple* URLs — enter them separated by commas in the Preferences dialog.

### 1) Open Arduino IDE → Preferences

* **IDE 1.8.x**: *File → Preferences*
* **IDE 2.x**: *File → Preferences* (or click the gear icon)
* Look for **“Additional Boards Manager URLs”**.

### 2) Add the URLs

* Paste one URL per line **or** paste them all separated by commas.
* Example (paste this block directly):

```
http://arduino.esp8266.com/stable/package_esp8266com_index.json,
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json,
https://github.com/stm32duino/BoardManagerFiles/raw/main/package_stmicroelectronics_index.json,
https://mcudude.github.io/MegaCore/package_MCUdude_MegaCore_index.json,
https://mcudude.github.io/MiniCore/package_MCUdude_MiniCore_index.json,
https://mcudude.github.io/MightyCore/package_MCUdude_MightyCore_index.json,
https://files.seeedstudio.com/arduino/package_seeeduino_boards_index.json,
http://digistump.com/package_digistump_index.json
```

> Tip: Keep frequently-used URLs in a `boards-manager-urls.txt` in your repo for easy copying.

### 3) Open Boards Manager

* **IDE 1.8.x**: *Tools → Board → Boards Manager…*
* **IDE 2.x**: *Tools → Board → Boards Manager* (search is at the top)

### 4) Search & Install each core

* Type the vendor or board name (e.g., `esp8266`, `esp32`, `stm32`, `mcudude`, `seeeduino`, `digistump`).
* Click **Install** for the matching package.
* Wait — some packages are large (ESP32/ESP8266 include toolchains).

### 5) Select board & port

* After install: *Tools → Board → [choose your board]*
* Select the correct *Port* (COMx on Windows, `/dev/ttyUSBx` on Linux/Mac).

### 6) Test with an example

* Load a simple sketch like `Blink` (or the board-specific example) and upload.
* Check the Serial Monitor for debug messages (most ESP boards print their IP).

---

# 🧰 Platform-specific notes & tips

* **ESP8266 (NodeMCU, Wemos)**

  * Use `Arduino Core for ESP8266 by ESP8266 Community`.
  * If upload fails, try slower upload speed (e.g., 115200 → 74880 sometimes used for boot messages).

* **ESP32**

  * Installs toolchain & partition manager. Choose the correct `Flash Frequency` / `Partition Scheme` for advanced use.
  * If you face issues, install the CH340/CP210x drivers depending on your board.

* **STM32**

  * Some STM32 boards need ST-Link or a separate USB-to-Serial bootloader; check the board docs.

* **MCUdude MegaCore, MiniCore, MightyCore**

  * These add classic AVR variants (ATmega32, ATmega8/328, ATmega128, etc.).
  * After installing, choose the correct clock, bootloader, and programmer settings under *Tools*.

* **Seeeduino XIAO**

  * Tiny board — pick the XIAO entry and flash with the correct upload speed.

* **DigiSpark (Digistump)**

  * Digistump cores enable ATTiny-based boards. Use tiny example sketches and verify the USB driver if required.

---

# ⚠️ Troubleshooting (quick)

* **Board not listed**: Re-open Boards Manager after adding URLs, restart IDE if necessary.
* **Slow or failed download**: Check internet, try again later, or manually download core archives (advanced).
* **Driver problems**: Install CP210x / CH340 drivers for USB-serial chips.
* **Upload errors**: Select correct COM port, lower upload speed, press BOOT (if board requires manual boot mode).

---
