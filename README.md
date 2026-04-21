
8-Bit Processor

Overview

This project implements an 8-bit multicycle processor in Digital. The processor supports both R-type and I-type instructions and includes a program counter, instruction memory, instruction register, control unit, register file, ALU, immediate path, and writeback path.

Architecture

The processor operates using four stages:

1. Fetch
2. Decode
3. Execute
4. Writeback

The control unit generates timing signals for instruction loading, PC incrementing, and register writeback.

Instruction Format

The 8-bit instruction format is:

* bit 7: T
* bits 6..4: opcode
* bits 3..2: Rd
* bits 1..0: Rs or immediate

Supported Instructions

R-type:

* ADD Rd, Rs
* ADDC Rd, Rs
* SUBB Rd, Rs
* SUB Rd, Rs
* PASS Rd
* INC Rd
* DEC Rd

I-type:

* LDI Rd, #imm

Main Components

* Program Counter
* Instruction Memory
* Instruction Register
* Control Unit
* Register File
* FinalALU8
* Immediate zero-extension path
* ALU input mux

Test Program

The provided test program is:

* LDI R1, #3
* LDI R2, #1
* ADD R1, R2
* SUB R1, R2
* INC R1
* DEC R1
* ADDC R1, R2
* PASS R1

Machine-code values:

* 143
* 147
* 12
* 108
* 168
* 200
* 44
* 136

Files

* Digital circuit files for the processor and all subcircuits
* project report
* screenshots and test results

Author

Kirsten Kajubi
