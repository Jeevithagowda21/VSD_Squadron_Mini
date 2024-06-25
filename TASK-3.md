TASK-3
SPIKE Simulation And Debug.

Spike, is the RISC-V Instruction Set Simulator (ISS).
Spike simulates a RISC-V processor, providing a platform for running RISC-V binaries and testing software before deploying it on actual hardware.

By Running this Command we can verify our output with the RISC-V gcc,
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/43437fbd-a641-4562-a978-5a8888fc2874)
If the output is same, it means that our instructions and simulation is correct(i.e verified) 
![Screenshot 2024-06-25 162533](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/a4fbceac-99c9-4502-b09b-037fbc33560c)


Next, we debug the instruction sets using the command:
![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/a338d2b2-fbce-4093-b4c6-09516c787690)

![image](https://github.com/Jeevithagowda21/VSD_Squadron_Mini/assets/142243440/f5e29c11-975b-4cdc-b52a-842ee0414afd)

reg - It is used to find the content of register 

AUIPC(Add Upper Immediate to PC) - It is an Assembly instruction in RISC-V architecture. It is is used to add a 20-bit immediate value, shifted left by 12 bits, to the program counter (PC) and store the result in the specified register.

ADDI(Add Immediate) - It is an Assembly instruction in RISC-V architecture. It is used to add a signed immediate value to the value in a register and store the result in another register. 
For Example : if the instruction is a2,a5,0x123, Where a2 is the Destination register, where the result of the addition will be stored. a5 is the Source register, containing the value to which the immediate will be added. 0x123 is the Signed immediate value (12 bits), which is added to the value in source regiter.




END













