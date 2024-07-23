

****Identifying various RISC-V instruction set and exact 32-bit instruction code in the instruction type format.****

RISC-V instructions are categorized into several types based on their instruction formats. These formats define how the binary representation of an instruction is structured. The main types of RISC-V instruction formats are R, I, S, B, U, and J. 

![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/79454e23-d885-479f-b098-2e97086b1b96)

**1. R-type(Register)**
   R-type instructions perform operations that involve only registers (no immediate values or memory accesses). They are primarily used for arithmetic and logical operations.
   The instructions are divided into six fields:

      ![rt](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/2662e018-2ec5-4f5c-ae24-a8bd928b1f9f)
   **func7** - The 'funct7' field is a 7-bit field located in bits (31-25) of the instruction. It provides additional specificity for the operation, often distinguishing between different 
   variants of an operation.

   **rs2 and rs1** - The 'rs2' and 'rs1'  are source register.Each of length 5-bits .Both contain an operand to perform operation.

   **func3** - The 'funct3' field is a 3-bit field located in bits (14-12) of the instruction.Differentiates between different operations or variants of an operation sharing the same opcode.

   **rd** - The 'rd' is a destination register of length 5-bits, where the final result of the operation is stored.

   **opcode** - It determines the primary type of the operation (e.g., arithmetic, logical, etc.), which is of length 7-bits.


**2. I-type(Immediate)**
   I-type instructions are used for operations involving an immediate value (a constant number) and a register. These instructions typically involve one source register and produce a 
   result in one destination register.

   ![vr](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/1047b75f-a565-4a9e-ab80-fc2496e7c4c0)

   **immediate** - The 'immediate' field consists of 12 bits and holds a constant value that is used directly in the operation. This value can be a positive or negative number and is 
   typically used for arithmetic operations, memory addressing, or setting specific bits in the destination register.

   **rs1** - The 'rs1' field specifies the first source register and is 5 bits long. This register contains one of the operands needed for the operation. The value stored in this register 
   will  be used in conjunction with the immediate value or another register to perform the desired computation.

   **func3** - The 'funct3' field is a 3-bit wide field that provides additional details about the operation to be performed. It differentiates between various types of instructions that 
   share the same opcode. For example, it specifies whether the operation is an addition, logical operation, or a type of comparison.

   **rd** - The 'rd' field is a 5-bit field that designates the destination register. This register is where the result of the operation will be stored. The value computed from the operation 
   involving rs1 and the immediate value will be written to this register.

   **opcode** - It determines the primary type of the operation (e.g., arithmetic, logical, etc.), which is of length 7-bits.
