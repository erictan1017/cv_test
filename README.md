# RISCV-processor
A simulator for a simplified RISC-V processor in C++

## Supported Instructions:
LW, SW, SLT, SLL, SLLI, BEQ, BLT

Additional Instructions: ADD, SUB, AND, ADDI

## Design Methodology:
assembler.hpp - contains shared data structures, constants, and global declarations

encoder.cpp - contains functions for translation to opcode

encoder.hpp - contains functions for translation to opcode

index.html - main webpage used for GUI

instruction_set.cpp - contains the RISC-V instruction definitions

main.cpp - main file containing simulator functions for HTML

parser.cpp - handles reading, and instruction parsing

parser.hpp - handles reading, and instruction parsing

pipeline_structs.hpp - contains data structures used for pipelining

simulator.cpp - contains functions used for simulator in main

simulator.hpp - contains functions used for other larger functions in simulator.cpp

simulator.js - JavaScript file used for index.html

simulator.wasm - wasm file used for index.html

utils.cpp - for helper/utility functions (e.g., splitting, conversions, register parsing)

utils.hpp - for helper/utility functions (e.g., splitting, conversions, register parsing)

## AHA Moments
- Since the original program was built with C++, we realized that we could utilize HTML for a GUI through the use of WebAssembly (WASM) 

- One big problem was debugging a 32 bit integer
- For example, 320 in binary is 1 0100 0000, but the lower 8 bits are only seen as 64. This made it so that mem 16 contained 64 and mem 17 contained 1.

- Data hazards can be detected by simply looking at the IR values of the previous cycle and instruction since it contains information of registers that needed to be updated
