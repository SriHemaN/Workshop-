# RTL DESIGN USING VERILOG WITH SKY130 TECHNOLOGY
![image](https://user-images.githubusercontent.com/84923955/119863419-27fe0f00-bf37-11eb-80dd-d847c639770b.png)
### ABOUT THE WORKSHOP
This Workshop works as a training course which covers from the basic to advance. It was a cloud based 5-Day workshop which introduced the concepts such as Introduction to Verilog RTL design and Synthesis, Timing libs, hierarchical vs flat synthesis and efficient flop coding styles, Combinational and sequential optmizations, GLS, blocking vs non-blocking and Synthesis-Simulation mismatch, Optimization in synthesis. I was given the oppurtunity to work on the opensource environment. Labs were performed using 
Yosys and Sky130 PDKs.
### AUTHOR OF THE WORKSHOP
##### Mr. Kunal Ghosh
Co-founder of VLSI System Design (VSD) Corporation Private Limited
### AGENDA
1. ASIC Design Flow / RTL TO GDS Flow
2. Day 1
   - Introduction to Verilog RTL Design and Synthesis
     - Introduction to open-source simulator iverilog
     - Introduction to iverilog design testbench
   - Labs using iverilog and gtkwave
     - Introduction to Lab
     - Introduction to iverilog gtkwave
   - Introduction to Yosys and Logic synthesis
     - Introduction to Yosys
     - Introduction to Logic Synthesis
   - Labs using Yosys and SKY130 PDKs
### 1. ASIC Design Flow / RTL TO GDS Flow
![asic flow](https://user-images.githubusercontent.com/84923955/119888907-8fc25300-bf53-11eb-890c-4db9dc60266a.jpg)

**Specification** is the first step in the design. Specification are the requirements or the features that the chip must possess. i.e., in terms of the functionality means what logic or function it must perform? how much area it must consume? and with what clock frequency it must operate?
  
  Now, as per the specifications given from the customer, the top level Engineer designs the **Architecture of the design** in the form of Block Diagram. i.e., what must be the different blocks the design must contain. Like example: ALU, memory unit etc. and its interconnections.
  The cost of the chip is also estimated at this stage and if everything is fine then we proceed it to the **RTL design**.
  
  As the ASIC designs are very complex, EDA tools are used to proceed.
  
  Now, from the Block diagram or the Architecture, the RTL Engineer derives the **behaviour or the functionality of the design in an algorithmic manner and writes an RTL code using HDL which may be verilog or VHDL** so that the RTL code is understood by the tool.
  
  **RTL** is the Register Transfer Level which includes interconnections of the combinational elements like logic gates and the sequential elements like registers as per the functionality.
  
  **XILINX** tools are comonly used for the RTL coding and is coded using **Verilog Behavioral model**.
  
  **Behavioral model** represents the algorithmic way of representing the behavior of the design and also uses some mathematical or arithmetic expressions.
  
  Next step is the **Functional Verification**. i.e., to verify and cross check the RTL code whether it satisfies the functionality and the given specifications. If there are any errors, the code is modified and iterations are made until the specifications are satisfied.
  
  Next is the **Logic Synthesis**. In this stage, the tool converts the **RTL behavioral model code into the structural verilog code which is a Gate level Netlist**.
  
  The tools used for Logic Synthesis are **Design Compiler from Synopsys** and **Genus from Cadence** mostly.
