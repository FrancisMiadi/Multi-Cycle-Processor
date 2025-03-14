# ⚙️ Multi-Cycle RISC Processor

## 📌 Overview  
This project presents the design and verification of a **16-bit multicycle RISC processor**. The processor has a **16-bit program counter (PC)**, **eight 16-bit general-purpose registers**, a **16-bit return register (RR) for function calls**, and **Performance registers** that keep track on various program execution metrics. This design uses **Word-addressable memories** to store data and instructions in **two distinct physical memories**, supporting three different instruction types: **R-, I-, and J-type**. Each instruction is carried out by the multicycle architecture in several steps: **fetch, decode, execute, access memory, and write back**. To ensure the datapath and control path functionality, boolean equations and control signals were created. A testbench for the primary structural module and waveform simulations for every module were used for verification in order to confirm their functionality. **Active-HDL** was used for RTL design, while **Canva** was employed for drawing the micro-Architecture diagram.

## 💡 Supported Instructions

### 🔹 R-Type Instructions  
| **Instruction** | **Format** | **Operation** |
|---------------|------------|-----------------------------|
| **AND**  | `AND Rd, Rs, Rt` | `Reg(Rd) = Reg(Rs) & Reg(Rt)` |
| **ADD**  | `ADD Rd, Rs, Rt` | `Reg(Rd) = Reg(Rs) + Reg(Rt)` |
| **SUB**  | `SUB Rd, Rs, Rt` | `Reg(Rd) = Reg(Rs) - Reg(Rt)` |
| **SLL**  | `SLL Rd, Rs, Rt` | `Reg(Rd) = Reg(Rs) << Reg(Rt)` |
| **SRL**  | `SRL Rd, Rs, Rt` | `Reg(Rd) = Reg(Rs) >> Reg(Rt)` |

---

### 🔹 I-Type Instructions  
| **Instruction** | **Format** | **Operation** |
|---------------|------------|-----------------------------|
| **ANDI**  | `ANDI Rt, Rs, Imm` | `Reg(Rt) = Reg(Rs) & Imm` |
| **ADDI**  | `ADDI Rt, Rs, Imm` | `Reg(Rt) = Reg(Rs) + Imm` |
| **LW**    | `LW Rt, Imm(Rs)`  | `Reg(Rt) = Mem(Reg(Rs) + Imm)` |
| **SW**    | `SW Rt, Imm(Rs)`  | `Mem(Reg(Rs) + Imm) = Reg(Rt)` |
| **BEQ**   | `BEQ Rs, Rt, Imm` | `if (Reg(Rs) == Reg(Rt)) Next PC = branch target else Next PC = PC + 1` |
| **BNE**   | `BNE Rs, Rt, Imm` | `if (Reg(Rs) != Reg(Rt)) Next PC = branch target else Next PC = PC + 1` |
| **FOR**   | `FOR Rs, Rt`      | `Rs stores loop target; Rt is loop counter, decremented each iteration until 0` |

---

### 🔹 J-Type Instructions  
| **Instruction** | **Format** | **Operation** |
|---------------|------------|-----------------------------|
| **JMP**  | `JMP Offset`  | `Next PC = jump target` |
| **CALL** | `CALL Offset` | `Next PC = jump target; PC + 1 stored in RR` |
| **RET**  | `RET`         | `Return from function (assumed instruction)` |

---

## 📄 Notes  
- **Registers:** `Rd, Rs, Rt` represent general-purpose registers.  
- **Imm:** Immediate values used in I-Type instructions.  
- **Memory Access:** `LW` and `SW` involve loading/storing values from memory.  
- **Branching:** `BEQ` and `BNE` control conditional execution.  
- **Loop Control:** `FOR` uses `Rs` for loop address and `Rt` for the iteration count.  
- **Jumping:** `JMP` and `CALL` modify the **Program Counter (PC)**.  


## 🤝 Project Team
-**Francis Miadi**  
-Miar Taweel 
-Leena AbuHammad

## 🌐 Contact  
For inquiries, reach out via:  
- **Email:** *francismiadi0@gmail.com*  
- **GitHub:** *FrancisMiadi*  
