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
Task 2:Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler simulator

Debugging with SPIKE: Comparing -O1 and -Ofast Optimizations

-O1: A moderate optimization for balanced performance.

-Ofast: A high-speed optimization that prioritizes performance over strict standards
![image](https://github.com/user-attachments/assets/c3e77cd0-b1d1-445a-b60b-e1164bb41419)


add.c File sum code

Commands:

riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum.o sum.c
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum.o sum.c
![image](https://github.com/user-attachments/assets/7e53f7d1-ce42-4898-8fe1-fa3f66e0ec6a)
![image](https://github.com/user-attachments/assets/dfbbef97-d375-4cdd-bc0c-20dbef6b9ccc)


Debugging O1

Debugging Ofast

Running on SPIKE

Commands:

spike pk sum.o
To open Interactive Debugging

spike -d pk sum.o
Objdump:

riscv64-unknown-elf-objdump -d sum.o
riscv64-unknown-elf-objdump -d sum.o | less
Objdump -O1

Objdump -Ofast
![image](https://github.com/user-attachments/assets/f9f98422-d523-46f2-833c-d358c9b25ba0)
![image](https://github.com/user-attachments/assets/7fa06632-87ec-448c-99d5-20b39384a024)

Task 3: The task is to determine the instruction type for each of the provided instructions and provide their corresponding 32-bit instruction codes in the appropriate format
Understanding RISC-V and Its Instruction Formats
What is RISC-V?
RISC-V is an open-source Instruction Set Architecture (ISA) that enables developers to design processors tailored to specific applications. Based on Reduced Instruction Set Computer (RISC) principles, RISC-V represents the fifth generation of processors built on this concept. Its open and free nature means developers can utilize RISC-V without purchasing licenses, making it a compelling alternative to proprietary processor technologies.

Instruction Formats in RISC-V
The instruction format of a processor defines how machine language instructions are structured for execution. These instructions are composed of binary data (0s and 1s), each segment providing details about data location and operations to be performed. In RISC-V, there are six primary instruction formats:

R-format
I-format
S-format
B-format
U-format
J-format
instructions_types
1. R-type Instruction
R-type (Register-type) instructions operate on registers rather than memory locations. These are used for arithmetic and logical operations. Each instruction is 32 bits and divided into six fields:
![image](https://github.com/user-attachments/assets/71caa4e5-fb47-442d-aa46-62fed3a145e7)


Structure:
Field Name	Size	Description
Opcode	7 bits	Determines the instruction type
rd	5 bits	Destination register
func3	3 bits	Specifies the type of operation
rs1	5 bits	First source register
rs2	5 bits	Second source register
func7	7 bits	Additional operation specification
Example: ADD r9, r2, r5
Operation: Adds values in registers r2 and r5, storing the result in r9.

Field Breakdown:

Opcode: 0110011
rd (Destination): r9 -> 01001
rs1 (Source 1): r2 -> 00010
rs2 (Source 2): r5 -> 00101
func3: 000
func7: 0000000
32-bit Instruction: 0000000_00101_00010_000_01001_0110011

Example: XOR r10, r1, r4
Operation: XOR operation between r1 and r4, result in r10.

Field Breakdown:

Opcode: 0110011
rd (Destination): r10 -> 01010
rs1 (Source 1): r1 -> 00001
rs2 (Source 2): r4 -> 00100
func3: 100
func7: 0000000
32-bit Instruction: 0000000_00100_00001_100_01010_0110011
![image](https://github.com/user-attachments/assets/15b908fe-ecec-4bfd-b04e-922c42fea7e0)


Example: SLT r11, r2, r4
Operation: Sets r11 to 1 if r2 < r4; otherwise, sets r11 to 0.

Field Breakdown:

Opcode: 0110011
rd (Destination): r11 -> 01011
rs1 (Source 1): r2 -> 00010
rs2 (Source 2): r4 -> 00100
func3: 010
func7: 0000000
32-bit Instruction: 0000000_00100_00010_010_01011_0110011
![image](https://github.com/user-attachments/assets/3f44f578-397b-4f79-9bb3-4b1bf88c29f7)


r type

2. I-type Instruction
I-type (Immediate-type) instructions use a register and an immediate (constant) value. These are typically used for load and immediate operations.

Structure:
Field Name	Size	Description
Opcode	7 bits	Determines the instruction type
rd	5 bits	Destination register
func3	3 bits	Specifies the type of operation
rs1	5 bits	Source register
imm[11:0]	12 bits	Immediate value
Example: ADDI r12, r4, 5
Operation: Adds immediate value 5 to the value in r4 and stores it in r12.
Field Breakdown:
Opcode: 0010011
rd (Destination): r12 -> 01100
rs1 (Source): r4 -> 00100
imm[11:0] (Immediate): 000000000101
func3: 000
32-bit Instruction: 000000000101_00100_000_01100_0010011
![image](https://github.com/user-attachments/assets/34310bef-f5b4-4859-859f-23b6f6e8e64d)

i type

3. S-type Instruction
S-type (Store-type) instructions store register values into memory locations.

Structure:
Field Name	Size	Description
Opcode	7 bits	Determines the instruction type
rs1	5 bits	Base address register
rs2	5 bits	Source register
imm[11:5]	7 bits	Upper immediate value
imm[4:0]	5 bits	Lower immediate value
func3	3 bits	Specifies the type of operation
Example: SW r3, 2(r1)
Operation: Stores the value in r3 into the memory at the address r1 + 2.
Field Breakdown:
Opcode: 0100011
rs1 (Base Address): r1 -> 00001
rs2 (Source): r3 -> 00011
imm[11:5] (Upper Immediate): 0000000
imm[4:0] (Lower Immediate): 00010
func3: 010
32-bit Instruction: 0000000_00011_00001_010_00010_0100011
s type

4. B-type Instruction
B-type (Branch-type) instructions handle branching based on conditions.

Structure:
Field Name	Size	Description
Opcode	7 bits	Determines the instruction type
rs1	5 bits	Source register 1
rs2	5 bits	Source register 2
imm[12	10:5	4:1
func3	3 bits	Specifies the condition for branching
Example: BNE r0, r1, 20
Operation: Branches to the address PC + 20 if r0 is not equal to r1.
Field Breakdown:
Opcode: 1100011
rs1: r0 -> 00000
rs2: r1 -> 00001
imm[12|10:5|4:1|11]: 0000010100
func3: 001
32-bit Instruction: 0000000_00001_00000_001_10100_1100011
Example: BEQ r0, r0, 15
Operation: Branches to the address PC + 15 if r0 equals r0 (always true).
Field Breakdown:
Opcode: 1100011
rs1: r0 -> 00000
rs2: r0 -> 00000
imm[12|10:5|4:1|11]: 000001111
func3: 000
32-bit Instruction: 0000000_00000_00000_000_01111_1100011
![image](https://github.com/user-attachments/assets/0469b77b-8db8-4c6d-a826-6ec6be886baf)

b type

5. U-type Instruction
U-type (Upper Immediate) instructions load immediate data into the destination register.

Structure:
Field Name	Size	Description
Opcode	7 bits	Determines the instruction type
rd	5 bits	Destination register
imm[31:12]	20 bits	Upper immediate value
![image](https://github.com/user-attachments/assets/c75d14b1-ea00-4750-a628-3144494c8245)

u type

6. J-type Instruction
J-type (Jump-type) instructions implement jump operations, often used for loops.

Structure:
Field Name	Size	Description
Opcode	7 bits	Determines the instruction type
rd	5 bits	Destination register
imm[20	10:1	11
![image](https://github.com/user-attachments/assets/04360682-d767-4ac0-8948-3feaf08cba1b)

j type

This repository contains a list of 15 unique RISC-V instructions extracted from the assembly code along with their corresponding 32-bit instruction codes. These instructions cover different instruction formats, such as U-type, I-type, J-type, B-type, and R-type.



 TASK 4, you will simulate the RISC-V Core using the provided Verilog netlist and testbench. This involves setting up a simulation environment with tools like Icarus Verilog and GTKWave. You will run the simulation to verify the core's functional correctness, analyze the output signals, and capture waveform snapshots of executed instructions. These snapshots, along with a brief description explaining your understanding of RISC-V functional simulation and verification, should be uploaded to your GitHub repository.
 4. FUNCTIONAL SIMULATION

4.1 About iverilog and gtkwave

Icarus Verilog is an implementation of the Verilog hardware description language.
GTKWave is a fully featured GTK+ v1. 2 based wave viewer for Unix and Win32 which reads Ver Structural Verilog Compiler generated AET files as well as standard Verilog VCD/EVCD files and allows their viewing.
4.2 Installing iverilog and gtkwave
For Ubuntu
Open your terminal and type the following to install iverilog and GTKWave

$   sudo apt get update
$   sudo apt get install iverilog gtkwave
To clone the repository and download the netlist files for simulation , enter the following commands in your terminal.
$ git clone https://github.com/vinayrayapati/iiitb_rv32i
$ cd iiitb_rv32i
To simulate and run the verilog code , enter the following commands in your terminal.
$ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
$ ./iiitb_rv32i
To see the output waveform in gtkwave, enter the following commands in your terminal.
$ gtkwave iiitb_rv32i.vcd

4.3 The output waveform

The output waveform showing the instructions performed in a 5-stage pipelined architecture.

Instruction 1:add r6,r2,r1
![image](https://github.com/user-attachments/assets/ac24b1a8-e165-42d0-98ec-6a933750b2c2)
![image](https://github.com/user-attachments/assets/09bfa323-4da0-48db-9e25-826af77e9da1)
![image](https://github.com/user-attachments/assets/07719e5c-86c1-4bae-9ea5-0f7303031716)
![image](https://github.com/user-attachments/assets/908528b4-9f0f-4268-a76d-2bf8a9e4a92b)
![image](https://github.com/user-attachments/assets/bd86bce4-2212-404a-80d6-ca892ca037c7)
![image](https://github.com/user-attachments/assets/a00a4ad2-6bbc-4f2f-9fc5-63cfc860c7e7)
![image](https://github.com/user-attachments/assets/ca92aab9-6da0-45dd-ad41-c4530e5b1718)
![image](https://github.com/user-attachments/assets/86102da8-8347-4e89-8d58-78c541cfad11)
![image](https://github.com/user-attachments/assets/6c4d4856-d1a9-43fd-b767-2d28cfdbe87b)









