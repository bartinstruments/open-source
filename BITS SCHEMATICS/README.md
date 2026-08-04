# b:art instruments - Open-Source b:its Schematics

Free, open-source KiCad schematics for the **b:bits** series of Eurorack utility modules by [b:art instruments](https://bartinstruments.com/). These are released to give back to the DIY / modular synth community — build them, learn from them, remix them.

## License

All files in this repository are released under **[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)** (Attribution–NonCommercial–ShareAlike).

That means you are free to:
- **Share** — copy and redistribute the material in any medium or format
- **Adapt** — remix, transform, and build upon the material

Under the following terms:
- **Attribution** — credit "b:art instruments" and link back to [bartinstruments.com](https://bartinstruments.com/)
- **NonCommercial** — you may not use this material for commercial purposes (no selling built modules, kits, or PCBs based on these designs without permission)
- **ShareAlike** — if you remix or build upon the material, you must distribute your contributions under the same license

This license notice is also embedded directly in the title block of every schematic sheet.

## Contents

Each PDF is a single-sheet schematic exported directly from the module's KiCad source (`.kicad_sch`). All schematics share the b:art instruments ±12V analog signal rail convention unless noted otherwise.

| File | Module | Description | Rev |
|---|---|---|---|
| `b01-vca.pdf` | b:01 — Dual VCA | Two independent voltage-controlled amplifiers (LM13700-based) for audio and linear CV level control. | 3.1 |
| `b02-bmult.pdf` | b:02 — Buffered Multiples | Splits input signals into multiple buffered copies, preventing signal loading when patching one output to many destinations. | 2.0 |
| `b03-mixer.pdf` | b:03 — Simple Mixer | Compact dual 3-into-1 summing mixer. | 2.1 |
| `b04-matrix-mixer.pdf` | b:04 — Dual 2:2 Matrix Mixer/Multiple | Flexible routing tool combining a 2x2 matrix mixer with switchable gain jumpers. | 2.0 |
| `b06-quick-maths.pdf` | b:06 — Quick Maths | Analog computing utility for CV/audio math - offsetting, inverting, and summing signals. | 2.0 |
| `b07-fixed-filter-bank.pdf` | b:07 — Fixed Filter Bank | A fixed filter bank consisting of two fixed low-pass filters and two fixed highpass filters. | 2.1 |
| `b08-cut-boost.pdf` | b:08 — Cut/Boost Utility | Four-channel gain stage offering fixed ±6 dB / ±12 dB boost or cut per channel for audio and CV gain control. | 3.0 |
| `b09-offset-crossfader.pdf` | b:09 — Offset + Attenuverter + Crossfader | Combines a CV offset generator, attenuverter, and crossfader in one dual-purpose utility module. | 2.1 |
| `b10-offset-slew.pdf` | b:10 — Offset + Attenuverter + Slew Limiter | Adds a slew limiter stage to offset/attenuverting utility functions for smoothing CV transitions. | 2.2 |
| `b12-quick-maths-2.pdf` | b:12 — Quick Maths 2 | Expanded analog math module with add/subtract/LM13700-based multiply/absolute-difference functions (A+B, A−B, \|A−B\|, A×B). | 2.0 |
| `b13-mutes.pdf` | b:13 — Quick Mutes | Dual-channel mute module built for live performance, with latching switches and CV-controlled muting per channel. | 1.0 |
| `b14-mixer-multiple.pdf` | b:14 — Mixer Multiple | Compact 4-in / 4-out mixer and multiple combo with switchable gain jumpers. | 1.0 |
| `b15-sample-hold.pdf` | b:15 — Sample & Hold + Noise + Utilities | Combines a sample & hold circuit, white noise generator, and signal inversion/utility functions in one module. | 2.0 |
| `b16-mmf.pdf` | b:16 — Multimode Filter | Dual multimode VCF (LP/BP/HP simultaneous outputs) built around LM13700 OTAs, with CV-controllable cutoff and resonance. | 1.0 |

> Note: module numbers b:05 and b:11 are intentionally absent - the b:05 is a passive multiple, simple enough to figure out. The b:11 is reserved for a module not yet released as open-source schematics.

## Format & Tools

- Source format: **KiCad** (`.kicad_sch`), exported here as single-page PDF schematics
- Reference designators follow the `bNN` numbering convention (e.g. `R14xx` belongs to b:04)
- All active analog stages use standard, easily sourced parts (TL074/TL072, LM13700, OPA1678, MMBT39xx transistors)

## Disclaimer

These schematics are provided as-is, for educational and personal (non-commercial) use. b:art instruments makes no warranty regarding fitness for any particular purpose. Build at your own risk — always double-check power rail polarity (±12V) before powering a freshly built PCB.

## Links

- Website: [bartinstruments.com](https://bartinstruments.com/)
- ModularGrid: [b:art instruments manufacturer page](https://modulargrid.net/e/vendors/view/1228)

---
*Handbuilt in Wrocław, Poland.* 🇵🇱
