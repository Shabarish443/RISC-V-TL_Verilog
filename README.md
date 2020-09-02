# RISC-V-TL_Verilog
# Contents
- [Introduction to RISC-V Basic Key words](#Introduction-to-RISC-V-Basic-Key-words )
  - [Apps to Hardware]
  - [Lab work for RISC-V software tool Chain]
  - [Numbersystem]
- [Application Binary Interface]
  - [Introductoin to Application Binary Interface]
  - [Memory Allocation for Double Words]
- [Lab work using ABI function calls]
  - [Alhorithm to sum 1 to N using ASM]
  - [Simulate C program with Function call]
- [Basic Verification flow using iverilog]  
- [Digital logic with TL-Verilog in Makerchip IDE]
  - [Boolean Operators]
  - [Makerchip Platform]
- [Basic Programs]
  - [MUX program]
  - [Chaining Ternary Operator]
  - [Sequesntial logic]
  - [Counter]
- [Calculator](#calculator)
    - [Combinational Calculator](#combinational-calculator)
    - [Sequential Calculator]
    - [Counter and Calculator in Pipeline]
    - [Cycle calculator]
    - [Cycle Calculator with Validity]
    - [Calculator with Single-Value Memory]
- [RISC-V]   
  - [RISC-V Block Diagram]
- [Simple RISC-V subset]
  - [Next PC]
  - [Fetch]
  - [Decode Block Diagram]
  - [Instruction Types Decode]
  - [Instruction Immediate Decode]
  - [Instruction Decode]
  - [RISC-V Instruction Field Decode]
  - [Instruction_Decode]
  - [Register File Read Block diagram]
  - [Register File Read]
  - [ALU]
  - [Register File Write]
  - [Branches]
- [Pipelined RISC-V subset]
  - [Waterfall Logic Diagram]
  - [Cycle RISC-V]
  - [Register File Bypass]
  - [Lab_Branches]
  - [Complete Instruction Decode]
  - [Complete ALU]
  - [Load/Store]
  - [Jumps]
- [Testbench]

# Introduction to RISC_V Basic Key words


# Calculator
Calculator is the basic project that any programer who knows how to use arithmetics in a programing Language. A basic calculator should be able to perform +,-,*,/. 

# Combinational Calculator
This circuit implements a basic calculator that can perform + , - , * , / on two inputs(val1 and val2) with a two bit width selsect line(sel)
![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/Calculator.JPG)
# Sequential Calculator
Sequential logic is sequenced by a clock signal and must be able to return to a known state on reset. A real calculator remembers the last result, and uses it for the next
calculation .So we will be taking one of the input of the calculator as the output of previous calculation and also introduce a reset that can clear the output.
![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/SeqCalculator.JPG)
