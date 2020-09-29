# RISC-V-TL_Verilog
# Contents
- [Introduction to RISC-V Basic Key words](#Introduction-to-RISC-V-Basic-Key-words )
  - [Apps to Hardware](#Apps-to-Hardware)
  - [Types of Instructions](#Types-of-Instructions)
  - [Lab work for RISC-V software tool Chain](#Lab-work-for-RISC-V-software-tool-Chain)
  - [Number system](#Number-system)
- [Application Binary Interface](#Application-Binary-Interface)
  - [Introductoin to Application Binary Interface](#Introductoin-to-Application-Binary-Interface)
  - [Memory Allocation for Double Words](#Memory-Allocation-for-Double-Words)
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
    - [Sequential Calculator](#Sequential-Calculator)
    - [Counter and Calculator in Pipeline](#Counter-and-Calculator-in-Pipeline)
    - [2-Cycle calculator](#2-Cycle-calculator)
    - [2-Cycle Calculator with Validity](#2-Cycle-Calculator-with-Validity)
    - [Calculator with Single-Value Memory](#Calculator-with-Single-Value-Memory)
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

# Introduction to RISC-V Basic Key words
  - ISA - Instruction Set Architecture(it is basically the language of computer)
  - ABI - Applicatoin Binary Interface(Also called System call interface, with which  program can directly acess the resources of Processor RISC-V here).
# Apps to Hardware
  Application Software ----> System software ----> Hardware
  With any on Application software like Email, Browser the programs (according to the action took) are run in the back ground by the system software. System Software includes OS, Compiler, Assembler. OS takes care of I/O operations, Allocate memory and some low level system functions. Compiler converts the invoked C, C++, java programs (by the OS with the action of User in the Application Software)to a set of instructions (.exe file) and then these instructuions are converted to binary format by the assembler And these binary stream is run or applied to the hardware that it performs the alloted task to such pattern.
# Types of Instructions
  1) Pseudo Instructions
  2) Base integer Instructions RV64I
  3) Multiply extension RV64M
  4) Single and Double precission floating point extension RV64F & RV64D.
  5) Application Binary Interface
  6) Memory Allocation and Stack pointer

# Lab work for RISC-V software tool Chain
  We start the labwork by writing a simple C program to compure the sum from 1 to n compile and run it with the help of riscv cpu and view the assmebly level code walkthrough registers with the help of spike debug.
  ![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/sum1ton.JPG)
  ![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/objfile.JPG)
  ![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/assmeblycodeinput.JPG)
  ![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/assemblyprogram.JPG)
  ![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/spikedebug.JPG)
# Number system
  The number system used is binary and for signed numbers 2's complement numbersystem is followed
# Application Binary Interface
  # Introductoin to Application Binary Interface
  
  ![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/ABI.JPG)
  # Memory Allocation for Double Words
  Their are two types of memory allocation for words they are little endian and Big endian. Little endian means low significant byte is stored in low address and the subsequnectly significant byte is stored in the consecutively big adress and in Big endian it takes as reverse Most signifacnt byte takes low address and and low significant takes higher address.Little endian addressing cann be clearly explained by the following image.
  ![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/littleendian.JPG)


# Calculator
  Calculator is the basic project that any programer who knows how to use arithmetics in a programing Language. A basic calculator should be able to perform +,-,*,/. 

# Combinational Calculator
  This circuit implements a basic calculator that can perform + , - , * , / on two inputs(val1 and val2) with a two bit width selsect line(sel).

![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/Calculator.JPG)

# Sequential Calculator
  Sequential logic is sequenced by a clock signal and must be able to return to a known state on reset. A real calculator remembers the last result, and uses it for the next
calculation .So we will be taking one of the input of the calculator as the output of previous calculation and also introduce a reset that can clear the output.

![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/SeqCalculator.JPG)

# Counter and Calculator in Pipeline
  We will keep a count on number of calculations done in it  in a single stage pipeline and other use can be known further.

![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/Cnt%20and%20Calc.JPG)

# 2-Cycle calculator
  Now we will run calculator in two stages 
1) To know the operation to be performed.
2) To do the selected operation.

So one the input(taken from the output of calculator) should be given as input after two cycles and while doing 1st operation we will clear the output using a valid signal- we can get this from the counter in the previous step (we should make it as single bit counter).

![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/CycleCalc.JPG)

# 2-Cycle Calculator with Validity
  # validity
    Validity Provides
  ● Easier debug
  ● Cleaner design
  ● Better error checking
  ● Automated clock gating
We can provide this validity using when condition that only ona valid signal both operation will be done.

![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/CycleCalcwithvalidity.JPG)

# Calculator with Single-Value Memory

  Calculators support “mem” and “recall”, to remember and recall a value . We extend the select line to 3 bits for these operation and we will be using the 3rd bit for selecting recall and mem operation.

![alt text](https://github.com/Shabarish443/RISC-V-TL_Verilog/blob/master/images/Calcwithsinglemem.JPG)

