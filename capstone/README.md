# Capstone Project — Make the Computer Draw a Box

**Course:** Nand to Tetris – I (ETCCNT301)  
**Student:** S. Aradhana  
**Roll number:** 2501010358  
**Personal number:** K = 58

---

## 1. Project requirements

| Requirement | Personalized value |
|---|---|
| K mod 3 | 1 — report invalid instructions with their original source line number |
| K mod 4 | 2 |
| Box width | 48 pixels |
| Box height | 20 rows |
| Top row | 58 |
| First screen address | 18240 |

The first screen address is calculated as:

~~~text
16384 + (32 × 58) = 18240
~~~

Each screen row contains 32 words. The program writes three consecutive 16-bit words per row (48 pixels), then advances to the next row.

## 2. Project files

| File | Purpose |
|---|---|
| CPU.hdl | Hack CPU implementation |
| Memory.hdl | RAM, screen, and keyboard memory map |
| Computer.hdl | Complete Hack computer connection |
| assembler.py | Two-pass Hack assembler |
| test_assembler.py | Automated assembler unit tests |
| Box.asm | Keyboard-controlled rectangle program |
| Box.hack | Machine code for Box.asm |
| *.tst / *.cmp | Official Hardware Simulator test scripts and comparison files |
| Add.hack, Max.hack, Rect.hack | Official Project 5 comparison programs |
| REPORT-TEMPLATE.md | Capstone report and evidence checklist |

## 3. Run the assembler

Open a terminal in this directory.

~~~bash
python assembler.py Box.asm
~~~

The command generates Box.hack in the same directory.

## 4. Run assembler unit tests

~~~bash
python -m unittest -v test_assembler.py
~~~

The tests cover instruction encoding, labels, variable allocation, line-numbered errors, duplicate labels, and malformed C-instructions. Record the actual test output in your report.

To verify the personalized error feature, assemble a file containing an invalid instruction. The assembler should display the original source line number instead of an unhandled Python traceback.

## 5. Verify the hardware

Open this directory in the Nand2Tetris Hardware Simulator and run:

1. CPU.tst
2. Memory.tst
3. ComputerAdd.tst
4. ComputerMax.tst
5. ComputerRect.tst

Each test uses its corresponding .cmp file. Save a genuine screenshot after each successful run and add it to the report.

## 6. Compare the assembler with the official assembler

Download the official Project 6 source programs:

- [Add.asm](https://github.com/nand2tetris/projects/tree/main/projects/06/add)
- [Max.asm](https://github.com/nand2tetris/projects/tree/main/projects/06/max)
- [Rect.asm](https://github.com/nand2tetris/projects/tree/main/projects/06/rect)
- [Pong.asm](https://github.com/nand2tetris/projects/tree/main/projects/06/pong)

Place each .asm file in this directory, run it through assembler.py, and compare the generated .hack output with the official assembler output. Record the actual results in the report.

## 7. Run the box program

1. Open the Hack CPU Emulator.
2. Load Box.hack.
3. Press any key. A black rectangle should appear from the left edge, starting at row 58, with a width of 48 pixels and a height of 20 rows.
4. Release the key. The rectangle should disappear.
5. Capture screenshots for both states and include them in the report.

## 8. Submission checklist

- [ ] CPU, Memory, and Computer HDL files included
- [ ] Python assembler and unit tests included
- [ ] Box.asm and Box.hack included
- [ ] All five official Hardware Simulator tests run
- [ ] Official assembler comparison completed for Add, Max, Rect, and Pong
- [ ] CPU Emulator screenshots captured for key pressed and released
- [ ] Report completed with genuine test results and screenshots

**Important:** The repository contains the source files and official test assets. Hardware Simulator runs, official assembler comparisons, and CPU Emulator screenshots must be performed locally. Do not mark a test as passed until it has actually been run.
