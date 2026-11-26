# b:art instruments AUDIO CORE

STM32H723-based digital audio submodule for the **b:ounce** multi-effect Eurorack module. The AUDIO CORE holds every digital signal in the system (microcontroller, external memory, clocks and digital-domain power).

> **Revision:** 1.1 (2026-11-26) | **Status:** production-ready schematics | **License:** CC-BY-NC-SA

## Overview

The AUDIO CORE is a compact DSP platform built around an STM32H723ZGT6. It was designed for long, dense reverbs and modulated delays that need far more compute and memory than many effects chips offer.

| Resource | Specification |
|----------|---------------|
| Microcontroller | STM32H723ZGT6 (Arm Cortex-M7, floating-point, DSP instructions, LQFP-144) |
| Core clock | 550 MHz |
| Audio format | 24-bit, 48 kHz stereo |
| Compute budget | About 11,000 clock cycles per audio sample (550 MHz / 48 kHz) |
| External RAM | IS42S16160J SDRAM, 16M x 16 (256 Mbit, 32 MB) |
| Audio buffer | About 87 seconds of stereo audio |
| Flash | W25Q64 QSPI NOR flash, 64 Mbit (8 MB) |
| Non-volatile settings | 24LC64 I2C EEPROM, 64 kbit |
| Audio clock | 12.288 MHz crystal for the I2S / SAI master clock |
| MCU clock | 16 MHz crystal |
| Connector | M.2-style 75-pin edge connector (XP101) |
| Debug | Tag-Connect TC2030 serial-wire debug |

## What it does

The AUDIO CORE runs the b:ounce effect engine: a clean delay, a tape delay, a hall-leaning reverb and a spectral reverb. It plugs into the b:ounce carrier board, which provides the analog audio chain, codec, controls and power.

### Power

- **+5V** enters from the carrier through the edge connector.
- **+3V3 (digital):** TPS62840 step-down converter.
- **+3.3VA (analog):** TLV75533 LDO with a ferrite bead filter for the MCU analog supply (VDDA).
- **VBUS** from the carrier's USB-C (VBUS_DET).
- LED power indication.

> **Mandatory on the carrier board:** if VBUS is used as a power source, the carrier must include a diode-OR between VBUS and +5V, as noted on the schematic. The b:ounce carrier board already includes this.

## Edge connector (XP101)

The AUDIO CORE connects to the carrier through a 75-pin M.2-style key B edge connector. Signal groups routed through XP101:

| Group | Signals |
|-------|---------|
| Power | +5V, VBUS, GND |
| Audio (SAI) | MCLK, SCK, FS, SD_A, SD_B |
| Clock | I2S_CKIN |
| Analog inputs (ADC) | Pot and CV channels |
| Digital I/O | LEDs, buttons, clock input, expander and general GPIO |
| Communication | I2C, USB D+ / D- |
| Debug | SWDIO, SWCLK, SWO, NRST |

The full XP101 pin assignments are in the KiCad project.

## Firmware

No firmware is included in this repository. Firmware and settings are managed through the [b:art instruments web configurator](https://flash.bartinstruments.com/) over USB-C.

## Debugging

- **SWD:** TC2030 Tag-Connect header (J101) with SWDIO, SWCLK, SWO and NRST.
- **USB:** D+/D- routed to the carrier's USB-C port.

## Related repositories

- [**b:ounce carrier board**](https://github.com/bartinstruments/open-source/tree/main/BOUNCE%20MULTIEFFECT): host board for this submodule.

## Repository contents

- KiCad project (`STM32H723ZGT6.kicad_sch` and related files).
- PDF schematic export.

## License

Copyright applies to every part of this repository and to the product. Released under **CC-BY-NC-SA**. Commercial use requires permission.

For commercial inquiries: [bart@bartinstruments.com](mailto:bart@bartinstruments.com)