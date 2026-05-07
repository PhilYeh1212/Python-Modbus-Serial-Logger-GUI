# Modbus Logger Pro

> A production-ready Modbus RTU/TCP data logger with multi-threaded GUI, 8 data formats, and full byte-order support.
<img width="1280" height="720" alt="modbus_cover" src="https://github.com/user-attachments/assets/609f97ed-5586-46c6-b57e-87a28ba56ab7" />

**This is a commercial tool, sold on Gumroad.** Source code is included in your purchase.

---

## What it does

- **Modbus RTU + TCP** in one tool — switch with one click
- **8 data formats** — INT16, UINT16, INT32, UINT32, FLOAT32, FLOAT64, hex, ASCII
- **All 4 byte orders** — ABCD / CDAB / BADC / DCBA, including the Schneider word-swap that breaks most pymodbus scripts ([read why →](https://dev.to/philyeh/why-your-schneider-plcs-float32-reads-14e-41-instead-of-255degc-44lg))
- **Multi-threaded GUI** — never freezes during long polls
- **Auto-CRC** validation for RTU frames
- **CSV export** — pair with [CSV Dashboard](https://philyeh.gumroad.com/l/python-csv-dashboard) for free interactive plotting
- **Single-file Python** — no install hell, no cloud dependencies

## Why this exists

Most "Modbus debuggers" cost $200-800, run only on Windows, and ship as a 50MB installer that bundles a 2010-era UI. Free alternatives are either CLI-only or break the moment a Schneider PLC sends a CDAB float.

This tool is what I wished existed when I started doing industrial integration work: small, focused, runs on Windows / Mac / Linux, and handles the byte-order quirks every real-world device throws at you.

## Tested on

| Device | Connection | Notes |
|---|---|---|
| Schneider M221, M241 | TCP / RTU | CDAB byte order |
| Siemens S7-1200, S7-1500 | TCP (Modbus wrapper) | CDAB or ABCD |
| Allen-Bradley CompactLogix | TCP (via Prosoft) | ABCD |
| Mitsubishi FX | RTU | ABCD |
| Delta DVP | RTU | ABCD |
| Schneider PM5xxx energy meters | TCP | CDAB |
| ABB ACS / Schneider Altivar VFDs | TCP / RTU | Mixed — test all 4 |

## Get it

→ **[Modbus Logger Pro on Gumroad — $49](https://philyeh.gumroad.com/l/modbus-logger-pro)**

Or grab the **[Industrial Integration Bundle](https://philyeh.gumroad.com/l/industrial-integration-bundle)** ($119) and save $48 vs buying the Modbus, MQTT, and OPC UA tools separately.

## What's in the purchase

- `modbus_logger.py` — Single-file Python application
- `requirements.txt` — Pinned dependencies
- `README.md` — Setup guide + troubleshooting
- Commercial use license per Gumroad EULA

## License

Commercial use license per Gumroad EULA. You may use this software at the company that purchased it for any commercial purpose. Redistribution, resale, or open-sourcing the code is not permitted.

## Support

- Reply to your Gumroad purchase email — I read every one
- Bug reports / feature requests welcome via [GitHub Issues](https://github.com/PhilYeh1212/Python-Modbus-Serial-Logger-GUI/issues)

---

I write about industrial Python and protocol internals at **[dev.to/philyeh](https://dev.to/philyeh)**, and post Chinese versions on [iThelp](https://ithelp.ithome.com.tw/users/20171204).

— Phil Yeh · Senior Automation Engineer · Industrial Python · Developer Tools
