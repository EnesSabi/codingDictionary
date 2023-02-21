# Assembler
## Usage
1. STM32G474 Nucleo with ARMv7-M Architecture
## Instructions
Instructions in ARMv7-M are typically written in lowercase and are composed of an opcode and zero or more operands. The ARMv7-M instruction set includes a wide range of instructions for data processing, control flow, memory access, and other tasks.
### Syntax
```asm
[Symbol]  command/statement/pseudocommand  [Operand1[,Operand2...]]  [;Comments]
```
[] is optional
### Symbol
A symbol is an optional label that you can use to mark a specific location in your code. A symbol is usually written in uppercase and followed by a colon ( : ) character. The symbol can be used later as a reference to that location in your code.
1. Symbols names jumps, constants or variables
2. Symbols must start without indentation
3. Must start with a letter or an underscore (could be a number between 0 - 99, but only local)
4. case sensitive!
### Command
This field represents the instruction or command that you want the processor to execute. In assembly language, each instruction or command is represented by an opcode, which is a unique binary code that the processor understands. Examples of instructions or commands include add, mov, jmp, etc.
1. need to use the Mnemonics from the manufactures
2. not case sensitve
### Operand
An operand is a value or a memory address that you want to operate on using the instruction or command. Some instructions require one or more operands, while others may not require any operands. Operands are separated by commas, and each operand can be a register, a memory location, an immediate value, or a label.
## Comments
Comments in ARMv7-M Assembly Language start with a semicolon ( ; ) and are used to provide explanations or documentation for the code.
## Labels
Labels are used to mark specific locations in the code that can be referred to later. In ARMv7-M Assembly Language, labels are identified by placing a colon ( : ) at the end of the label name, and the name is usually written in uppercase.
## Registers
Registers are identified by a name, such as R0, R1, R2, and so on. In ARMv7-M, there are 16 general-purpose registers, and these can be used for arithmetic and logical operations, as well as for holding memory addresses.
## Directives
Directives in ARMv7-M are identified by a dot ( . ) followed by a keyword, and are used to give instructions to the assembler. Some common directives in ARMv7-M include .section, .global, .word, and .byte.
## Example
```assembly
start:  ; Define a label called 'start'
        mov     r0, #0       ; Move the immediate value 0 into register R0
        ldr     r1, =data    ; Load the address of the 'data' variable into register R1
        add     r0, r0, r1   ; Add the value in R1 to the value in R0
        bx      lr           ; Return from the function

data:   .word   1234         ; Define a 32-bit word containing the value 1234

```