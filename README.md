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



