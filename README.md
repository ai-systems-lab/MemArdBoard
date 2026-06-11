# MemArdBoard

**An open-architecture, Arduino-compatible system for working with memristive devices.**

MemArdBoard is a low-cost, open hardware platform that lets researchers, educators, and enthusiasts study memristive devices and run hardware artificial neural network (ANN) models on them — using only an Arduino UNO (or a compatible board) and a personal computer. It is designed to lower the barrier to entry into memristor research, which normally requires expensive instrumentation such as probe stations or dedicated characterisation platforms.

The system is operated through **[MemriBoard](https://github.com/neurocomputer/MemriBoard)**, an open-source, cross-platform application (Windows, Linux, macOS) that provides the full functionality required for memristor experiments. You can also write your own software and communicate with the hardware over its open protocol.

---

## Boards

The hardware is mounted on an Arduino UNO (or a pin-compatible board) and consists of two stacked PCBs:

- **Signal board** — handles signal generation and read-out. Suitable for working with individual memristive cells. Built around SPDT analog switches, a 12-bit DAC (MCP4921), an op-amp buffer/amplifier stage (AD8616), and an ADC for the read path.
- **Switching board** — routing/commutation circuit for addressing arrays. Suitable for working with active **1T1R crossbar arrays** (up to 32×8) via analog multiplexers and shift-register control.

---

## Key characteristics

- 12-bit DAC (MCP4921), 1 channel
- 14-bit ADC (TLC3541) or 10-bit Arduino UNO built-in ADC, 1 channel
- Operation with a single selected cell, or with crossbar arrays / discrete memristive devices
- Pulsed-mode operation ("write" and "read" pulses)
- Maximum "write" voltage: 3 V (up to 5 V)
- Maximum allowable "write" current: up to 40 mA
- Connectable hardware current limiter for SET (2 mA)
- Crossbar array connection via a contacting device (UK64-4S or ICS-CQFP64-1830-1830-100-1)
- USB connection to a computer
- Mains power supply: 220 V, 50 Hz
- Highest measurement accuracy in the 1–10 kΩ resistance range (relative error below ~1%)

---

## Repository contents

| Path | Description |
|------|-------------|
| `signal-board/gerbers/` | Gerber files for the signal board (for PCB manufacturing) |
| `signal-board/schematic/` | Schematic of the signal board (PDF + source) |
| `commutation-board/gerbers/` | Gerber files for the switching board |
| `commutation-board/schematic/` | Schematic of the switching board (PDF + source) |
| `docs/` | Additional documentation, images, BOM |

> Source files were created in **EasyEDA Pro**.

*(Adjust the paths above to match your actual folder layout.)*

---

## Getting started

1. Order the two PCBs from any fab house using the Gerber files in this repository.
2. Assemble the boards according to the schematics and the bill of materials (`docs/BOM`).
3. Stack the boards onto an Arduino UNO (or compatible).
4. Install the **[MemriBoard](https://github.com/neurocomputer/MemriBoard)** software and connect the board over USB.

---

## Related repositories

- **MemriBoard** — control software: `(https://github.com/neurocomputer/MemriBoard)`


---
 
## License
 
This project is released under the **MIT License**. You are free to use, modify, and distribute the design files and software, including for commercial purposes, provided that the original copyright notice and license text are retained. See [`LICENSE`](LICENSE) for the full text.
 
---
