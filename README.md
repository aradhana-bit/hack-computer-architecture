<div align="center">

# Hack Computer Architecture

**Nand to Tetris – I · ETCCNT301**

A hands-on implementation of the Hack computer architecture using HDL, Hack assembly, and Python.

</div>

---

## Overview

This repository contains the capstone project **“Make the Computer Draw a Box”**, developed for Nand to Tetris – I at K.R. Mangalam University.

| Component | Description |
|---|---|
| Hardware | Hack CPU, Memory, and complete Computer chips implemented in HDL |
| Assembler | Two-pass Hack assembler written in Python |
| Assembly program | Keyboard-controlled rectangle rendered on the Hack screen |
| Verification | Official Nand2Tetris test scripts and Python unit tests |

## Student details

| Field | Details |
|---|---|
| Name | S. Aradhana |
| Roll number | 2501010358 |
| Personal number | K = 58 |
| Course | Nand to Tetris – I (ETCCNT301) |
| University | K.R. Mangalam University |

## Personalized specifications

| Calculation | Result |
|---|---|
| K mod 3 | 1 — line-numbered assembler error messages |
| K mod 4 | 2 |
| Rectangle width | 48 pixels |
| Rectangle height | 20 rows |
| Starting row | 58 |
| Starting screen address | 18240 |

The starting address is calculated as `16384 + (32 × 58) = 18240`. The program writes three 16-bit words per row, then advances to the next screen row.

## Repository structure

All project files are kept directly in the repository root for easy access.

```text
hack-computer-architecture/
├── README.md
├── CPU.hdl
├── Memory.hdl
├── Computer.hdl
├── assembler.py
├── test_assembler.py
├── Box.asm
├── Box.hack
├── Add.hack
├── Max.hack
├── Rect.hack
├── CPU.tst
├── CPU.cmp
├── Memory.tst
├── Memory.cmp
├── ComputerAdd.tst
├── ComputerAdd.cmp
├── ComputerMax.tst
├── ComputerMax.cmp
├── ComputerRect.tst
├── ComputerRect.cmp
└── REPORT-TEMPLATE.md
```

## Quick start

Run these commands from the repository root.

**Assemble the box program**

```bash
python assembler.py Box.asm
```

**Run assembler unit tests**

```bash
python -m unittest -v test_assembler.py
```

For hardware verification, open this repository folder in the Nand2Tetris Hardware Simulator and run `CPU.tst`, `Memory.tst`, `ComputerAdd.tst`, `ComputerMax.tst`, and `ComputerRect.tst`. Load `Box.hack` in the CPU Emulator to test the keyboard-controlled rectangle.

## Documentation and resources

- [Project report template and evidence checklist](REPORT-TEMPLATE.md)
- [Official Nand2Tetris project materials](https://github.com/nand2tetris/projects)

## Verification status

The repository includes source files and official test assets. Hardware Simulator runs, official assembler comparisons, and CPU Emulator screenshots must be completed locally and recorded with genuine results. No simulator result is marked as passed before it has actually been verified.

---

<div align="center">

**K.R. Mangalam University**  
*School of Engineering & Technology*

</div>
