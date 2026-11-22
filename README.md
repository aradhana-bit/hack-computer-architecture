<div align="center">

# Hack Computer Architecture

**Nand to Tetris – I · ETCCNT301**

A hands-on implementation of the Hack computer architecture using HDL, Hack assembly, and Python.

[Capstone Project](capstone/) · [Setup & Testing Guide](capstone/README.md) · [Project Report](capstone/REPORT-TEMPLATE.md)

</div>

---

## About the project

This repository contains the capstone **“Make the Computer Draw a Box”**, developed as part of the Nand to Tetris – I course at K.R. Mangalam University.

| Component | Description |
|---|---|
| **Hardware** | Hack CPU, Memory, and complete Computer chips implemented in HDL |
| **Assembler** | A two-pass Hack assembler written in Python |
| **Assembly program** | A keyboard-controlled rectangle rendered on the Hack screen |
| **Verification** | Official Nand2Tetris test scripts and Python unit tests |

## Student details

| Field | Details |
|---|---|
| Name | S. Aradhana |
| Roll number | 2501010358 |
| Personal number | K = 58 |
| Course | Nand to Tetris – I (ETCCNT301) |
| University | K.R. Mangalam University |

## Personalized specifications

The assignment derives the additional assembler feature and rectangle dimensions from the personal number **K = 58**.

| Calculation | Result |
|---|---|
| K mod 3 | 1 — line-numbered assembler error messages |
| K mod 4 | 2 |
| Rectangle width | 48 pixels |
| Rectangle height | 20 rows |
| Starting row | 58 |
| Starting screen address | 18240 |

## Repository structure

~~~text
hack-computer-architecture/
├── README.md
└── capstone/
    ├── CPU.hdl
    ├── Memory.hdl
    ├── Computer.hdl
    ├── assembler.py
    ├── test_assembler.py
    ├── Box.asm
    ├── Box.hack
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
~~~

All assignment files are kept together in **one capstone/ directory** at the repository root. There is no second nested capstone/capstone/ directory.

## Quick start

Open a terminal in the capstone/ directory.

**Assemble the box program**

~~~bash
python assembler.py Box.asm
~~~

**Run the assembler unit tests**

~~~bash
python -m unittest -v test_assembler.py
~~~

For hardware verification, open the capstone/ directory in the Nand2Tetris Hardware Simulator and run the included test scripts. Load Box.hack in the CPU Emulator to test the keyboard-controlled rectangle.

## Documentation

- [Capstone setup and execution guide](capstone/README.md)
- [Capstone report template and evidence checklist](capstone/REPORT-TEMPLATE.md)
- [Official Nand2Tetris project materials](https://github.com/nand2tetris/projects)

## Verification status

The repository contains the project source files and official test assets. Hardware Simulator runs, official assembler comparisons, and CPU Emulator screenshots must be completed locally and recorded with genuine results. No simulator result is marked as passed before it has actually been verified.

---

<div align="center">

**K.R. Mangalam University**  
*School of Engineering & Technology*

</div>
