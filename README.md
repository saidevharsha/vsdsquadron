# vsdsquadron
<details>
<summary><b> Task 1</b>  </summary>
  <br>

**1) Installing virtual box**

![VM VIRTUAL BOX](https://github.com/saidevharsha/vsdsquadron/blob/main/task1/1%20installing%20virtual%20%20box.png?raw=true)

**2) Installing leafpad**

![Installing leafpad](https://github.com/saidevharsha/vsdsquadron/blob/main/task1/2%20install%20leafpad.png?raw=true)

*By using the following command we can install the leafpad in ubuntu*
```
  sudo apt install leafpad
```
**3) Sample c code**
![sample c code](https://github.com/saidevharsha/vsdsquadron/blob/main/task1/3%20sample%20c%20code.png?raw=true)

The code which is given in above picture will perform the addition function from 1 to 100 numbers,
After entering the code save the code

**4) Output for c code**
![output](https://github.com/saidevharsha/vsdsquadron/blob/main/task1/4%20sample%20c%20code%20output.png?raw=true)

By using following commands we can get the output for respective code

```
  gcc filename.c
  ./a.out
```
**5) Calculations of instructions**
![calculations](https://github.com/saidevharsha/vsdsquadron/blob/main/task1/5%20calculations%20of%20instructions.png?raw=true)

By using the following commands we can get the assembly codes which are the above picture
```
  riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
  ls -ltr sum1ton.o
```
Then the sum1ton.o file will be enable
```
  riscv64-unkown-elf-objdump -d sum1ton.o
```
The above command will give you bunch of assembly language code
```
  riscv64-unkown-elf-objdump -d sum1ton.o | less
```
The above command will help to reduce the assembly language code
</details>

<details>
<summary><b> Task 2</b>  </summary>
  <br>

**Traffic Flow Controller**
A simple Traffic flow controller controls the trafiic to reduce the congestions in this project iam using three lights red,yellow and green there will be a delay which will waste the time and it will be given to the each light and the delays for lights will be different and it will be fixed

**simple c code for traffic flow controller**

![c code](https://github.com/saidevharsha/vsdsquadron/blob/main/task2/c%20program%20for%20traffic%20light%20controller.png?raw=true)

**traffic flow controller program**
```
#include <stdio.h>
void redLight (int duration);
void yellowLight (int duration);
void greenLight (int duration);
void delay(int seconds);
int main() {
int redDuration = 4;
int yellowDuration = 2;
int greenDuration = 8;
while (1) {
redLight(redDuration);
yellowLight (yellowDuration);
greenLight(greenDuration);
}
return 0;
}
void redLight (int duration) {
printf("Red light on for %d seconds\n", duration); delay(duration);
}
void yellowLight (int duration) {
printf("Yellow light on for %d seconds\n", duration); delay(duration);
}
void greenLight (int duration) {
printf("Green light on for %d seconds\n", duration); delay(duration);
}
void delay(int seconds) {
unsigned long count;
for (int i=0; i< seconds; i++){
}
for(count=0; count<1000000000); count++);
}
```
The numericals which are assigned to the the lights are the delays for example redlight=4 so the red light will be enabled for 4 seconds this applicable to the remaining lights

**Output for the program**

![output](https://github.com/saidevharsha/vsdsquadron/blob/main/task2/output%20for%20c%20program.png?raw=true)

By using these commands we can get the output
```
  gcc filename.c
  ./a.out
```
First red light is enabled for 4 seconds,
Then yellow light is enabled for 2 seconds,
atlast green light is enabled for 8 seconds,
this process iterative process the lights will be enabled according there delays

**implementing traffic flow controller using RISCV**

![commands](https://github.com/saidevharsha/vsdsquadron/blob/main/task2/riscv%20gcc%20commands.png?raw=true)

```
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o tlc.o tlc.c
ls -ltr tlc.o
```
These are the commands used to implement in RISCV

**Assembly language code for traffic flow controller**

![assembly](https://github.com/saidevharsha/vsdsquadron/blob/main/task2/large%20number%20of%20assembly%20codes.png?raw=true)

```
  riscv64-unknown-elf-objdump -d tlc.o
```
By using the above command we will get bunch of assembly language codes to reduce the assembly language code there is another command

**reduced assembly language code**

![reduced](https://github.com/saidevharsha/vsdsquadron/blob/main/task2/reduced%20assembly%20codes.png?raw=true)

```
  riscv64-unknown-elf-objdump -d tlc.o | less
```
This is reduced assembly language code for traffic flow controller
</details>


<details>
<summary><b> Task 3</b></summary>
  <br>
  This task is to perform spike simulation and verifying the 01 and 0fast instructions in RISC-V 

 **verifying with -01 command**
 
 ![-01command](https://github.com/saidevharsha/vsdsquadron/blob/main/task3/01%20instruction.png?raw=true)

  This the command used to get the -01 instruction ``` riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o tlc.o tlc.c ```
 ,  we will get the output by using ``` ./a.out``` 

 ![spike-01](https://github.com/saidevharsha/vsdsquadron/blob/main/task3/01%20command.png?raw=true)

By using the following command we can get the spike verification
```
spike pk tlc
```
  
**Assembly language code for -01command**

![assembly code](https://github.com/saidevharsha/vsdsquadron/blob/main/task3/assembly%20language%20code%20for%2001%20instruction.png?raw=true)

 to get assembly language code for 01 instruction following command is used
 ```
  riscv64-unknown-elf-objdump -d tlc.o
```
by using above command we will get the large number of assembly language codes to reduce the no.of codes we will use the below code

```
  riscv64-unknown-elf-objdump -d tlc.o | less
```

**spike simulation for -01command**
![spike-01](https://github.com/saidevharsha/vsdsquadron/blob/main/task3/spike%20simulation%20for%2001%20instruction.png?raw=true)

In this we perform debugging by sing this instruction
```
spike pk tlc
```
"100b0" is the 1st address so we can start debugging from the 100b0 by using this command we can start simulation
```
until pc 0 100b0
```
for getting the register value ``` reg 0 a5 ```

**verifying with -0fast command**

This the command used to get the -0fast instruction ``` riscv64-unknown-elf-gcc -0fast -mabi=lp64 -march=rv64i -o tlc.o tlc.c ```
 ,  we will get the output by using ``` ./a.out``` 

 ![assembly 0fast](https://github.com/saidevharsha/vsdsquadron/blob/main/task3/assembly%20language%20code%20for%200fast%20instruction.png?raw=true)

 we can get the assembly code for 0fast instruction by using the same commands which we used to get the -01 instruction's assembly language code

 **Spike simulation for -0fast command**

 ![spike 0fast](https://github.com/saidevharsha/vsdsquadron/blob/main/task3/spike%20simulation%20for%200fast%20instruction.png?raw=true)


In this we perform debugging by sing this instruction
```
spike pk tlc
```
"100b0" is the 1st address so we can start debugging from the 100b0 by using this command we can start simulation
```
until pc 0 100b0
```
for getting the register value ``` reg 0 a5 ```

</details>


<details>
  <summary><b> Task 4</b></summary>
  <br>

 **RISC-V ISA:** RISC-V (pronounced "risk-five") is an open-source instruction set architecture (ISA) for processors. Unlike most ISAs, RISC-V is royalty-free, meaning anyone can design and build RISC-V chips without paying licensing fees. It's based on the RISC (Reduced Instruction Set Computing) principle, where processors perform simple operations efficiently. RISC-V has a modular design with a base instruction set and optional extensions for specific tasks. This flexibility makes it suitable for a wide range of devices, from tiny embedded systems to powerful computers. RIS-V is gaining traction in the industry with companies designing RISC-V processors and software tools being developed to support it.
There are some set of important instructions 

**Instruction set**
1. R - Register
2. I - Immediate
3. S - Store
4. B - Branch
5. U - Upper Immediate
6. J - Jump

![instructionset](https://github.com/saidevharsha/vsdsquadron/blob/main/task4/RISC-V%20INSTRUCTION%20%20SET.png?raw=true)

**R-TYPE INSTRUCTION(Register)**
* R-type instructions operate on data stored in registers, without relying on immediate values (numbers directly included in the instruction).
* The first 7 bits (opcode) act as a fingerprint, identifying the general type of operation (like addition or subtraction).
* Next 5 bits (rd index) specify the destination register, where the result of the operation will be stored.
* Combined opcode and 3-bit funct3 field provide more details about the exact operation to be performed.
* Finally, the last two registers (rs1 and rs2), identified by their indexes (bits 15-19 and 20-24 respectively), hold the data used in the operation.
 ![rtype](https://velog.velcdn.com/images/taegon1998/post/fe0b327b-f8e3-4ff3-b77e-0c2ec99f06a8/image.jpg?raw==true)

**I-TYPE INSTRUCTION(Immediate)**
* I-type instructions are workhorses that combine register data with immediate values (small constant numbers included within the instruction itself). This eliminates the need to constantly access memory for these values, making them faster.
* The key difference from R-type is the 12-bit immediate field occupying the upper portion of the instruction. This field holds the constant value directly usable in the operation.
* The opcode remains in the same location but identifies operations suited for immediate values (like adding a register with a constant).
* The rest of the structure, including destination register (rd) and source register (rs1) indexes, resembles R-type instructions.
* In short, I-type instructions offer a more compact way to perform calculations involving both register data and fixed values.
  
![ITYPE](https://velog.velcdn.com/images/taegon1998/post/cb659e46-c7db-40b5-b3c0-44835e8fedd8/image.jpg?raw=true)

**S-type Instruction(Store)**
* S-type instructions are all about moving data out of registers and into memory. They act like couriers, delivering register values to their designated storage locations.
* Unlike R-type and I-type, S-type instructions don't have a destination register (rd) because their focus is on storing, not manipulating data.
* To pinpoint the memory address for storage, S-type instructions utilize a split immediate field. This field is divided into two parts:
* Bits 11 to 5 hold the higher-order bits of the offset.
* Bits 4 to 0 contain the lower-order bits of the offset.
* This combined immediate value, added to the base address stored in a register (usually rs1), specifies the exact memory location where the data from the source 
 register will be deposited.

![stype](https://velog.velcdn.com/images/taegon1998/post/61bcec43-61f4-45ee-8e2f-1f9d51c80dba/image.jpg?raw=true)

**B-TYPE INSTRUCTION(Branch)**
* B-type instructions are the decision-makers of the RISC-V world. They control the flow of the program by performing conditional branches. Unlike their R, I, and S counterparts, B-type instructions focus on changing the execution path based on certain conditions.
* B-type instructions are all about "if-then-else" scenarios. They compare the values in two registers (rs1 and rs2) using a funct3 field that specifies the comparison type (equal to, greater than, etc.).
* There's no destination register (rd) because B-type instructions aren't concerned with storing results, just altering the program flow.
* Similarly, funct7 is absent as B-type instructions deal with branching logic, not complex arithmetic operations.
* It provides an offset value that determines how many instruction positions to jump (forward or backward) if the specified condition is met.
* Think of B-type instructions as road signs. They evaluate conditions and, if met, adjust the program's course by a certain distance (the immediate offset) in 
  memory.

![btype](https://velog.velcdn.com/images/taegon1998/post/889b5adc-c152-4fa1-814a-85f10336e036/image.jpg?raw=true)

**U-TYPE INSTRUCTION(Upper Immediate)**

* U-type instructions are the express delivery service of RISC-V. They specialize in loading large immediate values (constants) directly into registers. Unlike I- 
  type with its smaller immediate field, U-type offers a dedicated 20-bit space for these values.
* U-type instructions are all about efficiency. They ditch most other fields, focusing solely on the essential elements:
* A 20-bit immediate field carries the hefty data payload.
* A destination register (rd) is specified, where this immediate value will be deposited.
* You won't find funct3, rs1, rs2, or funct7 in U-type instructions. These fields are unnecessary for the simple task of loading immediate data.
* Think of U-type instructions as pre-filled envelopes. They contain a large value (immediate) and a clear destination address (rd register), making data transfer 
  swift and streamlined

![utype](https://velog.velcdn.com/images/taegon1998/post/f5397f8a-e8c2-4b09-9967-d8889c7d6186/image.jpg?raw=true)

**J-TYPE INSTRUCTION(Jump)**

* While the RISC-V instruction set architecture (ISA) did have J-type instructions in earlier versions, it's important to note that  J-type instructions are no longer part of the base ISA as of RISC-V specification version 2.2. 
* Previously, J-type instructions were used for unconditional jumps, similar to U-type instructions for loading immediates. They shared a similar format with just the opcode, destination register (rd), and a large immediate field for the jump target address.

  Here's a quick comparison:

    | Feature       | U-type Instruction | J-type Instruction (deprecated) |
    |----------------|---------------------|---------------------------------|
    | Purpose        | Load immediate      | Unconditional jump               |
    | Key Field      | 20-bit immediate      | 20-bit jump target address        |
    | Other Fields    | rd register (destination) | rd register (destination), opcode |

* However, J-type instructions have been replaced by a combination of JAL (Jump and Link) instruction using the U-type format and setting rd to zero (x0). This simplifies the ISA and eliminates the need for a separate J-type format.

**given instruction sets and their type of instructions**

**Instruction** | **Type**         |**Description**
----------------|-----------------|-----------------------------------
ADD r1, r2, r3     | R-type          | Adds the values in rs1 and rs2, stores the result in rd.
SUB r3, r1, r2     | R-type          |  Subtracts the value in rs2 from rs1, stores the result in rd.
AND r2, r1, r3     | R-type          |  Performs bitwise AND between rs1 and rs2, stores the result in rd.
OR r8, r2, r5      | R-type          |  Performs bitwise OR between rs2 and rs5, stores the result in r8.
XOR r8, r1, r4     | R-type          |  Performs bitwise XOR between rs1 and r4, stores the result in r8.
SLT r10, r2, r4    | R-type          |  Sets r10 to 1 if rs2 is less than rs4, otherwise 0. (Set Less Than)
ADDI r12, r3, 5   | I-type (immediate) |  Adds the immediate value (imm) to the value in rs1, stores the result in rd.
SW r3, r1, 4       | S-type          |  Stores the value in rs2 at the memory address calculated by adding imm to the value in rs1.
SRL r16, r11, r2   | R-type          |  Shifts the value in rs1 right by the number of bits specified in rs2, stores the result in r16. (Shift Right Logical)
BNE r0, r1, 20     | B-type (branch)   |  Branches to the instruction at address `PC + imm` if the values in r0 and r1 are not equal. (Branch Not Equal)
BEQ r0, r0, 15     | B-type (branch)   |  Branches to the instruction at address `PC + imm` if the value in r0 is equal to itself (always true). (Branch Equal)
LW r13, r11, 2     | I-type (load)    |  Loads the value from the memory address calculated by adding imm to the value in rs1, stores the value in r13.
SLL r15, r11, r2   | R-type          |  Shifts the value in rs1 left by the number of bits specified in rs2, stores the result in r15. (Shift Left Logical)


**32 Bit Instruction code for each instruction**

**1.ADD r1, r2, r3**
>* Opcode: 0110011 
>* rd : 00001 
>* funct3: 000 
>* rs1 : 00010 
>* rs2 : 00011 
>* funct7: 0000000

*32 Bit Instruction code:* ```0000000 00011 00010 000 00001 0110011 ```

**2.SUB r3, r1, r2**

>* Opcode: 0110011 
>* rd: 00011 
>* funct3: 000 
>* rs1 : 00001 
>* rs2 : 00010 
>* funct7: 0100000 

*32 Bit Instruction code:* ```0100000 00010 00001 000 00011 0110011 ```

**3.AND r2, r1, r3**
>* Opcode: 0110011 
>* rd : 00010 
>* funct3: 111 
>* rs1 : 00001 
>* rs2 : 00011 
>* funct7: 0000000

*32 Bit Instruction code:*```0000000 00011 00001 111 00010 0110011  ```

**4.OR r8, r2, r5**
>* Opcode: 0110011 
>* rd : 01000 
>* funct3: 110 
>* rs1 : 00010 
>* rs2 : 00101 
>* funct7: 0000000 

*32 Bit Instruction code:*```0000000 00101 00010 110 01000 0110011```
**5.XOR r8, r1, r4**
>* Opcode: 0110011 
>* rd : 01000 
>* funct3: 100 
>* rs1 : 00001 
>* rs2 : 00100 
>* funct7: 0000000 

*32 Bit Instruction code:* ```0000000 00100 00001 100 01000 0110011 ```

**6.SLT r10, r2, r4**

>* Opcode: 0110011 
>* rd : 01010 
>* funct3: 010 
>* rs1 : 00010 
>* rs2 : 00100 
>* funct7: 0000000 

*32 Bit Instruction code:* ``` 0000000 00100 00010 010 01010 0110011```

**7.ADDI r12, r3, 5**

>* Opcode: 0010011 
>* rd : 01100 
>* funct3: 000 
>* rs1 : 00011 
>* imm: 000000000101

*32 Bit Instruction code:* ```000000000101 00011 000 01100 0010011```

**8.SW r3, r1, 4**

>* Opcode: 0100011 
>* imm[4:0]: 00100 
>* rs1 : 00001 
>* rs2 : 00011 
>* funct3: 010 
>* imm[11:5]: 0000000

*32 Bit Instruction code:*```0000000 00011 00001 010 00100 0100011```

**9.SRL r16, r11, r2**

>* Opcode: 0110011 
>* rd : 10000 
>* funct3: 101 
>* rs1 : 01011 
>* rs2 : 00010 
>* funct7: 0000000 

*32 Bit Instruction code:*```0000000 00010 01011 101 10000 0110011```

**10.BNE r0, r1, 20**
