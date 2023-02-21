# Assembly
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
### Comments
Comments in ARMv7-M Assembly Language start with a semicolon ( ; ) and are used to provide explanations or documentation for the code.
### Labels
Labels are used to mark specific locations in the code that can be referred to later. In ARMv7-M Assembly Language, labels are identified by placing a colon ( : ) at the end of the label name, and the name is usually written in uppercase.
### Registers
Registers are identified by a name, such as R0, R1, R2, and so on. In ARMv7-M, there are 16 general-purpose registers, and these can be used for arithmetic and logical operations, as well as for holding memory addresses.
### Directives
Directives in ARMv7-M are identified by a dot ( . ) followed by a keyword, and are used to give instructions to the assembler. Some common directives in ARMv7-M include .section, .global, .word, and .byte.
### Example
```asm
start:  ; Define a label called 'start'
        mov     r0, #0       ; Move the immediate value 0 into register R0
        ldr     r1, =data    ; Load the address of the 'data' variable into register R1
        add     r0, r0, r1   ; Add the value in R1 to the value in R0
        bx      lr           ; Return from the function

data:   .word   1234         ; Define a 32-bit word containing the value 1234
```
In this example, the first line defines a label called 'start'. The subsequent lines contain instructions or commands that use various operands to perform operations on registers or memory. Finally, there is a data definition that uses the pseudo command .word to define a 32-bit word containing the value 1234.
## Assembly - Directives
Directives don't create Machine-Code
There are different types of directives: 
1. Control directives for the assembler
2.for defining symbols
3. for data defining and reservation of memory
### important ARM directives
#### Sections/Area
The Syntax is: 
```asm
AREA <sectionname>[,<attributes>, ...]
```
##### defined section and usage
1. CODE: code-section (default: readonly)
2. DATA: data-section (default: readwrite)
3. READONLY (for code and constants)
4. READWRITE (for data and variables)
Example:
```asm
AREA const, DATA, readwrite variable DCB 0

AREA main_s, CODE, readonly
    ldr r2, =variable
    ldr r3, [r2]
```
#### Reservation/Initialisation of Memory
1. [label] DCB value [,[value]]
1.1 initialize memory with a Byte (8Bit)
1.2 with a label it can be referenced
1.3 initialization of a constant must be immediatly after
2. [label] DCW value [,[value]]
like DCB, but with 2 Bytes (16-Bit)(half-world)
3. [label] DCD value [,[value]]
like DCB, but with 4 Bytes (32-Bit)(word)
4. Example for 1-3:
```asm
AREA variables, DATA
    var1 DCB 64, 'A'
    var2 DCW 0x1234
    var3 DCD 0x12345678
AREA main, CODE
    ldr r0, =var1
    ldr r1, [r0]    ;r1 = var1
```
5. ALIGN [number]
5.1 alignes the object to the number in the memory
5.2 the number should be 2^n (if no number is given: 4)
5.3 default: next free memorycell
5.4 Gaps should be filled with NOPS (no operation)
#### constants
label EQU value
Expample: 
```asm
wert EQU 0x0000
ldr r0, =wert
```
#### conditions
```asm
IF <logical expression/ boolean>
    ... ; code
[Else 
    ... ; code]
ENDIF
```
| operator | meaning |
|----------|---------|
| < | less then |
| <= | less then or equal |
| > | greater than |
| >= | greater than or equal |
|==| equal |
|!=| not equal |

##### Example:
```asm
Alternate EQU 2

IF Alternate == 2
    add r0, r1
ELSE
    sub r0, r1
ENDIF
```
#### more directives
1. INCLUDE filename
GET filename
```asm
INCLUDE STM32G4xx_REG_ASM.inc
```
2. PROC - ENDP (explained later)
3. UNCTION - ENDFUNC (explained later)
4. END is the end of the assemblyfile
5. GLOBAL Symbol
6. EXPORT Symbol
7. EXTERN Symbol
8. Example 5-7:
    file1.s
    ```asm
    AREA vars, data
    extvar DCB 0x12
    GLOBAL extvar
    ```
    file2.s
    ```asm
    EXTERN extvar
    ...
    AREA main, code
    ldr r0, =extvar
    ldr r1, [r0]
    ```
## Aritmetic and Logic
1. addition : ADD Rd, Rn, Rm (Rd <- Rn + Rm)
2. subtraction:  SUB Rd, Rn, Rm (Rd <- Rn - Rm)
3. multiplication: MUL Rd, Rn, Rm (Rd <- Rn * Rm)(32-Bit Result!)
4. bitwise OR: ORR Rd, Rn, Rm (Rd <- Rn or Rm)(logical or)
5. bitwise AND: AND Rd, Rn, Rm (Rd <- Rn and Rm)(logical and)
6. bit clear: BIC Rd, Rn, Rm (Rd <- Rn and !Rm)
7. bitwise XOR: EOR Rd, Rn, Rm (Rd <- Rn + Rm)(logical exclusive or)
8. bitwise negation: MVN Rd, Rs (Rd <- !Rn)
## Branch commands
1. Sprünge
1.1 (absolute) B label (PC <- Addr(label))
1.2 (indirekt) BX Rm (PC <- [Rm])
2. UP Aufruf
2.1 (absolute) BL label (PC <- Addr(label))
2.2 (indirekt) BLX Rm (PC <- [Rm])
3. Vergleiche CMP R1, R2 (R1 - R2)
4. conditional jumps
4.1 BNE label
4.2 BEQ label
4.3 BPL label
4.4 BMI label


