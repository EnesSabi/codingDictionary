# Applied Microcomputer Technology
## Makefile
### Make
1. Comments - For Commenting 
```makefile
# This is a comment
```
2. Macros - for Variables 
```makefile
name = string 
CFLAGS= -c --asm --cpu Cortex-M4
```
3. Rules -  to define dependencies and generate targets
```makefile
target: dependecies
[TAB not a Space] command #command to create target shell/commandline
```
4. Start Make Process - Every dependency is up to date
```makefile
make target
```
## Embedded C
Just a brief crashcourse for the used C
### Variables and Datatypes
Syntax: ```Datatyp Variablename [, Variablename];```
Types: ```char, int, float, double, void ```
Modificators: ```signed, unsigned, short, long```
```#define NAME VALUE```

### Problems with stdlib
The datatypes bitsize aren't defined. -> better stdint.h
#### stdint.h
```c
typedef signed char int8_t;
typedef signed int int16_t;
typedef signed long int int32_t;
typedef signed long long int int64_t;
typedef unsigned char uint8_t;
typedef unsigned int uint16_t;
typedef unsigned long int uint32_t;
typedef unsigned long long int uint64_t
```