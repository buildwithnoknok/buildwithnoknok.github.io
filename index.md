# Welcome to the noknok Ecosystem

Modular hardware for Makers, 3D Designers, Builders, and Explorers.  
This is the central hub for all noknok modules, kits, documentation, and ecosystem standards.

- **Main Website** — [https://www.noknok.app](https://www.noknok.app)
- **Shop** — [https://shop.noknok.app](https://shop.noknok.app)

---

# Who are you? Choose your path:

- **[I'm a Software Maker](#software-maker)** — I use existing modules and program in Python.
- **[I'm a Hardware Maker](#hardware-maker)** — I design or modify noknok PCBs.
- **[I'm a 3D Designer](#3d-designer)** — I create housings for noknok modules and kits.
- **[I'm a Builder](#builder)** — I assemble ready-made noknok kits.

---

## Software Maker

You want to use noknok modules to build a product, prototype, or kit and program them in Python?

**Start here:**

- **Python library and example scripts**  
  [`noknok.py`](https://github.com/buildwithnoknok/brain-Pico/tree/main/software) — the Conductor library that runs on the Pico. Includes drivers for all I²C modules, enumeration, roles, and test scripts.

- **Module API documentation**  
  Each module's `README.md` contains the full I²C protocol, Python API, and wiring guide.  
  → [Module Index](#module-index)

- **How module discovery works**  
  All modules are found automatically at boot — no hardcoded addresses.  
  → [Enumeration Protocol](https://github.com/buildwithnoknok/Ecosystem/blob/main/software/enumeration.md)

- **Software & firmware conventions**  
  → [Software Guidelines](https://github.com/buildwithnoknok/Ecosystem/blob/main/software/readme.md)

---

## Hardware Maker

You want to create your own or customize existing hardware modules that plug into the noknok ecosystem?

**Start here:**

- **Electrical Standards**  
  Connector pinout, power rules, I²C addressing, PCB design, flashing interface.  
  → [Electrical Guidelines](https://github.com/buildwithnoknok/Ecosystem/blob/main/electrical/readme.md)

- **Mechanical Standards**  
  PCB sizes (20×20 mm, 40×40 mm, 40×60 mm), mounting holes, KiCad origin rules.  
  → [Mechanical Guidelines](https://github.com/buildwithnoknok/Ecosystem/blob/main/mechanical/readme.md)

- **Enumeration Protocol**  
  Every I²C module must implement this. No hardcoded addresses.  
  → [Enumeration Protocol](https://github.com/buildwithnoknok/Ecosystem/blob/main/software/enumeration.md)

- **Reference Designs**  
  Use existing module repos as KiCad templates.  
  → [Module Index](#module-index)

- **Contribution Guide**  
  Want to publish your own module and earn from it?  
  [Contact the noknok Team](https://noknok.odoo.com/support#Contact-us)

---

## 3D Designer

You want to customize or create housings for noknok modules or kits?

**Start here:**

- **3D Housing Files**  
  Available inside each module repository under `/hardware/3d/`.

- **Mechanical Standards**  
  Mounting hole positions, PCB dimensions, clearances, tolerances, wall thickness recommendations.  
  → [Mechanical Guidelines](https://github.com/buildwithnoknok/Ecosystem/blob/main/mechanical/readme.md)

- **3D Printing Settings**  
  Layer height, infill, materials (PLA, PETG, TPU).  
  → [3D Printing Guidelines](https://github.com/buildwithnoknok/Ecosystem/blob/main/mechanical/3D_printed.md)

- **Module Index** — to find existing designs to modify  
  → [Module Index](#module-index)

---

## Builder

You bought a ready-made noknok kit and want to assemble it?

Visit [https://www.noknok.app](https://www.noknok.app) for tutorials, videos, and step‑by‑step instructions.

---

# Module Index

### I²C Modules

| Module | Description | Firmware | Repo |
|--------|-------------|----------|------|
| **noknok Buzzer** | I²C audio buzzer, 5 preloaded tunes, fire-and-forget | v3.2 ✅ | [module-I2C-buzzer](https://github.com/buildwithnoknok/module-I2C-buzzer) |
| **noknok Knob** | I²C rotary encoder with push button | v2.0 ✅ | [module-I2C-knob](https://github.com/buildwithnoknok/module-I2C-knob) |
| **noknok LED Button** | I²C tactile button with RGB LED backlight | v2.0 ✅ | [module-I2C-ledbutton](https://github.com/buildwithnoknok/module-I2C-ledbutton) |

### USB Modules

| Module | Description | Firmware | Repo |
|--------|-------------|----------|------|
| **noknok PicoHub** | Raspberry Pi Pico mount + I²C connectors | — | [module-usb-picohub](https://github.com/buildwithnoknok/module-usb-picohub) |
| **noknok PowerHub** | USB power distribution hub | — | [module-usb-powerhub](https://github.com/buildwithnoknok/module-usb-powerhub) |
| **noknok DataHub** | 4-port USB-C data hub (CH339) | — | [module-usb-datahub](https://github.com/buildwithnoknok/module-usb-datahub) |
| **noknok LEDs** | 8× WS2812b RGB LED ring, USB | pending | [module-usb-led](https://github.com/buildwithnoknok/module-usb-led) |

---

# Documentation

| Document | Description |
|----------|-------------|
| [Ecosystem Overview](https://github.com/buildwithnoknok/Ecosystem) | Root — architecture, goals, principles |
| [Electrical Guidelines](https://github.com/buildwithnoknok/Ecosystem/blob/main/electrical/readme.md) | Connectors, power, I²C, PCB design |
| [Mechanical Guidelines](https://github.com/buildwithnoknok/Ecosystem/blob/main/mechanical/readme.md) | PCB sizes, mounting, 3D printing |
| [Software Guidelines](https://github.com/buildwithnoknok/Ecosystem/blob/main/software/readme.md) | Languages, toolchain, firmware conventions |
| [Enumeration Protocol](https://github.com/buildwithnoknok/Ecosystem/blob/main/software/enumeration.md) | Full I²C module discovery & address assignment spec |
| [Python Library](https://github.com/buildwithnoknok/brain-Pico/tree/main/software) | `noknok.py` and Pico scripts |

---

# Contribute

Want to contribute a module, housing, or product to the noknok ecosystem?

Get in touch — we want to know what you're building.

**[Contact the noknok Team](https://noknok.odoo.com/support#Contact-us)**

---

Made with ❤️ in Switzerland.