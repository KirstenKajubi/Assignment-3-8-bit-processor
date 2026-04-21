# 8-Bit Multicycle Processor

## Overview
This project implements an 8-bit multicycle processor using Digital logic simulation. The processor is capable of executing arithmetic instructions through a structured datapath and a control unit that operates over multiple clock cycles.

The design demonstrates key computer architecture concepts including instruction fetch, decode, execution, and writeback, as well as synchronization between control and datapath components.

---

## Architecture

The processor follows a **4-stage multicycle architecture**:

1. **Fetch** – Instruction is loaded from memory into the Instruction Register (IR)  
2. **Decode** – Opcode is interpreted by the control unit  
3. **Execute** – ALU performs the required operation  
4. **Writeback** – Result is stored in the register  

---

## Instruction Format

Each instruction is 8 bits:
Example:
- `0001` → ADD instruction  
- `0010` → Immediate value (2)

---

## Supported Instruction

### ADD (Immediate)

Performs:
---

## Datapath

The processor datapath is structured as:
- **PC (Program Counter):** Selects instruction address  
- **ROM:** Stores program instructions  
- **IR (Instruction Register):** Holds the current instruction  
- **Control Unit:** Generates control signals  
- **ALU:** Performs arithmetic operations  
- **Register:** Stores computation results  

---

## Control Signals

Key control signals include:

- `IR_load` – Loads instruction into IR during fetch  
- `PC_inc` – Increments PC during fetch  
- `add_execute` – Activates ALU operation during execute stage  
- `add_writeback` – Enables register update during writeback  

---

## Program

The program loaded into instruction memory:Register ← Register + Immediate
---

## Datapath

The processor datapath is structured as:PC → ROM → IR → Control Unit
IR → ALU → Register → ALU (feedback)
- **PC (Program Counter):** Selects instruction address  
- **ROM:** Stores program instructions  
- **IR (Instruction Register):** Holds the current instruction  
- **Control Unit:** Generates control signals  
- **ALU:** Performs arithmetic operations  
- **Register:** Stores computation results  

---

## Control Signals

Key control signals include:

- `IR_load` – Loads instruction into IR during fetch  
- `PC_inc` – Increments PC during fetch  
- `add_execute` – Activates ALU operation during execute stage  
- `add_writeback` – Enables register update during writeback  

---

## Program

The program loaded into instruction memory:
ADD 2
ADD 3
ADD 1
ADD 4
Machine code:0x12
0x13
0x11
0x14
---

## Execution Result

The processor produces the following output sequence: 0 → 2 → 5 → 6 → 10
This confirms:
- Correct instruction execution  
- Proper ALU functionality  
- Accurate timing of writeback operations  

---

## Implementation Details

- Instruction memory implemented using ROM for stable execution  
- Control unit implemented using a one-hot state machine  
- PC increment controlled via `PC_inc` to synchronize with fetch stage  
- Immediate values are zero-extended before ALU input  

---

## Files

- `.dig` files → Digital circuit designs  
- `report.pdf` → Project report  
- `README.md` → Project documentation  

---

## Challenges

Key challenges addressed:

- Synchronizing PC, IR, and control unit timing  
- Preventing continuous PC increment  
- Ensuring instruction stability across multiple cycles  
- Debugging datapath and control signal interactions  

---

## Future Improvements

- Support additional instructions (SUB, LOAD, STORE)  
- Implement a multi-register file  
- Add branching and control flow  
- Extend to a pipelined processor design  

---

## Author

Kirsten Kajubi
