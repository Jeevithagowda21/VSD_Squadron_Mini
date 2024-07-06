***TASK-5***
### Observing waveform using RISC-V Core Verilog netlist and testbench for functional simulation experiment.

### 
***These are the following steps to perform simulation.***
* Create a directory for your Verilog project to keep your files organized.
  ```sh
   mkdir verilog_project
  ```
 ```sh
    cd verilog_project
  ```

* Create and Edit Verilog Module and Testbench.
 ```sh
   nano module.v
 ```
 ```sh
   nano testbench.v
  ```
Here 'nano' is the text editor.

* Compile and Run the Testbench.
```sh
$ iverilog -o simulation.vvp module.v testbench.v
```
  
* Run the Simulation.
```sh
 $ vvp simulation.vvp
 ```
  
* View the Waveform.
 ```sh
 $ gtkwave testbench.vcd
 ```

***After running these steps the GTKWave Window  will be opened.***

![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/46dd3aa9-b10a-48a4-99ee-aa82916e4740)

### Now Analysing and Verifying the result with help simulation from a Previous task.















  



