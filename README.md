# Fibonacci Processor Simulation – Logisim

This project implements a simple processor in **Logisim** capable of executing a custom instruction set to calculate and store a sequence of **Fibonacci numbers**. It was created as part of an assignment to test `store` and `move` instructions, memory writing, and program control flow within a hardware simulation environment.

## 🧠 Objective

Design a program that:
- Computes Fibonacci numbers **F₂ to F₁₁**
- Stores them in **data memory addresses 0 through 9**
- Ends with **361 (F₁₁)** stored at address **9**

The entire program is implemented in **≤ 35 instructions**, stored in ROM.

---

## ⚙️ Instruction Set

The custom processor supports six instructions:

| Instruction | Opcode | Format       | Description                        |
|-------------|--------|--------------|------------------------------------|
| `add`       | 0010   | `Rd, Rs`     | `Rd = Rd + Rs`                     |
| `sub`       | 0011   | `Rd, Rs`     | `Rd = Rd - Rs`                     |
| `ldi`       | 1110   | `Rd, val`    | `Rd = immediate value`             |
| `ld`        | 1111   | `Rd, Rs`     | `Rd = data[Rs]`                    |
| `mv`        | 0110   | `Rd, Rs`     | `Rd = Rs`                          |
| `st`        | 1011   | `Rd, Rs`     | `data[Rs] = Rd`                    |

The processor uses a typical **Fetch-Decode-Execute** pipeline, with a program counter, instruction register, control logic, ALU, and data memory.

---

## 🔁 Program Behavior

- Initializes necessary registers with `ldi` and `sub`.
- Uses a loop-like structure to:
  - Compute Fibonacci values using `add`
  - Store values into memory using `store`
- Verifies final value at address `9` is `361 (0x0169)`, confirming correct calculation of **F₁₁**.

---

## 🧪 Testing and Results

- ✅ `move` and `store` instructions are fully implemented and tested.
- ✅ Correct data flow and memory writing behavior.
- ✅ Address 9 contains the correct final value (`361`).
- ✅ Registers are explicitly initialized (no assumption of zero state after reset).
- ✅ Program fits within 35 instructions.

---

## 📌 Notes

This project demonstrates foundational understanding of:
- Custom CPU design
- Control logic for instruction decoding
- Memory management in hardware
- Writing machine-level programs for simulated CPUs
