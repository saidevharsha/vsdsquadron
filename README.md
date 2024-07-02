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

![instructionset]()
