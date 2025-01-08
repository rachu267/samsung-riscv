# samsung-riscv
The program is based on the RISC-V architecture and uses open-source tools for VLSI chip design and RISC-V.

## Basic Details

Name: Rachagond Doddashivannavar

College: Vidyavardhaka College of Engineering

Email ID:rachagonddoddashivannavar@gmail.com

GitHub Profile:

LinkedIN Profile: 

## Task 1: Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler

## C and RISC-V Based Labs

This repository demonstrates the processes involved in compiling C programs and generating assembly code using both a standard GCC compiler and a RISC-V GCC compiler. It includes comprehensive steps and explanations to guide users through each stage of the compilation and debugging workflow.

## C Language-Based Lab

### Steps to Compile a .c File on Your Machine:

1. Open the bash terminal and navigate to the directory where you want to create your file.
2. Use the following command to create and edit a new .c file:
   sh
   gedit sum_1ton.c
![sum1ton_code_snippet](https://github.com/user-attachments/assets/d74e9930-8ec0-4a94-a7be-8e3787d24331)
)
### Steps to Compile a .c File :
 sh
 gcc sum_1ton.c
 ./a.out

### Compilation and execution complete.

![sum1ton_output](https://github.com/user-attachments/assets/00a4a49d-7520-44b9-945d-095a31e0a36a)
)


## RISC-V Based Lab

### Steps to Compile Using RISC-V GCC Compiler:
1. Ensure the RISC-V GCC compiler is installed and accessible on your system.
2. Verify the .c file contents using the cat command:
sh
cat sum_1ton.c

![cat_sum1ton](https://github.com/user-attachments/assets/8d74dec2-0fdf-4885-aef5-f9f4962ddbda)
)

4. Compile the C program for RISC-V architecture using:
 sh
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum_1ton.o sum_1ton.c
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c

![O1 and Ofast](https://github.com/user-attachments/assets/7d01d22d-6c73-4a8e-a40c-4436cde559f0)
)


5. Disassemble the object file to view its assembly code using:
 sh
riscv64-unknown-elf-objdump -d sum_1ton.o
```
6. Use /main in the terminal to locate the main function in the assembly output.
![assembly_code_snippet](https://github.com/user-attachments/assets/98ebc243-65f5-441a-8e8e-dc1353a18050)

### Explanation of Commands and Options: 
1. -mabi=lp64: Specifies the Application Binary Interface (ABI) for 64-bit integers, pointers, and long data types, suitable for 64-bit RISC-V architecture.

2. -march=rv64i: Indicates the 64-bit RISC-V base integer instruction set architecture.

3. -O1: Enables basic optimization for better performance without significantly increasing compilation time.
  
4. -Ofast: Focuses on maximizing performance by enabling aggressive optimizations, potentially at the cost of standard compliance.

5. riscv64-unknown-elf-objdump: A tool for disassembling RISC-V binaries to examine the code structure and debug it effectively.
