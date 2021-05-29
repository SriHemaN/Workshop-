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
2. What is VSD-IAT, YOSYS OPEN SYNTHESIS SUITE, SKY130 TECHNOLOGY, iVerilog SIMULATOR and GTKwave?
3. Day 1
   - Introduction to Verilog RTL Design and Synthesis
     - Introduction to open-source simulator iverilog and iverilog design testbench
   - Labs using iverilog and gtkwave
     - Introduction to Lab and iverilog gtkwave
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
  
  The inputs required for the Logic Synthesis are the RTL code, library files and the constraints file.
  
  The logic synthesis happens in 3 stages:
   - **Translate**
   - **Mapping**
   - **Optimize**
  
  **Translate** means the **tool converts the high level RTL circuit into its corresponding logic gates**.
  For example, like the FullAdder at Higher level circuit representation is implemented at lower level of representaion using simply the logic gates. However, the functionality   remains the same.
  
  Next is the **Technology mapping**, Here the tool maps the logic gates with the required technology that we are designing here i.e., whether in 28nm, 14nm or 1nm etc.
  
  Next is to **Optimize**. The **tool does optimization in terms of power, area, timing i.e., to get the best QOR (Quality of results)**.
  
  Next is the **Design for test i.e., DFT insertion** is also done at this stage by DFT team.
  
  Now, the **Gate level Simulation i.e., Logic verification and testing** is done to check whether it performs the required logic and iterations are made until there are no       errors.
  
  The **Output of the logic Synthesis** is the **gate level netlist** and the **SDC contraints file which are given as the input to the physical design**.
  
  In **Physical Design or PNR**, the **gate level netlist is converted to the GDS Format**.
  
  **GDS** is the **Graphic Database Stream**. It is nothing but a transistor level layout format i.e., the physical representaion of the design which can be manufacturable.
  
  The various steps involved in physical design are
   - The **Design inputs** where all the inputs are read by the tool
   - **Floorplan**
   - **Powerplan**
   - **Placement**
   - **CTS and Routing** with optimizations in each stage.
  
  Thus in physical design, **Gatelevel netlist will be** finally **converted to a GDS transistor level layout will best QOR**.
  
  Now, the obtained GDS transistor level layout file is sent for **verification and signoff** where different checks are performed like
   - **DRC, Design Rule Check**
   - **ERC, Electrical Rule Check**
   - **LVS, Layout vs Schematic**
   - **Timing Analysis**
   - **Power Analysis**
   - **Crosstalk Analysis**, etc
  then iterations or modifications are made until we meet the requirements.
  
  The GDS file after verification is sent to the **Foundary**. And this process is called **Tape-Out**.
  
  In foundry, the **mask is generated for a design layout and chip is fabricated**.
  
  The **Fabricated chip is then packaged to protect from the external damage and again tested for any bugs before releasing into the market**.
  
  After the final testing process, the **bug free chip is released in the market finally**.
  
  This completes our **IC Design flow / Asic Design flow / RTL to GDS flow**.
  
### 2. VSD-IAT, YOSYS OPEN SYNTHESIS SUITE, SKY130 TECHNOLOGY, iVerilog SIMULATOR and GTKwave

#### VSD-IAT
  **VLSI System Design-Intelligent Assessment Technology** is a training platform designed by VLSI system Design which is best suited for the design requirements. It developed         for **providing automated & Self-paced Learning experience from IC to device physics**.

#### YOSYS OPEN SYNTHESIS SUITE
  **Yosys** is the synthesizer tool used for **converting the RTL to netlist**. It is a free software licensed under **ISC License**. It processes any **Synthesizable Verilog - 2005 design**.     It is controlled using synthesis scripts.
  
#### SKY130 TECHNOLOGY
  **SKY130 is a 180nm-130nm hybrid technology** which was developed by Cypress Semiconductor. SKY130 is available now as a **foundry technology** through SKYWater technology Foundry.
  **SkyWater Open Source PDK** is a Collaboration between Google and SkyWater Technology Foundary to provide a **Open Source Process Design Kit**.
  
#### iVerilog SIMULATOR
  **Icarus Verilog or iVerilog** is an open source simulator tool available for Linux, Windows and Mac OS X which is released under the GNU, General Public License.
  Iverilog is nothing but the **implementation of the verilog hardware description language**.
  
#### GTKWave
  **GTK is a VCD waveform viewer which is based on the GTK library**. It supports VCD and LXT formats for signal dumps withrespect to iVerilog, it is used to view the simulated       output of the verilog code.
   
