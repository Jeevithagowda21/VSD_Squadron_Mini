TASK-4

Identifying various RISC-V instruction set and exact 32-bit instruction code in the instruction type format.

RISC-V instructions are categorized into several types based on their instruction formats. These formats define how the binary representation of an instruction is structured. The main types of RISC-V instruction formats are R, I, S, B, U, and J. 

![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/79454e23-d885-479f-b098-2e97086b1b96)

1. R-type(Register)
   R-type instructions perform operations that involve only registers (no immediate values or memory accesses). They are primarily used for arithmetic and logical operations.

      Func7	        rs2	      rs1	    Func3	       rd	    opcode
      31-25                       24-20                     19-15                     14-12                   11-7                   6-0

   


