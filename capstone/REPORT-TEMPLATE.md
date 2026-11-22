# Capstone Project Report
## Make the Computer Draw a Box

**Name:** S. Aradhana  
**Roll number:** 2501010358  
**Course:** Nand to Tetris – I (ETCCNT301)  
**Personal number:** K = 58  
**School:** School of Engineering & Technology, K.R. Mangalam University

## 1. Project objective

The objective of this capstone is to build the Hack computer from its hardware components, implement a two-pass assembler in Python, and write a Hack assembly program that displays a black rectangular box while a keyboard key is pressed. The box must disappear when the key is released. The implementation is personalized using the last two digits of the roll number.

For roll number **2501010358**, the personal number is **K = 58**. Since 58 mod 3 = 1, the assembler's additional feature is line-numbered error reporting. Since 58 mod 4 = 2, the box width is 16 × (2 + 1) = **48 pixels**.

## 2. Part A — Build the computer

The hardware implementation is divided into three main chips.

- **CPU.hdl:** connects the A register, D register, ALU, program counter, instruction decoder signals, memory output, and jump-control logic. It produces the memory address, memory write signal, and program counter output.
- **Memory.hdl:** maps the RAM, screen memory, and keyboard memory-mapped input into one address space. The screen begins at address 16384 and the keyboard register is at address 24576.
- **Computer.hdl:** connects the CPU, ROM32K instruction memory, and Memory chip to form the complete Hack computer.

The official test scripts required by the assignment are listed below. Insert the screenshots captured from the Hardware Simulator after running each test.

| Official test | Actual result | Screenshot |
|---|---|---|
| CPU.tst | [Fill after running] | [Insert screenshot] |
| Memory.tst | [Fill after running] | [Insert screenshot] |
| ComputerAdd.tst | [Fill after running] | [Insert screenshot] |
| ComputerMax.tst | [Fill after running] | [Insert screenshot] |
| ComputerRect.tst | [Fill after running] | [Insert screenshot] |

**Built-in chips used instead of older lab chips:** [List only the chips actually used.]

## 3. Part B — Python assembler

The assembler translates Hack assembly instructions into 16-bit machine instructions. It uses two passes.

In the first pass, comments and blank lines are removed, original source line numbers are retained for error messages, and label declarations are recorded with their ROM addresses. Labels do not occupy ROM instruction addresses.

In the second pass, A-instructions are converted into 16-bit binary addresses and C-instructions are encoded using the destination, computation, and jump tables. Predefined symbols such as R0–R15, SCREEN, and KBD are supported. New variables receive RAM addresses beginning at 16 and are allocated in the order in which they first appear.

For K = 58, the required extra feature is clear error reporting. An invalid instruction produces a message containing its original source line number instead of an unhandled Python traceback.

The assembler includes automated unit tests for A-instruction encoding, C-instruction encoding, label resolution, variable allocation, line-numbered errors, and duplicate-label errors. Run the included unit tests with `python -m unittest -v` from this folder and record the actual result. Do not mark the tests as passed until they have been run.

**Official comparison results:** Run Add.asm, Max.asm, Rect.asm, and Pong.asm using this assembler. Compare each generated output with the official assembler output and record the actual result below.

| Program | Output matches official assembler? | Evidence / notes |
|---|---|---|
| Add.asm | [Yes/No] | [Add details] |
| Max.asm | [Yes/No] | [Add details] |
| Rect.asm | [Yes/No] | [Add details] |
| Pong.asm | [Yes/No] | [Add details] |

## 4. Part C — Box program

The box begins at row **58**, is **20 rows** tall, and is **48 pixels** wide. Each screen row contains 32 words, and each word represents 16 horizontal pixels. Therefore, the box occupies three words per row.

The first screen address is:

**SCREEN + 32 × K = 16384 + 32 × 58 = 18240**

The assembly program checks the keyboard register at KBD (24576). If its value is non-zero, the program writes -1 to three consecutive screen words for each of the 20 rows. A value of -1 sets all 16 pixels in a word to black. After writing three words, the screen pointer advances by another 29 words so that the next iteration begins exactly 32 words after the previous row's start.

If no key is pressed, the program writes 0 to the same 60 screen words, clearing the rectangle. It then repeats the keyboard check continuously.

**Box dimensions:** 48 pixels wide × 20 rows high  
**Top-left screen row:** 58  
**First screen address:** 18240

**CPU Emulator screenshot — key pressed:** [Insert genuine screenshot]

**CPU Emulator screenshot — key released:** [Insert genuine screenshot]

## 5. Mistake fixed during development

While implementing the memory map, the initial four-way decoder output mapping assigned the screen and one RAM bank to the wrong decoder outputs. This would cause addresses in the screen range to select the wrong memory component. I corrected the mapping so that the two RAM address ranges select RAM, addresses 16384–24575 select the Screen chip, and addresses 24576 and above select the Keyboard input. This correction keeps the memory-mapped address ranges aligned with the Hack computer specification.

## 6. Conclusion

This capstone combines digital logic, computer architecture, assembly language, and Python programming. The personalized assembler, hardware description files, and keyboard-controlled box program are included in the project repository. The final submission should include the genuine Hardware Simulator test screenshots, official assembler comparison results, and CPU Emulator screenshots recorded after completing the tests locally.
