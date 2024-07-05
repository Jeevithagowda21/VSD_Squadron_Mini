***TASK-5***
### Observing waveform using RISC-V Core Verilog netlist and testbench for functional simulation experiment.

### 
***These are the following steps to perform simulation.***
* Create a directory for your Verilog project to keep your files organized.
  \'''
     mkdir verilog_project
     cd verilog_project
  \'''

* Create and Edit Verilog Module and Testbench.
  \''' nano module.v
       nano testbench.v
   \'''

* Compile and Run the Testbench.
 /''' iverilog -o simulation.vvp module.v testbench.v /'''
  
* Run the Simulation.
 /''' vvp simulation.vvp/'''
  
* View the Waveform.
 /''' gtkwave testbench.vcd/'''

***After running these steps the GTKWave Window  will be opened.***
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/46dd3aa9-b10a-48a4-99ee-aa82916e4740)





  