### 

   **3. S-type(store)**
      S-type instructions are used for operations that involve storing data from a register into memory.

     

      
      **immediate** - The 'immediate' field, which is split into two parts (imm[11:5] and imm[4:0]), collectively forms a 12-bit constant value that is used as an offset for the memory 
      address. This offset is added to the base address provided by the rs1 register to determine the final memory address where the data will be stored.

      **rs2** - The 'rs2' field is a 5-bit field that specifies the second source register. This register contains the data that will be stored in memory at the address calculated using the 
      base address in 'rs1' and the immediate offset.

      **rs1** - The 'rs1' field is a 5-bit field that specifies the first source register. This register provides the base address for the memory operation. The effective memory address for 
      the store operation is calculated by adding the value in this register to the immediate offset.

      **func3**  - The funct3 field is a 3-bit function field that provides additional specification for the store operation. It differentiates between various types of store instructions, 
      such as storing a word, byte, or halfword, by specifying the exact nature of the store operation.


   **4. B-type(Branch)**
      B-type instructions are used for conditional branching in a program. These instructions allow the program to jump to a different part of the code if a specified condition is met. 
      They typically involve comparing values in two registers and, based on the comparison, determining whether to branch (jump) to a target address.

      

      immediate(12 bits) - The immediate field, which is 12 bits in total, is divided into several parts: imm[12], imm[10:5], imm[4:1], and imm[11]. These parts are combined to form a 
      12-bit  signed immediate value that specifies the offset for the branch target address. This offset is added to the current program counter (PC) to determine the address to which 
      the program will branch if the specified condition is met.

      rs2(5-bits)- he 'rs2' field is a 5-bit field that specifies the second source register. This register contains the second value to be compared during the branch operation. The 
      value in  this register is used in the comparison specified by the instruction.

      rs1(5-bits) - The 'rs1' field is a 5-bit field that specifies the first source register. This register contains the first value to be compared during the branch operation. The 
      value in  this register is used in the comparison along with the value in the rs2 register.

      func3(3-bits) - The 'funct3' field is a 3-bit field that provides additional details about the type of comparison to be performed. It specifies the condition under which the 
      branch should   occur, such as whether the values in 'rs1' and 'rs2' should be compared for equality, inequality, less than, greater than, etc.


   **5. U-type(Upper Immediate)**
      U-Type instructions are used to work with large numbers. They put a big number (20 bits long) into a specific part of a register. This is useful when you need to handle large 
      constants or addresses in your program.

      ![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/8d3320c6-650c-4577-a5dc-c9ff49f00267)

      **immediate(20-bits)** - This field contains a 20-bit constant value, which is a relatively large number, that you want to load into a specific register. It can represent addresses or 
      large constants within the program.

      rd(5-bits) - The 'rd' field specifies the destination register where the 20-bit immediate value will be stored. Registers in a CPU are like special storage containers used to hold 
      data during processing.


   **6. J-type(Jump)**
      J-Type instructions are used for performing unconditional jumps in a program. These instructions allow the program to jump to a different part of the code without any condition 
      being checked.

      ![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/b069ed91-2198-4c3f-8328-0e1229f6b9dc)

      immediate(20-bits) - This field contains a 20-bit value that represents the target address where the program will jump to. It is calculated based on the current program counter 
      (PC) and a specified offset.

      rd(5-bit) - The rd field is not used in J-Type instructions in RISC-V. It is reserved for other types of instructions.


   
   Now let us identify some examples
```sh
i) ADD r1,r2,r3
```
This is an R-type instruction. As aritmetic and logical operations are used in R-type.

In RISC-V, the opcode for ADD (addition) is **'0110011'**.

'r1' corresponds to register 1, typically represented as '00001' in 5-bit binary.
'r2' corresponds to register 2, typically represented as '00010' in 5-bit binary.
'r3' corresponds to register 3, typically represented as '00011' in 5-bit binary.

The funct3 field specifies the specific arithmetic operation. For ADD, it is typically '000'.
The funct7 field specifies additional details for the operation. For ADD, it is typically '0000000'.

Therefore, the 32-bit instruction is: **0000000 00011 00010 000 00001 0110011**.

```sh
ii) SUB r3,r1,r2
```
This is an R-type instruction.

In RISC-V, the opcode for SUB (subtraction) is typically **'0110011'**.

For SUB, funct7 is typically '0100000' in binary.
For SUB, funct3 is '000' in binary, indicating subtraction.

Therefore, the 32-bit instruction is: **0100000 00010 00001 000 00011 0110011**.

```sh
iii) AND r2,r1,r3
```
As 'AND' is an Logical operations.Thus, it is an R-type instruction.

In RISC-V, the opcode for the AND operation is represented by **'0110011'** in binary.

For AND, funct7 is typically 0000000 in binary.
For AND, funct3 is 111 in binary. 

Therefore, the 32-bit instruction is: **0000000 00011 00001 111 00010 0110011**.


```sh
iv) OR r8,r2,r5
```
As 'OR' is an Logical operations.Thus, it is an R-type instruction.

In RISC-V, the opcode for the OR operation is represented by **'0110011'** in binary.

For OR, funct7 is typically '0000000' in binary.
For OR, funct3 is '110' in binary.

Therefore, the 32-bit instruction is: **0000000 01000 00010 110 00101**.


```sh
v) XOR r8,r1,r4
```
As 'XOR' is an Logical operations.Thus, it is an R-type instruction.

In RISC-V, the opcode for the OR operation is represented by **'0110011'** in binary.

