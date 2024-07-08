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

### Now Analysing and Verifying the Output Waveform of various Instructions.
### 
```sh
add r6,r1,r2
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/84ba7466-f389-4b14-a027-42e4da11cc2b)

In the above image, '1' and '2' are values stored in two registers, so addition  1 + 2 = 3.Thus the output is 3.
And '02208300' is an 32-bit instruction.
### 

```sh
sub r7,r1,r2
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/1e1bed83-74ad-4d30-a653-23b0ddf1d01b)

In the above image, '1' and '2' are values stored in two registers, so subtration  1 - 2 = -1.Thus the output is -1.
And '02209380' is an 32-bit instruction.
### 

```sh
and r8,r1,r3
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/a891f7d7-b25a-426f-8b21-fa6ccb2105b5)


In the above image, '1' and '3' are values stored in two registers, so the bitwise AND  1 & 2 = 1.Thus the output is 1.
And '0230A400' is an 32-bit instruction.
###
```sh
or r9,r2,r5
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/1802fb90-846f-4831-b569-37692389fe9f)
In the above image, '2' and '5' are values stored in two registers, so the bitwise OR  2 | 5 = 7.Thus the output is 7.
And '02513480' is an 32-bit instruction.
###
```sh
xor r10,r1,r4
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/2fc9abb2-9123-4e5b-9c87-3b7535268291)

In the above image, '1' and '4' are values stored in two  registers, so the bitwise OR  1 | 4 = 5.Thus the output is 5.
And '0240C500' is an 32-bit instruction.
###
```sh
slt r11,r2,r4
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/dfc38adb-b55b-48ed-82ef-7b3917c0451e)

In the above image, '2' and '4' are values stored in two registers, if 2 < 4.Thus the output is 1.
And '02415580' is an 32-bit instruction.
###
```sh
addi r12,r4,5
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/4d867bcc-e08e-40c3-974e-89869e61d203)
In the above image,  '4' is a value stored in a register and '5' is an immediate value, so addition 4 + 5 = 9.Thus the output is 9.
And '00520600' is an 32-bit instruction.
###
```sh
sw r3,r1,2
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/fbb34c60-d3d5-481d-8219-1ac63fb9279a)
In the above image,  So, the sw r3, r1,2 instruction is storing the value 2 into memory address 3.
And '00209181' is an 32-bit instruction.
###
```sh
lw r13,r1,2
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/822aeba2-e5de-4192-92ff-1ad58fa0092e)
In the above image,  So, the lw r3, r1,2 instruction is storing the value 2 into memory address 3.
And '00208681' is an 32-bit instruction.
###
```sh
beq r0,r0,15
```
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/94982f46-f3cd-4d9f-9b5a-cb2fe4eb3a52)

In the above image, '0' is the value stored in register 'r0'. BEQ checks the values stored in both the registers if both the  values are equal, it increments the program counter(PC) by 15.Thus the output is 25 (10+15).
And '00F00002' is an 32-bit instruction.
###
###
### 
### 
###
END


















































  



