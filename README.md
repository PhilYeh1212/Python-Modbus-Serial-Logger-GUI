# ⚙️ Modbus Logger Pro — Python Modbus RTU + TCP Client with Smart Decoding

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![pymodbus](https://img.shields.io/badge/pymodbus-3.0+-orange.svg)](https://github.com/pymodbus-dev/pymodbus)
[![Protocol](https://img.shields.io/badge/Protocol-Modbus%20RTU%20%2B%20TCP-cyan.svg)](https://modbus.org/)
[![License](https://img.shields.io/badge/License-MIT--like-lightgrey.svg)](#-license)

> **Read any PLC, VFD, energy meter, or sensor with a clean Python GUI.**
> Modbus RTU (RS-485) **and** Modbus TCP in one tool. Smart register
> decoding (uint16 / int16 / int32 / float32) with all common byte/word
> swap options. Demo Mode. CSV logging. No expensive HMI software needed.

Modbus Logger Pro screenshot
<img width="1280" height="720" alt="modbus_cover" src="https://github.com/user-attachments/assets/50f00e1b-bb1f-4e9f-be1c-8490041cb282" />


---

## 🎯 Why this exists

Free Modbus tools either:
1. Are **command-line only** (no GUI for non-developers)
2. Don't support **both RTU and TCP** (most PLCs need both)
3. Don't decode **float32 with byte-swap** (the trap that breaks Schneider /
   Siemens reads)

Paid tools like **Modbus Poll ($129)** or **CAS Modbus Scanner** are
Windows-only and not extensible. This project is a clean middle ground:
GUI-friendly, both transports, real decoding, and you can modify it.

---

## 📂 Open Source vs Pro

This repo contains the **Community Edition** — a working Modbus RTU
logger, free for personal and educational use.

The **[Modbus Logger Pro](https://pokhts.gumroad.com)** version on Gumroad
adds the production features I built for real plant-floor work:

| Feature | Community (this repo) | **[Pro Edition ($49)](https://pokhts.gumroad.com)** |
|---|:---:|:---:|
| Modbus RTU (RS-485 serial) | ✅ | ✅ |
| **Modbus TCP** (Ethernet PLCs) | ❌ | ✅ |
| Multi-threaded GUI (no freezing) | ✅ | ✅ |
| Read holding / input registers | ✅ Basic | ✅ All 4 function codes |
| **Register decoding** (uint16 / int16 / int32 / float32) | ❌ | ✅ All 8 formats |
| **Byte-swap / word-swap options** (Schneider / Siemens trap) | ❌ | ✅ |
| **Modbus exception decoder** (all 9 standard codes) | ❌ | ✅ |
| **CRC validation** on responses | ⚠️ Send only | ✅ Both directions |
| **Demo Mode** with simulated registers | ❌ | ✅ |
| **CSV recording** with timestamps | ❌ | ✅ |
| **Dark industrial UI theme** | ❌ | ✅ |
| **Commercial license** | ❌ | ✅ |
| **Email support** | ❌ | ✅ |

### 👉 [Get Modbus Logger Pro on Gumroad — $49](https://pokhts.gumroad.com)

Or save $47 with the **[Industrial Python Toolkit Bundle](https://pokhts.gumroad.com)**
($129) — includes Modbus + J1939 + MQTT + EtherNet/IP.

---

## 🚀 Quick Start (Community Edition)

```bash
# Clone
git clone https://github.com/PhilYeh1212/Python-Modbus-Serial-Logger-GUI
cd Python-Modbus-Serial-Logger-GUI

# Install
pip install pymodbus pyserial

# Run
python main.py
```

In the GUI, configure the serial port (e.g. `COM3` on Windows, `/dev/ttyUSB0`
on Linux), baud rate, slave address, and register range. Hit **Read** and
the values will appear in the live table.

---

## 🔧 Hardware Compatibility

Tested with:

- **Allen-Bradley** MicroLogix, CompactLogix (via RS-485 modules)
- **Siemens** S7-1200, S7-1500 (via Modbus TCP module)
- **Schneider** Modicon M221, M241
- **Mitsubishi** FX series
- **Delta** DVP series
- **Energy meters** (Schneider PM5xxx, Eaton, Acuvim)
- **VFDs** (ABB ACS series, Schneider Altivar, Siemens MicroMaster)
- **Soil sensors / weather stations** with RS-485 output

If it speaks Modbus, this tool talks to it.

---

## 📖 The float32 Byte-Swap Trap

A common mistake when reading float32 from Modbus: the standard says nothing
about byte/word order, so vendors implement it differently. The Pro version
handles all four common variants:

```
ABCD  — IEEE-754 standard           (most clean implementations)
CDAB  — Word-swap                   (Schneider, some Siemens)
BADC  — Byte-swap                   (rare but exists)
DCBA  — Byte + word swap            (some old PLCs)
```

Pick the wrong one and you'll read `1.4e-41` instead of `25.5°C`. The Pro
version provides a dropdown for each register so you can match the device.

---

## 📚 Related reading

- [**How I Fixed Python's Serial Freezing Issue: A Multi-threaded Tkinter Solution**](https://dev.to/philyeh/how-i-fixed-pythons-serial-freezing-issue-a-multi-threaded-tkinter-solution-2n21)
  — Dev.to article on the threading model used in this tool

---

## 📥 Get the Pro version

The Community Edition is great for learning Modbus. The
**[Pro version](https://pokhts.gumroad.com)** is what I use in actual
client work — production-quality, both RTU and TCP, full decoding,
commercial license.

| Product | Price | Link |
|---|---:|---|
| ⚙️ **Modbus Logger Pro** (this tool, Pro edition) | $49 | [Buy](https://pokhts.gumroad.com) |
| 🚛 **J1939 Sniffer Pro** | $59 | [Buy](https://pokhts.gumroad.com) |
| 📡 **MQTT Logger Pro** | $39 | [Buy](https://pokhts.gumroad.com) |
| 🏭 **EtherNet/IP Study Kit** | $29 | [Buy](https://pokhts.gumroad.com) |
| 🔒 **Private ChatGPT Stack** | $59 | [Buy](https://pokhts.gumroad.com) |
| 📦 **Industrial Python Toolkit Bundle** (4 tools, save $47) | **$129** | [Buy](https://pokhts.gumroad.com) |
| 📊 **CSV Dashboard** (free companion to visualize your logs) | $0 | [Download](https://pokhts.gumroad.com) |

---

## 📫 About

**Phil Yeh** — Senior Automation Engineer based in Taiwan. I build Python
tools for industrial protocol work.

- 🛒 **Store:** [pokhts.gumroad.com](https://pokhts.gumroad.com)
- ✍️ **Blog:** [dev.to/philyeh](https://dev.to/philyeh)
- 💼 **LinkedIn:** [linkedin.com/in/phil-yeh-204144297](https://www.linkedin.com/in/phil-yeh-204144297/)

---

## 📝 License

The Community Edition in this repository is free for personal and
educational use. For commercial use (client projects, internal company
tools, products you sell), please get the **[Pro Edition](https://pokhts.gumroad.com)**
which includes a proper commercial license.

If this tool helped you, **a ⭐ on the repo** means a lot to an indie
developer. Thanks!

---

<sub>**Keywords:** Python, Modbus RTU, Modbus TCP, RS-485, PLC, SCADA,
VFD, energy meter, holding register, pymodbus, GUI, Tkinter, automation,
Schneider, Siemens, Allen-Bradley, float32 word-swap</sub>
<img width="1280" height="720" alt="modbus_cover" src="https://github.com/user-attachments/assets/2db2bc45-642d-42e4-a9b8-d2f99ddab568" />
