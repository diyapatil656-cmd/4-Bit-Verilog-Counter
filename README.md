# 4-Bit Binary Counter with Synchronous Reset
A digital hardware design project demonstrating sequential logic design, timing analysis, and testbench validation using Verilog HDL.

## 🚀 Project Overview
This repository contains the RTL design and verification testbench for a standard 4-bit binary counter. The hardware module increments its binary value (from `0000` to `1111`) sequentially on every positive edge of the system clock. It features a synchronous active-high reset to safely clear the state back to zero.

### Key Specifications:
- **Languages:** Verilog / SystemVerilog
- **Simulation Engine:** Icarus Verilog 0.10.0
- **Verification Platform:** EDA Playground / EPWave
- **Logic Type:** Sequential (Edge-Triggered)

---

## 🛠️ Hardware Architecture
The counter updates its state using non-blocking assignments (`<=`) inside a clock-edge triggered block, matching industry-standard synthesizable RTL coding styles.

- **Inputs:** 
  - `clk`: System clock signal.
  - `rst`: Active-high reset signal.
- **Outputs:** 
  - `count[3:0]`: 4-bit wide vector tracking the numeric count (0 to 15).

---

## 💻 Simulation & Verification Results
The correctness of the logic was validated using a simulation testbench that forces the system clock through multiple cycles and triggers a reset condition. 

### Waveform Analysis:
- Upon asserting the `rst` signal, the output `count` immediately drops to `4'b0000`.
- Once `rst` is de-asserted, the counter increments by `1` at every rising edge of `clk`.
- Upon reaching `4'b1111` (decimal 15), the counter rolls over cleanly back to `4'b0000` on the subsequent clock tick.

---

## ⚙️ How to Run the Simulation
To inspect the circuit behavior without physical hardware:
1. Open the design source files on [EDA Playground](https://edaplayground.com).
2. Select **Icarus Verilog** as your target simulator engine.
3. Check the **"Open EPWave after run"** option in the sidebar configuration.
4. Click **Run** to generate and review the timing signal waveforms.
