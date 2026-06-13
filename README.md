# Hierarchical 1-Bit Full Adder in Verilog

This repository contains the structural Verilog implementation of a 1-Bit Full Adder, designed by hierarchically instantiating two Half Adder sub-modules and an OR gate. The project includes the design files, a testbench for functional verification, and simulation configurations.

## Architecture

The design implements the standard full adder logic equations using structural hierarchy:
- **Sum Stage:** `sum_out = a ^ b ^ c_in`
- **Carry Stage:** `carry_out = (a & b) | (c_in & (a ^ b))`

### RTL Schematic
The design hierarchy verified during synthesis:
- `HA1` (Half Adder 1): Computes intermediate sum and carry from inputs `a` and `b`.
- `HA2` (Half Adder 2): Computes final `sum_out` and intermediate carry using the sum from `HA1` and `c_in`.
- `m1` (OR Gate): Combines carry signals from `HA1` and `HA2` to output the final `carry_out`.

<img width="941" height="752" alt="RTL Schematic" src="https://github.com/user-attachments/assets/5bc16d5b-5b92-43a3-9ab2-b9b6a2aefb15" />


## Simulation & Verification
Functional verification was performed using a dedicated testbench (`full_adder.tb.v`). The simulation waveform outputs confirm that the combinational logic perfectly matches the 1-bit full adder truth table with stable propagation paths.

<img width="960" height="768" alt="Simulation and Verification" src="https://github.com/user-attachments/assets/2b6b56b9-bdc0-405a-88a5-37e91d73d88e" />


## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/aditi-mahindrakar/Verilog-full-adder/tree/main
   ```
2. Import the source design files into your RTL synthesis tool to view the compiled schematic layout.
3. Load the source files and testbench into your simulation tool environment, compile them, and execute the simulation run to verify the timing waveforms.

