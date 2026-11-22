# Hack Computer Architecture

A hands-on implementation of the **Hack computer** from the *Nand2Tetris* course. This repository contains the hardware description files, assembler implementation, and capstone program developed for **Nand to Tetris – I (ETCCNT301)**.

## Capstone: Make the Computer Draw a Box

The capstone is maintained in the `capstone/` directory.

### Project overview

| Component | Description |
|---|---|
| Hardware | Hack CPU, Memory, and complete Computer chips in HDL |
| Assembler | Two-pass Hack assembler implemented in Python |
| Custom program | Keyboard-controlled rectangle drawing program |
| Tests | Official Nand2Tetris Hardware Simulator test scripts and comparison files |
| Documentation | Setup instructions, test checklist, and project report template |

### Personalized specification

- **Student:** S. Aradhana
- **Roll number:** 2501010358
- **K:** 58
- **Assembler extension:** Report invalid instructions with their original source line number (`K mod 3 = 1`).
- **Box dimensions:** 48 pixels wide × 20 rows high (`K mod 4 = 2`).
- **Top row:** 58
- **Starting screen address:** 18240

## Repository structure

```text
hack-computer-architecture/
└── capstone/
    ├── assembler.py
    ├── test_assembler.py
    ├── CPU.hdl
    ├── Memory.hdl
    ├── Computer.hdl
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
```

## Quick start

Open a terminal in the `capstone/` directory.

Assemble the box program:

```bash
python assembler.py Box.asm
```

Run the assembler unit tests:

```bash
python -m unittest -v test_assembler.py
```

For hardware verification, open the `capstone/` directory in the Nand2Tetris Hardware Simulator and run the included `.tst` scripts. Use the CPU Emulator to test `Box.hack`.

## Documentation

See [capstone/README.md](capstone/README.md) for detailed setup and testing instructions, and [capstone/REPORT-TEMPLATE.md](capstone/REPORT-TEMPLATE.md) for the submission report structure.

## Verification status

The source files and official test assets are included in the repository. Hardware Simulator runs, official assembler comparisons, and CPU Emulator screenshots must be completed locally and documented with genuine results. No local simulator result is claimed here unless it has actually been run.

---

**Course:** Nand to Tetris – I (ETCCNT301)  
**University:** K.R. Mangalam University
