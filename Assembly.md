# Assembly
## Usage
1. STM32G474 Nucleo with ARMv7-M Architecture
2. KEILv5 uVision IDE for ARM
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
Directives aren't Machine-Code.
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
    EXPORT main
    ...
    AREA main, code
    ldr r0, =extvar
    ldr r1, [r0]
    ```
## Commandgroups
### Aritmetic and Logic
| command | Parameter | Function |name|
|-|-|-|-|
| ADD | Rd, Rn, Rm | Rd <- Rn + Rm |addition|
| SUB | Rd, Rn, Rm | Rd <- Rn - Rm | subtraction |
| MUL | Rd, Rn, Rm | Rd <- Rn * Rm | multiplication 32-Bit Result! |
| ORR | Rd, Rn, Rm | Rd <- Rn or Rm | bitwise OR / logical or |
| AND | Rd, Rn, Rm | Rd <- Rn and Rm | bitwise AND / logical and |
| BIC | Rd, Rn, Rm | Rd <- Rn and !Rm | bit clear |
| EOR | Rd, Rn, Rm | Rd <- Rn + Rm | bitwise XOR / logical exclusive or|
| MVN | Rd, Rs | Rd <- !Rn | bitwise negation |
### Branch commands
1. Jumps
1.1 (absolute) B label (PC <- Addr(label))
1.2 (indirekt) BX Rm (PC <- [Rm])
2. UP call
2.1 (absolute) BL label (PC <- Addr(label))
2.2 (indirekt) BLX Rm (PC <- [Rm])
3. compare CMP R1, R2 (R1 - R2)
4. conditional jumps
4.1 BNE label (PC <- Addr(label))
4.2 BEQ label (PC <- Addr(label))
4.3 BPL label (PC <- Addr(label))
4.4 BMI label (PC <- Addr(label))
### Data Transfer and manipulation
| command | Parameter | Function |name|
|-|-|-|-|
| MOV | Rd, Rs | Rd <- Rs | Load from Register |
| MOV | Rd, #const | Rd <- #const | Load from constant |
| LDR | Rd, =const | Rd <- #const | alternative MOV |
| LDR | Rd, [Rn, #offset] | Rd <- SRAM(Rn+#offset) | Load from RAM |
| STR | Rd, [Rn, #offset] | SRAM(Rn+#offset) <- Rd | Save in RAM |
| POP | {R1} | R1 <- STACK | Load from Stack |
| PUSH | {R1} | STACK <- R1 | Save in Stack |

More are in the _Mikrocomputertechnik – Befehlsübersicht THUMB2/Cortex-M3_ by _Prof. Dr. Peter Raab_ at _university of applied sciences Coburg_, licensed under CC BY-SA 4.0 https://creativecommons.org/licenses/by-sa/4.0/.
The Cheat Sheet is on my GitHub Page.

## Ports of STM32G4
### GPIO
The GPIO (general purpose input/output) tells if an I/O Pin has high or low.
16 I/O Pins are connected to one Port from A-G (-> max 107 Pins)
At first after the start-up you need to initialize the relevant parts of the application.
### Relevant Inits
1. RCC_AHB2ENR ;Clock activation for Ports
#### GPIO
2. GPIOx_MODER ;Configuration of the Ports, Masking, I/O Mode
3. GPIOx_ODR ;Output Data Register (to set an output)
4. GPIOx_IDR ;Input Data Register (to read if there is an input)
#### Timer
1. RCC_APB1ENR1 ;Interrupts, Timer activation
2. TIMx_PSC ;Prescaler defines the actual frequency: TimerClock = Peripheral Clock/(PSC[15:0]+1)(protip: Base 10 Hz like 100 Hz)
3. TIMx_ARR ;Auto Reload Register(After how many seconds the Timer should reload)(protip: If PSC is Base 10 then ARR should be also Base 10)
4. TIMx_DIER ;DMA/Interrupt Enable Register(0 for UIE and 8 for UDE)
#### Handler
1. NVIC_ISERx ;Interrupt Set/Clear Enable Register(to catch the Timerinterrupts from the Interruptsource)
2. NVIC_ICPRx ; Interrupt Clear Pending Register(both are set the same, but should be before the main program to avoid flawed excecution)

## First Assembly Program
### The Main Program
At first there is a keyword, which identifies the beginning of the program. The keyword is ```main```. In the special case which our USAGE defined it could be like this:
main.s
```asm
INCLUDE STM32G4xx_REG_ASM.inc
EXPORT main
AREA MAIN, code

;Beginning of the main program

main PROC

;some code

loop

    ;more code

    B loop
ENDP
END
```

### Example program
Is the example.s in Github

