# Capstone Project Report — Make the Computer Draw a Box

**Name:** S. Aradhana  
**Roll number:** 2501010358  
**Course:** Nand to Tetris – I (ETCCNT301)  
**Personal number:** K = 58

## 1. Personalized box

- Top row: 58
- Height: 20 rows
- Width: 48 pixels (3 words per row)
- Starting screen address: 18240
- K mod 3 = 1: line-numbered assembler error reporting

## 2. Part A — Hardware implementation

Describe how CPU.hdl, Memory.hdl, and Computer.hdl connect the ALU, registers, program counter, RAM, screen, keyboard, and ROM.

**Official test evidence to insert:**
- CPU.tst — [Insert your successful simulator screenshot]
- Memory.tst — [Insert your successful simulator screenshot]
- ComputerAdd.tst — [Insert your successful simulator screenshot]
- ComputerMax.tst — [Insert your successful simulator screenshot]
- ComputerRect.tst — [Insert your successful simulator screenshot]

**Built-in chips used instead of older lab chips (if any):** [List them here.]

## 3. Part B — Python assembler

The assembler uses two passes. The first pass removes comments and blank lines and records label addresses. The second pass translates A-instructions and C-instructions into 16-bit machine instructions. New variables are allocated from RAM address 16. For this roll number, invalid instructions and symbols produce a clear message containing the original source line number.

**Assembler test results:** [Record the Add.asm, Max.asm, Rect.asm, and Pong.asm comparisons against the official assembler.]

## 4. Part C — Box program

The program checks the keyboard memory-mapped register. If a key is pressed, it writes -1 into three consecutive screen words on each of 20 rows. If no key is pressed, it writes 0 to the same addresses. After three words, the pointer advances by 29 more words, making the next row 32 words after the previous row.

**Insert CPU Emulator screenshot with key pressed:** [Screenshot]  
**Insert CPU Emulator screenshot after key release:** [Screenshot]

## 5. One mistake fixed

[Write one real mistake you encountered, how you identified it, and the exact change that fixed it. Do not invent a debugging story.]

## 6. Conclusion

[Briefly state what you implemented and which simulator tests you successfully completed.]
