# -Fibonacci-Sequence-Generator-using-Custom-Adders
Verilog-based digital design project implementing RCA, CLA, and Carry Skip Adders integrated into an FSM-based Fibonacci generator, along with a configurable hierarchical decoder (2→4, 3→8, 4→16). Includes testbenches and simulation results.
 Compute the Fibonacci series using three adder architectures and compare synthesis results.
Adder Implementations
1. Ripple Carry Adder (RCA)

 5-bit RCA (rca_adder_5bit) instantiated within a state-machine-based Fibonacci generator
 States: IDLE → INIT → COMPUTE → FINISH
 Detects overflow via carry-out bit
 Generates first 10 Fibonacci numbers (0–34)

2. Carry Look-Ahead Adder (CLA)

6-bit CLA (cla_adder_6bit) with full parallel carry generation
All carries computed simultaneously: C1–C6 using propagate (P) and generate (G) signals
Eliminates ripple delay — faster critical path

3. Carry Skip Adder (CSA)

10-bit CSA (carry_skip_adder_10) divided into two 5-bit blocks
Each block has a skip path: if all bits propagate (block_prop = &P[4:0]), carry skips the block
Fibonacci module uses direct clock-cycle updates (no state machine)