For XOR, funct7 is typically 0000000 in binary.
For XOR, funct3 is 100 in binary.

Therefore, the 32-bit instruction is: **0000000 01000 00001 100 00100**.


```sh
vi) SLT r10,r2,r4
```
In RISC-V assembly language, 'SLT' (Set Less Than) compares two registers and sets the destination register to 1 if the first source register is less than the second, otherwise sets it to 0. 

In RISC-V, the opcode for the SLT operation is represented by **0110011** in binary.

For SLT, funct7 is typically 0000000 in binary.
For SLT, funct3 is 010 in binary, indicating set less than.

Therefore, the 32-bit instruction is: **0000000 01010 00010 010 00100**.


```sh
vii) ADDI r12,r3,5
```
In RISC-V assembly language, 'ADDI' (Add Immediate) adds a constant value (immediate) to a register and stores the result in another register. Thus it is an I-type instruction format.
In RISC-V, the opcode for the ADDI operation is represented by **'0010011'** in binary.

For ADDI, funct3 is 000 in binary.

The 32-bit instruction is: **000000000101 00011 000 01100 0010011**.


```sh
viii) SW r3,r1,4
```
In RISC-V assembly language, 'SW' (Store Word) stores the word from a register to memory.Thus it is an S-type instruction format.
In RISC-V, the opcode for the SW operation is represented by **'0100011'** in binary.

For SW, funct3 is 010 in binary, indicating store word.

The 32-bit instruction is: **0000000 00011 00001 010 00100 0100011**.


```sh
ix) SRL r16,r11,r2
```
In RISC-V assembly language, 'SRL' (Shift Right Logical) shifts the bits in a register to the right, filling the leftmost bits with zeros. The shift amount is specified in another register(r2). Here the operation is carried out using register.Thus, it ias an R-type instruction format.
In RISC-V, the opcode for the SRL operation is represented by **'0110011'** in binary.

For SRL, funct7 is 0000000 in binary.
For SRL, funct3 is 101 in binary, indicating shift right logical.

Therefore, the 32-bit instruction is: **0000000 00010 01011 101 10000 011011**.

```sh
x) BNE r0,r1,20
```
In RISC-V assembly language, 'BNE' (Branch if Not Equal) checks if the values in two registers are not equal, and if so, it branches to the specified immediate address offset.
In RISC-V, the opcode for the BNE operation is represented by **1100011** in binary, which signifies that this is a B-Type (Branch Type) instruction.

For BNE, funct3 is 001 in binary.

The instruction set format is: **0 000001 00001 00000 001 0100 0 1100011**.


```sh
xi) BEQ r0,r0,15
```
In RISC-V assembly language, 'BEQ' (Branch if Equal) checks if the values in two registers are equal, and if so, it branches to the specified immediate address offset. 
In RISC-V, the opcode for the BEQ operation is represented by **'1100011'** in binary.

 For BEQ, funct3 is 000 in binary.

 The 32-bit instruction set is: **0 000000 00000 00000 000 1111 0 1100011**.

 

```sh
 xii) LW r13,r11,2
```
In RISC-V assembly language, 'LW' (Load Word) loads a 32-bit word from memory into a register. 
In RISC-V, the opcode for the LW operation is represented by **'0000011'** in binary, which signifies that this is an I-Type (Immediate Type) instruction for load operations.

 For LW, funct3 is 010 in binary.

 The 32-bit instruction set is: **000000000010 01011 010 01101 0000011**.
 

```sh
 xiii) SLL r15,r11,r2
```
 In RISC-V assembly language, 'SLL' (Shift Left Logical) shifts the bits in a register to the left, filling the rightmost bits with zeros. The shift amount is specified in another 
 register.
 In RISC-V, the opcode for the SLL operation is represented by **'0110011'** in binary, which signifies that this is an R-Type (Register Type) instruction.


 For SLL, funct7 is 0000000 in binary.
 For SLL, funct3 is 001 in binary.

 The 32-bit instruction set is: **0000000 00010 01011 001 01111 0110011**.








 

















      





      


      


      



   


