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



#Task 2:</b>Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler simulator</summary>
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

     ![u type](https://github.com/user-attachments/assets/20546a03-4725-4219-a148-f6a3b17ebb3b)

     ![j type](https://github.com/user-attachments/assets/b9f6cb0b-07fa-433e-b928-81efc739ebfe)

     ![r type](https://github.com/user-attachments/assets/75dda646-6a50-4ac3-bd3d-58539e6acad6)

     ![s type](https://github.com/user-attachments/assets/0242ffc8-e33b-4734-a590-b8a7b7a97d1a)

     ![u type](https://github.com/user-attachments/assets/52a47773-e6c8-4827-b72d-e9c38e047f81)






---
This classification provides a detailed mapping of the instruction types based on the given C code.



Task 4:By making use of RISCV Core: Verilog Netlist and Testbench, perform an experiment of Functional Simulation and observe the waveforms

1. Project Overview
   - This project performs a functional simulation of a RISC-V Core using a Verilog netlist and a testbench.
   - The goal is to verify the functional correctness of the core by analyzing the simulation results.

2. Prerequisites
- Install the required simulation tools:
- Icarus Verilog (iverilog) – To run the Verilog simulation.
- GTKWave – To visualize the waveform outputs.
- Ensure that you have access to:
- The Verilog netlist of the RISC-V core.
- The testbench for executing the simulation.
  
3. Setting Up the Simulation Environment
- Clone or download the Verilog netlist and testbench files.
- Install the required tools (e.g., Icarus Verilog, GTKWave).
- Navigate to the project directory and compile the Verilog files using
  
  iverilog -o riscv_sim risc_v_netlist.v testbench.v

  Run the simulation:
  
    vvp riscv_sim
  
Generate waveform files for analysis:

gtkwave dump.vcd

4. Running the Functional Simulation
   
- Load the netlist and testbench into the simulator.
- Execute the testbench to generate output signals.
- Verify key signal behaviors such as:
- Instruction execution
- Register updates
- Memory access
  
6. Capturing and Analyzing Waveforms
- Use GTKWave to open the generated VCD file.
- Observe important signals like PC (Program Counter), register values, and memory accesses.
- Compare the expected vs. actual results to ensure functional correctness.
  
7. Uploading Results to GitHub
- Save waveform snapshots as .png or .vcd files.
- Update the README with:
- Simulation logs
- Waveform analysis






TASK_5:-Introduction: Water Level Sensor Using RISC-V and Ultrasonic Sensor
Water level monitoring is essential for applications such as water tank automation, irrigation management, and flood detection. This project involves developing a water level detection system using a RISC-V development board and an ultrasonic sensor (e.g., HC-SR04). The system measures the water level by calculating the distance between the sensor and the water surface, then processes the data using the RISC-V board.

Objective:
The primary goal of this system is to accurately monitor and display water levels while enabling automation features such as alerts or motor control. The ultrasonic sensor sends sound pulses, which bounce off the water surface and return to the sensor. The time taken for the pulse to return is measured and converted into distance using the speed of sound

![Screenshot 2025-02-28 074441](https://github.com/user-attachments/assets/0589f20c-31e2-45f2-a374-8157aca1f81d)

![Screenshot 2025-02-28 074504](https://github.com/user-attachments/assets/2c7a550c-c94f-41c7-b3e1-a034a459fac0)

![Screenshot 2025-02-28 074518](https://github.com/user-attachments/assets/bc3d8b3c-83a9-43db-b4f4-3df263b80256)


TASK_6:-Project: Water Level Sensor Using RISC-V and Ultrasonic Sensor
1. Project Overview
This project focuses on designing a water level monitoring system using a RISC-V development board and an ultrasonic sensor (HC-SR04). The system continuously measures the water level in a container or tank by detecting the distance between the sensor and the water surface. The collected data can be displayed on an LCD/OLED screen, sent to a microcontroller for decision-making, or used to trigger alarms or motor control systems.

2. Working Principle
The system works by utilizing the time-of-flight principle of an ultrasonic sensor:

The HC-SR04 sensor sends out a high-frequency sound pulse.
The pulse travels toward the water surface and reflects back.
The RISC-V board measures the time taken for the echo to return.
Using the speed of sound, the system calculates the distance to the water surface.
The water level is determined by subtracting this distance from the total tank height.
Based on the water level, the system can display values, trigger alarms, or activate a motor pump for automation.
3. Hardware Components
-RISC-V Development Board (e.g., HiFive1, Sipeed Longan Nano, or FPGA-based RISC-V core)
-Ultrasonic Sensor (HC-SR04) for distance measurement
-5V Power Supply for sensor and board operation
-LCD/OLED Display (optional) to show water level readings
-Bzzer/LED (optional) for alert notifications
-Relay Module (optional) to control a water pump based on threshold levels
4. Software Implementation
Programming Language: C (for microcontroller-based RISC-V) or Verilog (for FPGA-based RISC-V)


-Triggering the ultrasonic sensor
-Measuring the echo response time
-Calculating the water level
-Displaying the water level on an LCD or sending it to a remote system
-Controlling alerts or pumps when predefined thresholds are reached
5. Applications
-Automatic water tank monitoring in households and industries
-Smart irrigation systems for agriculture
-Flood detection and water level monitoring in reservoirs and rivers
-Water conservation systems for optimized usage

![project](https://github.com/user-attachments/assets/24fbae41-524f-4281-9504-dc13a45d6903)

![p3](https://github.com/user-attachments/assets/7545880d-8081-4e67-a7aa-d6a686e49dc4)

![Screenshot 2025-02-28 080533](https://github.com/user-attachments/assets/251acc21-36aa-4432-ac8f-19a1a054bd5d)




