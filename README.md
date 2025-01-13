# samsung-riscv
# samsung-riscv
The program is based on the RISC-V architecture and uses open-source tools to teach people about VLSI chip design and RISC-V. The instructor for this internship is Kunal Ghosh Sir.

# Basic Details

Name: Arya h v

College: Vidyavardhaka College of Engineering

Email ID: aryahv29@gmail.com

GitHub Profile: Arya-hv29

LinkedIN Profile: Arya H V

Task 1: Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler

# C Language based LAB
# C and RISC-V Based Labs

This repository demonstrates the processes involved in compiling C programs and generating assembly code using both a standard GCC compiler and a RISC-V GCC compiler. It includes comprehensive steps and explanations to guide users through each stage of the compilation and debugging workflow.

## C Language-Based Lab

### Steps to Compile a .c File on Your Machine:

1. Open the bash terminal and navigate to the directory where you want to create your file.
2. Use the following command to create and edit a new .c file:
   ```sh
   gedit sum_1ton.c


### Steps to Compile a .c File on Your Machine:
 sh
 gcc sum_1ton.c
 ./a.out
 # Compilation and execution complete.
 


### Steps to Compile Using RISC-V GCC Compiler:
1. Ensure the RISC-V GCC compiler is installed and accessible on your system.
2. Verify the .c file contents using the cat command:
 sh
cat sum_1ton.c

3. Compile the C program for RISC-V architecture using:
 sh
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum_1ton.o sum_1ton.c

4. Disassemble the object file to view its assembly code using:
 sh
riscv64-unknown-elf-objdump -d sum_1ton.o

5. Use /main in the terminal to locate the main function in the assembly output.

### Explanation of Key Commands and Options: 
1. -mabi=lp64: Specifies the Application Binary Interface (ABI) for 64-bit integers, pointers, and long data types, suitable for 64-bit RISC-V architecture.

2. -march=rv64i: Indicates the 64-bit RISC-V base integer instruction set architecture.

3. -O1: Enables basic optimization for better performance without significantly increasing compilation time.

4. riscv64-unknown-elf-objdump: A tool for disassembling RISC-V binaries to examine the code structure and debug it effectively.Task 2:
*Debugging with SPIKE: Comparing -O1 and -Ofast Optimizations*

*-O1:* A moderate optimization for balanced performance.

*-Ofast:* A high-speed optimization that prioritizes performance over strict standards

*add.c File*
![sum code](![IMG-20250113-WA0001](https://github.com/user-attachments/assets/5360708a-ec12-4978-b9fe-86b6e5da6890)

Commands:

riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum.o sum.c
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum.o sum.c

![Debugging O1](![IMG-20250113-WA0002](https://github.com/user-attachments/assets/aca28883-689b-4840-b03f-ca9c735e1004)

![Debugging Ofast](![IMG-20250113-WA0003](https://github.com/user-attachments/assets/2b7272bb-9d60-42f9-b8eb-3231df155944)


*Running on SPIKE*

Commands:

spike pk sum.o
spike -d pk sum.o


Objdump:

riscv64-unknown-elf-objdump -d sum.o

![Objdump -O1](![IMG-20250113-WA0005](https://github.com/user-attachments/assets/1e44253f-6b25-421a-9a42-d1958a727955)

![Objdump -Ofast](![IMG-20250113-WA0004](https://github.com/user-attachments/assets/48f3a98c-031d-4a1c-9bce-fa4a3693346d)
