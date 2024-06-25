# vsdsquadron
<details>
<summary><b> Task 1:</b> The task is to download the required software and to run a simple c code using RISC-V instructions </summary>
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
<summary><b> Task 2:</b> The task is to write a c program for Traffic Flow Controller and getting out using RISC-V instructions </summary>
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




