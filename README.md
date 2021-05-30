# RTL DESIGN USING VERILOG WITH SKY130 TECHNOLOGY
![image](https://user-images.githubusercontent.com/84923955/119863419-27fe0f00-bf37-11eb-80dd-d847c639770b.png)
### ABOUT THE WORKSHOP
This Workshop works as a training course which covers from the basic to advance. It was a cloud based 5-Day workshop which introduced the concepts such as Introduction to Verilog RTL design and Synthesis, Timing libs, hierarchical vs flat synthesis and efficient flop coding styles, Combinational and sequential optmizations, GLS, blocking vs non-blocking and Synthesis-Simulation mismatch, Optimization in synthesis. I was given the oppurtunity to work on the opensource environment. Labs were performed using 
Yosys and Sky130 PDKs.
### AUTHOR OF THE WORKSHOP
#### Mr. Kunal Ghosh
Co-founder of VLSI System Design (VSD) Corporation Private Limited
### AGENDA
1. ASIC Design Flow / RTL TO GDS Flow
2. What is VSD-IAT, YOSYS OPEN SYNTHESIS SUITE, SKY130 TECHNOLOGY, iVerilog SIMULATOR and GTKwave?
3. Day 1
   - Introduction to Verilog RTL Design and Synthesis
     - Introduction to open-source simulator iverilog and iverilog design testbench
     - Labs using iverilog and gtkwave
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
      
      Cloning : cloning means just making a copy of the repository.
      
      git : Git is a project management system which keep track of the changes we make from version to version and also facilitates multiple developers to work on a single project.
      
      SKY130RTLDesignAndSynthesisWorkshop : It is the github page for the workshop.
      
      my_lib : It contains all library files which are needed.
               
               It has two folders namely lib, verilog_model.
               
               lib : It contains the standard cell library which will be used for the synthesis.
               
               verilog_model : This contains all the standard cell verilog models of the standard cells which are present in the lib.
     
      Verilog_files : It is a folder containing all the lab experiments. It contains all the verilog source files, test bench files and so on.
      
      mkdir : make directory i.e., creates a folder.
      
      ls : lists all the files in the directory.
      
      cd : This command is to go to a directory.
      
      cd .. : This command helps to go back from a folder to the folder before that.
      
   **Fig: Steps followed to git clone and look into the files present**
   
  ![image](https://user-images.githubusercontent.com/84923955/120074537-f1e99800-c0ba-11eb-95c0-aa06109e4bfd.png)
  
  **Fig: Files inside my_lib, lib, verilog_model**
  
  ![image](https://user-images.githubusercontent.com/84923955/120074576-1e9daf80-c0bb-11eb-9d7d-de06ac1dd480.png)
  
  **Fig: Command execution to goinside verilog_files**
  
  ![image](https://user-images.githubusercontent.com/84923955/120074585-2cebcb80-c0bb-11eb-808e-31d79c1ad19a.png)
  
  **Fig: List of files inside verilog_files**
  
  ![image](https://user-images.githubusercontent.com/84923955/120074602-3c6b1480-c0bb-11eb-92b1-57933750a7f5.png)
  
  **Fig: List of files inside verilog_files continued**
  
  ![image](https://user-images.githubusercontent.com/84923955/120074617-4a209a00-c0bb-11eb-895a-84afba586968.png)
  
  
  **HOW TO WORK WITH iVERILOG AND GTKWAVE?**
  
  Let us consider the example of a 2x1 MUX.
  
  **LOGIC DIAGRAM**
  
  ![image](https://user-images.githubusercontent.com/84923955/120076510-7a6c3680-c0c3-11eb-91dd-591f38a8c1c7.png)


  **TRUTH TABLE**
  
  | Sel | y  |
  | ----|----|
  | 0   | i0 |
  | 1   | i1 |
  
  **LOGIC EQUATION**
  
      Y = i0 Selbar + i1 Sel

  **CIRCUIT DIAGRAM**
  
  ![image](https://user-images.githubusercontent.com/84923955/120077243-0895ec00-c0c7-11eb-937c-72d8d6009106.png)
  
  **VERILOG CODE**
  
  Command used : **vim good_mux.v**
  
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
   
   Command used : **vim tb_good_mux.v**
   
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
  
   - We go to our design folder verilog_files which contains all our design files.
            
   ```verilog
   cd verilog_files
   ```
            
   - Load the design in iVerilog.
   
   ```verilog
   iverilog good_mux.v tb_good_mux.v
   ```
            
   Where, good_mux is the design name
          tb_good_mux is the test bench name
                   
   - Dump the file.
   
   ```verilog
   ./a.out
   ```
            
   - Load the VCD file into the GTKwave form viewer.

   ```verilog
   gtkwave tb_good_mux.vcd
   ```
  
  #### INTRODUCTION TO YOSYS
  **SYNTHESIZER**

  Synthesizer is the tool used for converting the RTL to netlist.
  
  Yosys is the Synthesizer tool
  
  **LEVELS OF ABSTRACTION**
  
  **Fig: Different levels of abstraction and synthesis**
  
  ![image](https://user-images.githubusercontent.com/84923955/120082719-23c22500-c0e2-11eb-9a1b-73365eba33e2.png)

  
  **SYNTHESIZER FLOW**
  
  ![image](https://user-images.githubusercontent.com/84923955/120079145-392e5380-c0d0-11eb-8d4e-bd27c230cd1a.png)
  
  Consider we have a design and a .lib which we will be applying to Yosys and we get netlist from the Yosys.
  
  **NETLIST**
  
  Netlist is the representation of the design in the form of standard cells in the .lib.
  
  **YOSYS SETUP FLOW COMMANDS**
  
   - **read_verilog :** It is used to read the design.
   - **lib :** It is used to read the library .lib.
   - **write_verilog :** It is used to write out the netlist.
  
  **HOW TO VERIFY THE SYNTHESIS?**
  
  ![image](https://user-images.githubusercontent.com/84923955/120079668-a04d0780-c0d2-11eb-8fbc-86a225a3c587.png)
  
  Lets see, I have a netlist and my testbench. We apply both to the simulator. The output we get from the simulator is the VCD output file. We load VCD file to the GTKwave to observe the stimulus.
  
      Note :
         - The stimulus obtained during synthesis simulation should be same as the output observed during RTL simulation.
         - We can use the same test bench which we had used during RTL simulation.
         - The set of primary inputs or primary outputs will remain same between the RTL design and the synthesized Netlist i.e., Same TestBench can be used!!

  #### INTRODUCTION TO SYNTHESIS
  **SYNTHESIS**
  
  Synthesis is the transformation of an idea into a manufacturable device to carry out an intended function.
  
  Now, consider the RTL code below:
  
  ```verilog
  module sample_code(
  input clk, rst,
  output result, done);
  
  always@(posedge clk, posedge rst)
  if(rst)
  ...
  else
  ...
  endmodule
  ..................
  ..................
  ```
  
  I want a digital circuit looking like this:
  
  ![image](https://user-images.githubusercontent.com/84923955/120083400-1f980680-c0e6-11eb-9d11-21476108d547.png)

I don't want a code. I want a hardware circuit. **How do I map these two?**

**Answer comes in the form of SYNTHESIS!**

**LOGIC SYNTHESIS**

Logic Synthesis is defined as the process of transforming the RTL code into a gate-level netlist.

**WHAT HAPPENS IN THE SYNTHESIS?**

- Performs gate level translation.

- Design is converted into gates and connections are made between the gates.

- The file what we write out finally is a gate-level netlist.

**WHAT IS .lib?**

.lib is the collection of logic modules which includes basic logic gates such as AND, OR, NOT, etc. 

It also contains different flavours of the same gate.

Like, 

      2 - input AND gate
      Versions:
      - slow
      - medium
      - fast
     3 - input AND gate
     Versions:
     - slow
     - medium
     - fast
     4 - input AND gate
     Versions:
     - slow
     - medium
     - fast


      
        
         




  
