# N-bit Arithmetic Unit (Logisim Evolution)

## Overview
This project implements a modular N-bit arithmetic unit using Logisim Evolution. The design follows a hierarchical structure, building complex functionality from simple digital components such as half adders and full adders.

A key feature of the design is the use of control signals to manipulate the B input before it enters the adder, enabling different arithmetic operations such as addition and subtraction.

---

## Features
- Modular and hierarchical design
- Scalable N-bit architecture (implemented as 4-bit)
- Ripple-carry adder structure
- Control-based arithmetic operations via B input logic
- Separate testing circuits for validation

---

## Circuit Components

### 1. Half Adder
- Computes sum and carry of two single-bit inputs
- Sum = A ⊕ B
- Carry = A · B

### 2. Full Adder
- Built using two half adders and an OR gate
- Handles carry input and output

### 3. B_input_logic
- Modifies input B based on control signals (S1, S0)
- Enables arithmetic operations such as:
  - Passing B directly
  - Inverting B (for subtraction)
  - Other controlled transformations

### 4. OneBit_arithmetic_unit
- Combines B_input_logic and a full adder
- Performs a single-bit arithmetic operation

### 5. Nbit_arithmetic_unit
- Chains multiple one-bit units into a ripple-carry structure
- Produces multi-bit output and final carry-out

---

## Inputs and Outputs

### Inputs
- A[3:0] : First operand
- B[3:0] : Second operand
- Cin    : Carry input
- S1, S0 : Control signals

### Outputs
- G[3:0] : Result output
- Cout   : Final carry-out

---

## Operation

The behavior of the circuit depends on control signals S1 and S0. These signals determine how the B input is modified before entering the adder.

Typical functionality includes:
- Addition (A + B)
- Subtraction (A - B using two’s complement)

---

## Design Approach
- Bottom-up design methodology
- Reusable components
- Clear separation between datapath and control logic
- Emphasis on scalability and readability

---

## Testing
The project includes dedicated test circuits:
- binputtest
- binputnbittest
- arithmeticunit1bittest
- arithmeticunitnbittest

These verify correctness at each level of abstraction.

---

## Limitations
- Uses ripple-carry architecture (linear delay)
- No overflow detection implemented
- Limited operation set (focused on arithmetic)

---

## Possible Improvements
- Add overflow detection logic
- Implement carry-lookahead adder for speed
- Extend to full ALU (AND, OR, XOR operations)
- Parameterize bit-width for dynamic scaling

---

## Requirements
- Logisim Evolution (v3.8.0 or compatible)
