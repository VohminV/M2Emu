# M2Emu

### Open-Source Emulator for the Panasonic 3DO M2 Platform

[![Project Status](https://img.shields.io/badge/status-research%20%26%20development-orange)]()
[![Platform](https://img.shields.io/badge/platform-Panasonic%203DO%20M2-blue)]()
[![Architecture](https://img.shields.io/badge/architecture-PowerPC%20602-green)]()
[![Language](https://img.shields.io/badge/language-C%2B%2B-blue)]()
[![License](https://img.shields.io/badge/license-TBD-lightgrey)]()

**M2Emu** is an open-source research and development project dedicated to building an accurate, modular emulator for the Panasonic 3DO M2 gaming platform.

The project aims to preserve the M2 hardware and software ecosystem by researching its architecture, documenting undocumented components, implementing hardware emulation, and achieving compatibility with original M2 software.

---

## Project Overview

The Panasonic 3DO M2 is a relatively obscure gaming platform developed in the 1990s. Although it was intended to succeed the original 3DO Interactive Multiplayer, the platform never received a conventional worldwide consumer release.

Despite its limited commercial availability, M2 featured an advanced hardware architecture, PowerPC processors, dedicated graphics hardware, and multimedia capabilities.

A significant portion of its technical documentation and software ecosystem remains difficult to access or incompletely documented.

**M2Emu aims to address this gap.**

The project combines hardware research, software reverse engineering, and emulator development to create an accessible implementation of the platform.

## Project Goals

- Reconstruct the M2 hardware architecture.
- Implement accurate emulation of the PowerPC 602 processors.
- Research and emulate the M2 graphics subsystem.
- Reconstruct memory mapping and system bus behavior.
- Implement peripheral and interrupt controllers.
- Investigate audio and multimedia subsystems.
- Understand the BIOS and boot process.
- Support original M2 executable formats and game media.
- Achieve compatibility with original M2 software.
- Establish a documented and reproducible development environment.

## Target Hardware Architecture

The emulator is intended to reproduce the major components of the Panasonic 3DO M2 platform.

| Component | Responsibilities | Status |
|---|---|---|
| PowerPC 602 | CPU instruction execution | Research |
| Dual CPU configuration | Processor coordination | Research |
| BDA | Graphics processing | Research |
| CDE | Peripheral and system control | Research |
| Bridgette | System logic and memory interfaces | Research |
| DSP | Audio processing | Research |
| MPEG subsystem | Multimedia decoding | Research |
| Memory subsystem | RAM, ROM and address mapping | Research |
| CD-ROM subsystem | Game media access | Research |
| Interrupt system | Hardware interrupt handling | Research |

*Hardware implementation details and component boundaries will be refined as documentation and hardware research progress.*

## Planned Emulator Architecture

The project is designed around a modular architecture.

```text
M2Emu/
├── src/
│   ├── core/
│   │   ├── emulator/
│   │   ├── scheduler/
│   │   └── state/
│   │
│   ├── cpu/
│   │   ├── powerpc602/
│   │   ├── mmu/
│   │   └── cache/
│   │
│   ├── hardware/
│   │   ├── bda/
│   │   ├── cde/
│   │   ├── bridgette/
│   │   ├── dsp/
│   │   └── memory/
│   │
│   ├── media/
│   │   ├── cdrom/
│   │   ├── iso/
│   │   └── formats/
│   │
│   ├── system/
│   │   ├── bios/
│   │   ├── boot/
│   │   └── portfolio/
│   │
│   ├── audio/
│   ├── video/
│   └── frontend/
│
├── docs/
│   ├── architecture/
│   ├── hardware/
│   ├── cpu/
│   ├── graphics/
│   ├── audio/
│   ├── memory/
│   ├── formats/
│   ├── reverse-engineering/
│   └── research/
│
├── tests/
│   ├── cpu/
│   ├── memory/
│   ├── hardware/
│   └── compatibility/
│
├── tools/
├── third_party/
├── CMakeLists.txt
├── LICENSE
└── README.md
```

## Research Areas

### 1. CPU Emulation

Research and implementation of the PowerPC 602 architecture.

Key areas:

- PowerPC instruction set.
- Dual-processor configuration.
- MMU and address translation.
- Instruction and data caches.
- Exceptions and interrupts.
- Processor synchronization.
- Hardware bus interactions.

### 2. Graphics Emulation

Research and reconstruction of the M2 BDA graphics subsystem.

Key areas:

- Graphics registers.
- Command processing.
- Triangle rasterization.
- Texture mapping and filtering.
- Z-buffer operations.
- Alpha blending.
- Shading.
- Framebuffer management.
- Video output.

### 3. System Hardware

Investigation of the platform's internal hardware.

Key areas:

- Bridgette system logic.
- CDE peripheral controller.
- Memory mapping.
- DMA operations.
- Interrupt routing.
- System buses.
- Hardware initialization.

### 4. Audio and Multimedia

Research into the M2 audio and multimedia architecture.

Key areas:

- DSP instruction set.
- Audio processing.
- Audio DMA.
- MPEG decoding.
- Multimedia synchronization.

### 5. System Software

Research into the M2 boot process and software environment.

Key areas:

- BIOS and ROM.
- Portfolio OS.
- Bootloader.
- System libraries.
- Device drivers.
- Executable loading.
- Runtime environment.

### 6. Game Compatibility

Support for original software and media formats.

Key areas:

- CD-ROM images.
- ISO and BIN formats.
- ELF executables.
- Game resources.
- Textures and graphics.
- Audio and video assets.
- Original game compatibility testing.

## Development Roadmap

| Phase | Objective | Status |
|---|---|---|
| 01 | Documentation and research | In progress |
| 02 | Hardware architecture reconstruction | Planned |
| 03 | PowerPC 602 implementation | Planned |
| 04 | Memory subsystem | Planned |
| 05 | BIOS execution and boot process | Planned |
| 06 | Dual CPU synchronization | Planned |
| 07 | BDA graphics implementation | Planned |
| 08 | Audio and multimedia | Planned |
| 09 | CD-ROM and software loading | Planned |
| 10 | Portfolio OS compatibility | Planned |
| 11 | Original game compatibility | Planned |
| 12 | Accuracy and performance improvements | Planned |

The roadmap is subject to change as new technical information becomes available.

## Research Resources

The following projects and resources are relevant to M2Emu development:

- [3DO Development Repository](https://www.3dodev.com/) — historical documentation and development resources.
- [MAME](https://github.com/mamedev/mame) — existing hardware emulation research and M2 implementation.
- [M2Suite](https://github.com/Hackinside/M2Suite) — M2 media analysis and reverse-engineering tools.
- [PowerPC Documentation](https://www.nxp.com/) — processor architecture and technical references.
- [Emulation General Wiki](https://emulation.gametechwiki.com/) — emulation research and compatibility information.

## Research and Documentation Principles

M2Emu follows several important principles:

1. **Accuracy over shortcuts** — hardware behavior should be implemented based on technical evidence.
2. **Modularity** — each hardware component should be independently testable.
3. **Documentation first** — undocumented behavior must be recorded and investigated.
4. **Reproducibility** — research findings and test results should be repeatable.
5. **Compatibility** — original software should be used as the primary validation target.
6. **Transparency** — incomplete implementations and known limitations must be clearly documented.

## Contributing

Contributions are welcome in the following areas:

- Hardware documentation.
- Technical research.
- Reverse engineering.
- PowerPC 602 development.
- Graphics and audio emulation.
- BIOS and operating system analysis.
- Test cases and compatibility reports.
- Code review and performance optimization.

Before contributing major architectural changes, please open an issue to discuss the proposed implementation.

## Legal Notice

M2Emu is an independent, community-driven research and preservation project.

Panasonic, 3DO, and other referenced trademarks and product names belong to their respective owners.

This project is not affiliated with, endorsed by, or sponsored by Panasonic or The 3DO Company.

Original BIOS files, firmware, proprietary SDKs, and commercial game data are not distributed with this project.

Users are responsible for obtaining and using any proprietary software in accordance with applicable laws.

## Project Status

**Current focus: Hardware research, documentation collection, and emulator architecture design.**

The project is in its early research and development stage. No claim of complete hardware emulation or commercial game compatibility is currently made.

---

**M2Emu — Preserving the Panasonic 3DO M2 platform through open-source emulation.**
