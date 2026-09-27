This is a CPU i designed.
## Instruction Set Architecture (ISA)

The CPU operates on a minimal **4-bit opcode space (13 instructions)**. Dynamic memory indexing and table lookups are implemented via a dedicated **Data Address (Pointer) Register**:

| Opcode | Mnemonic | Name | Description |
| :---: | :--- | :--- | :--- |
| `0x0` | **NOP** | No Operation | Advances Program Counter (PC) with no state change. |
| `0x1` | **LOAD** | Load Direct | Loads byte from immediate memory address into Accumulator. |
| `0x2` | **STORE** | Store Direct | Stores Accumulator value directly into memory address. |
| `0x3` | **ADD** | Arithmetic Add | Computes `Accumulator + Operand` through the ALU. |
| `0x4` | **SUB** | Arithmetic Subtract | Computes `Accumulator - Operand` through the ALU. |
| `0x5` | **COMMIT** | Commit / Latch Result | Latches the ALU buffer output into Accumulator and updates status flags. |
| `0x6` | **IMM** | Load Immediate | Loads an 8-bit literal operand directly into working state. |
| `0x7` | **JMP** | Unconditional Branch | Sets PC to target address. |
| `0x8` | **JZ** | Branch if Zero | Conditionally jumps if the Zero flag ($Z$) is asserted. |
| `0x9` | **JC** | Branch if Carry | Conditionally jumps if the Carry flag ($C$) is asserted. |
| `0xA` | **RDA** | Read Indirect (Pointer) | Loads byte into Accumulator from address stored in Pointer Register (`[PTR]`). |
| `0xB` | **WDA** | Write Indirect (Pointer) | Writes Accumulator byte to address stored in Pointer Register (`[PTR]`). |
| `0xC` | **SDA** | Set Pointer Address | Sets the active target address in the Data Address / Pointer Register. |

> **Addressing Note:** `SDA`, `RDA`, and `WDA` provide register-indirect addressing without requiring self-modifying code. This enables dynamic array access, state-table lookups, and heap-style buffer traversal in 256 bytes of RAM.


<img width="651" height="863" alt="image" src="https://github.com/user-attachments/assets/8644e98b-957a-4074-be28-66a531746358" />
