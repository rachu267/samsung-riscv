# samsung-riscv
The program is based on the RISC-V architecture and uses open-source tools for VLSI chip design and RISC-V.

## Basic Details

Name: Rachagond Doddashivannavar

College: Vidyavardhaka College of Engineering

Email ID:rachagonddoddashivannavar@gmail.com

GitHub Profile:https://github.com/rachu267 

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


<details>
<summary><b>Task 2:</b>Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler simulator</summary>
<br>
	
**Debugging with SPIKE: Comparing -O1 and -Ofast Optimizations**

**-O1:** A moderate optimization for balanced performance.

**-Ofast:** A high-speed optimization that prioritizes performance over strict standards

**add.c File**
![sum code](https://github.com/user-attachments/assets/8989da87-e34d-4330-af71-683b478b9642)

Commands:

riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum.o sum.c
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum.o sum.c



**Running on SPIKE**

Commands:

spike pk sum.o

To open Interactive Debugging

spike -d pk sum.o

Objdump:

riscv64-unknown-elf-objdump -d sum.o
riscv64-unknown-elf-objdump -d sum.o | less
```


</details>
</details>
<details>





#task_3 Review the RISC-V software documentation to understand the R, I, S, B, U, and J 
instruction types. 
# RISC-V Instruction Types for the Given Code

## *Instruction Types*

### 1. *R-Type (Register-Register Instructions)*
   - Typically involves arithmetic and logical operations between registers.
   - No such instruction appears directly in the given code at the C level, but operations like comparisons (e.g., num <= 0.0) may involve R-type instructions at the assembly level.

### 2. *I-Type (Immediate Instructions)*
   - Used for instructions with immediate values or memory addressing.
   - Example in the code: scanf("%lf", &num);
     - This would translate to an I-type instruction to load the address of num or handle immediate values.

### 3. *S-Type (Store Instructions)*
   - Used for storing data from a register to memory.
   - Example: Assigning the value entered by the user into the variable num involves S-type instructions.

### 4. *B-Type (Branch Instructions)*
   - Used for conditional branching.
   - Examples:
     - if (num <= 0.0)
     - if (num == 0.0)
     - These conditions are compiled into B-type instructions such as BEQ (branch if equal), BLT (branch if less than), or BGE (branch if greater or equal).

### 5. *J-Type (Jump Instructions)*
   - Used for unconditional jumps.
   - Example: The else block in the code could lead to a jump instruction to skip over the if block or jump to the end of the program.

### 6. *U-Type (Upper Immediate Instructions)*
   - Used for loading upper bits of immediate values.
   - While not directly visible in the C code, U-type instructions like LUI (load upper immediate) might be used during address calculations or handling larger constants.

### 7. *UJ-Type (Unconditional Jump and Link Instructions)*
   - Similar to J-type but used for function calls.
   - Example: The main() function or calls to printf and scanf might involve UJ-type instructions like JAL (jump and link).

---
This classification provides a detailed mapping of the instruction types based on the given C code.