### 3. DAY 1
  #### INTRODUCTION TO VERILOG RTL DESIGN AND SYNTHESIS
  **RTL**
   
  **Register Transfer Level** is a representation of the digital circuit at the abstract level which consists of two elements namely Sequential circuits (flip-Flops) and  Combinational circuits(Logic Gates). With the help of these two elements, an RTL designs can implementany circuits.
      
  There are two commonly used hardware description language(HDL's):
  -  **Verilog HDL**
  -  **VHDL**

  **VERILOG HDL**
  
  Verilog HDL is a standardized IEEE 1364 hardware description language which is a textual format used to model the electronic systems and is commonly used in the RTL level of abstraction to design and verify the digital circuits.
  
  **DESIGN**
  
  Design is the actual Verilog code or set of Verilog codes which has the intended functionality to meet with the required specifications.
  
  Example : Verilog design for 2-input MUX
  
  ```verilog
  module good_mux (input i0 , input i1 , input sel , output reg y);
  always @ (*)
  begin 
         if(sel)
                  y <= i1;
          else
                  y <= i0;
   end
   endmodule
   ```
   
  **TEST BENCH**
  
  Test Bench is the setup to apply stimulus i.e., test_vectors to the design to check its functionality.
  
  Example : TestBench for the design 2:1 MUX
  
  ```verilog
  `timescale 1ns / 1ps
  module tb_good_mux;
          // Inputs
          reg i0,i1,sel;
          // Outputs
          wire y;
          
          // Instatiate the Unit Under Test (UUT)
          good_mux uut (
                  .sel(sel),
                  .i0(i0),
                  .i1(i1),
                  .y(y)
          );
          
          initial begin
          $dumpfile("tb_good_mux.vcd");
          $dumpvars(0,tb_good_mux);
          // Initialize Inputs
          sel = 0;
          i0 = 0;
          i1 = 0;
          #300 $finish;
          end
          
  always #75 sel = ~sel;
  always #10 i0 = ~i0;
  always #55 i1 = ~i1;
  endmodule
           
  ```
  
  **SETUP OF A DESIGN AND TEST BENCH**
  
![image](https://user-images.githubusercontent.com/84923955/120069510-ec348800-c0a3-11eb-8227-d3c5d9a2e83d.png)

Consider a design having a set of primary inputs which can be one or many. Now, to all these primary inputs, stimulus has to be generated and for all the primary outputs, need to observe the stimulus. So there is a Stimulus Generator and a Stimulus Observer. The design will be initiated in the testbench and then there will be a mechanism to apply Stimulus to the design.

    Note:
      -  Design may have one or more primary inputs, one or more primary outputs.
      -  Test Bench does not have a primary input or primary output.
      
  **SIMULATOR**
  
  Simulator is the tool used for simulating the design.
  
  RTL Design is checked for adherence to the spec by simulating the design.
  
  The tool used for simulating is iVerilog.
  
  **HOW SIMULATOR WORKS?**
  - Simulator looks for the changes on the input Signals.
  - If there is no change in the input, the simulator is not going to evaluate the output.
  
  **SIMULATION FLOW**
  
  ![image](https://user-images.githubusercontent.com/84923955/120071888-c791dd80-c0ae-11eb-9ea4-e4b7f4a23a81.png)
  
  Consider a design and a test bench written for that design. We know that the Simulator only looks for the changes in the input and then only dumps the changes in the output. So the output of a Simulation is going to be a VCD File where VCD stands for Value Change Dump.
  Now, in order to view the VCD file we use a tool called GTKwave where we will be able to view the waveform output and verify the functionality of the design.
  
  **ENVIRONMENT SETUP FOR RUNNING THE LAB**
  
  **Steps to install git clone and look into the files present**:
  
  **step 1 :** mkdir VLSISRI
  
  **step 2 :** cd VLSISRI
  
  **step 3 :** mkdir vsdflowsri
  
  **step 4 :** cd vsdflowsri
  
  **step 5 :** git clone https://github.com/kunalg123/vsdflow.git
  
  **step 6 :** cd SKY130RTLDesignAndSynthesisWorkshop
  
  **step 7 :** cd my_lib
  
  **step 8 :** cd lib
  
  **step 9 :** cd ..
  
  **step 10 :** cd verilog_model
  
  **step 11 :** cd ..
  
  **step 12 :** cd ..
  
  **step 13 :** cd verilog_files
  
      Note : 
      
      Cloning : cloning means just making a copy of the repository
      
      git : Git is a project management system which keep track of the changes we make from version to version and also facilitates multiple developers to work on a single project.
      sky130RTLDesignAndSynthesisWorkshop : It is the 
         




  
