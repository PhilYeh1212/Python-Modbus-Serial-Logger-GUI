> **🔥 BLACK FRIDAY SALE:** Get **15% OFF** all source codes with code `BLACKFRIDAY`. [**Click here to apply discount automatically**](https://pokhts.gumroad.com/l/senior-engineer-toolkit?offer_code=BLACKFRIDAY)





# 🐍 Python Modbus Data Logger (Pro GUI Version)

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-Commercial-green.svg)]()
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey.svg)]()

> **Stop writing boilerplate serial code.**
> This is a production-ready, multi-threaded Serial/Modbus data logger built with Python **Tkinter**. Designed for Automation Engineers to debug RS485/Serial devices without freezing UI.

<img width="744" height="910" alt="demo" src="https://github.com/user-attachments/assets/cb15afc6-4efe-4aba-af0a-1f4eba9c5e49" />

---

## 🚀 Why this tool? (V2.0 Updates)
I built this tool because most free scripts lack stability. This V2.0 release includes features requested by senior engineers:

* **✅ Adjustable Baud Rate:** Support for 9600, 19200, 38400, 57600, 115200 bps.
* **✅ Raw Hex Logging:** Records the raw byte response (RX) alongside parsed values. Essential for debugging unknown protocols.
* **✅ Auto-Timestamped Files:** Automatically generates unique CSV files (e.g., `datalog_20231102.csv`) to prevent data overwriting.
* **✅ Smart Hex Input:** Accurately parses commands with or without spaces (e.g., `01 03` or `0103`).

---

## ✨ Core Features
* **GUI Interface:** Built with `tkinter` (Standard Library), no heavy Qt/Electron dependencies.
* **Non-Blocking:** Uses `threading` to keep the UI responsive while polling data at high speeds.
* **Auto CRC-16:** Automatically calculates and appends Modbus RTU CRC (Little-Endian).
* **Cross-Platform:** Works natively on Windows, Linux, and macOS.

## 🛠️ Dependencies
Only one external library is required:
```bash
pip install pyserial
```

📥 Download Full Source Code
You can get the Complete Source Code (main.py) which includes the full GUI implementation, threading logic, and CRC algorithms.

It is fully commented and ready to be customized for your own proprietary protocols.

👉 Get the Source Code here: [Download on Gumroad ($29)](https://pokhts.gumroad.com/l/python-modbus-logger) (Includes: main.py, requirements.txt, and Setup Guide)

📖 Code Sneak Peek (Threading Logic)
The core logic uses a separate thread to handle the serial loop without freezing the UI:

```
Python

# The UI will NEVER freeze because we run this in a separate thread
def loop(self):
    while self.is_running:
        # ... (Serial Read Logic)
        response = self.ser.read(100)
        if response:
            # Log Raw Hex + Parsed Data to CSV
            writer.writerow([current_time, hex_resp, val1, val2])
        # ...
```
👨‍💻 About the Author
Phil Yeh - Senior Automation Engineer

My Gumroad Store (More Engineering Tools)

Keywords: Python, Modbus RTU, RS485, Serial Communication, Data Logger, Tkinter GUI, Scada, Automation, Source Code, CRC16

