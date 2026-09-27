This is a CPU i designed.
it runs a 13 bit ISA:
| Opcode (Hex) | Mnemonic | Standard Term / Name | Functional Description |
| :---: | :--- | :--- | :--- |
| `0x0` | **NOP** | No Operation | Performs no action; advances program counter (PC). |
| `0x1` | **LOAD** | Load Memory | Loads data from the specified memory address into the Accumulator. |
| `0x2` | **STORE** | Store Memory | Stores the current Accumulator value into the specified memory address. |
| `0x3` | **ADD** | Arithmetic Add | Computes `Accumulator + Operand` through the ALU. |
| `0x4` | **SUB** | Arithmetic Subtract | Computes `Accumulator - Operand` through the ALU. |
| `0x5` | **COMMIT** | Commit / Latch Result | Latches the ALU output buffer into the Accumulator / updates flags. |
| `0x6` | **IMM** | Load Immediate | Loads an immediate literal value directly into the working register. |
| `0x7` | **JMP** | Unconditional Branch | Sets the Program Counter (PC) to the target target address. |
| `0x8` | **JZ** | Branch if Zero | Conditionally jumps to the target address if the Zero flag ($Z$) is set. |
| `0x9` | **JC** | Branch if Carry | Conditionally jumps to the target address if the Carry flag ($C$) is set. |
| `0xA` | **RDA** | Read Device Address | Reads a byte from the pointer. |
| `0xB` | **WDA** | Write Device Address | Writes a byte from the Accumulator to the pointer. |
| `0xC` | **SDA** | Set Device Address | Sets the active address of the pointer. |

<img width="651" height="863" alt="image" src="https://github.com/user-attachments/assets/8644e98b-957a-4074-be28-66a531746358" />
