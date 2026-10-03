
# COA_LAB-05
Computer Organization and Architecture Lab

# Computer Organization & Architecture Lab

## Lab 05 – Use of Venus Simulator for Register Level Execution of RISC-V Control Instructions

### Lab Description

The purpose of this lab was to use the Venus RISC-V simulator to understand and implement control instructions in RISC-V assembly language. Different programs were written to explore conditional branching, unconditional jumps, loops, nested loops, bit shifting, and memory operations. The programs were executed in Venus to observe register values and verify their behavior.

The tasks performed in this lab were:

1. Identification of Actual Instructions and Pseudo-Instructions
2. Difference Between Conditional Branching and Jump Instructions
3. Execution Flow Using Branch Instructions
4. Conversion of C Code into RISC-V Assembly
5. Left Shift Operations
6. Implementation of a Counter Loop
7. Array Memory Access Using Loops
8. Implementation of Nested Loops

### Task 1 – Actual Instructions and Pseudo-Instructions

In this task, RISC-V control instructions were classified as actual instructions or pseudo-instructions. Actual instructions are supported by the RISC-V instruction set, whereas pseudo-instructions are assembly-language shortcuts translated into one or more actual instructions by the assembler.

The `beq`, `blt`, `bge`, `bne`, `jal`, and `jalr` instructions were identified as actual instructions. The `ble`, `bgt`, and `j` instructions were identified as pseudo-instructions. Their behavior and classification were studied using the Venus simulator.

**Instructions covered:** `beq`, `blt`, `ble`, `bgt`, `bge`, `bne`, `j`, `jal`, `jalr`

### Task 2 – Conditional Branching and Jump Instructions

In this task, the `beq` and `j` instructions were used to understand the difference between conditional branching and unconditional jumping. The `beq` instruction transfers control to a target label only when two registers contain equal values, whereas the `j` pseudo-instruction always transfers control to its target label.

A short assembly program was executed in Venus to observe how these instructions affect program execution and determine which instructions are skipped.

**Instructions used:** `addi`, `beq`, `j`

### Task 3 – Execution Flow Using Branch Instructions

Two RISC-V assembly programs were implemented to examine how branch conditions affect program execution.

In the first program, registers `s0` and `s1` were assigned the values 4 and 6. Since the values were unequal, the `beq` condition was false, and the addition instruction executed, producing `s2 = 10`.

In the second program, both registers were assigned the value 4. The branch condition was true, so execution transferred to the subtraction instruction, producing `s2 = 0`.

The final register values were examined in Venus to understand conditional execution and control flow.

**Instructions used:** `addi`, `beq`, `add`, `sub`, `j`

### Task 4 – Conversion of C Code into RISC-V Assembly

In this task, a conditional operation was implemented in RISC-V assembly using the given values `a = 5`, `b = 10`, `d = 4`, and `e = 3`.

The `beq` instruction compared the values stored in registers `s0` and `s1`. Since the values were unequal, the branch was not taken, and the program executed the addition instruction. The result, `d + e = 7`, was stored in register `s2`. The subtraction block was skipped, and execution continued to the end label.

The program was simulated in Venus to verify the branch decision and final register values.

**Instructions used:** `addi`, `beq`, `add`, `sub`, `j`

### Task 5 – Left Shift Operations

In this task, the number 2 was initialized in register `s0`. The `slli` instruction was used twice to shift the value one bit to the left on each execution.

Each left shift doubled the value, so the register changed from 2 to 4 and then from 4 to 8. The result was verified using the Venus simulator.

**Instructions used:** `addi`, `slli`

### Task 6 – Implementation of a Counter Loop

A counter loop was implemented using the `blt` branch instruction. Registers `s0` and `s1` were initialized to zero and one, respectively. During each iteration, both registers were incremented, and the value 6 was loaded into register `t0`.

The `blt` instruction compared `s1` with `t0` and returned execution to the `Loop` label while `s1` was less than 6. Once the condition became false, the loop terminated.

The loop behavior and register updates were observed using Venus.

**Instructions used:** `addi`, `blt`

### Task 7 – Array Memory Access Using Loops

In this task, an array of ten words was declared in the data section using the `.data` and `.word` directives. The `la` instruction loaded the base address of the array into register `s1`.

A loop was used to calculate values and store them in consecutive array locations. The `slli` instruction multiplied the loop index by four to obtain the byte offset for each 32-bit integer. The `add` instruction calculated the memory address, and `sw` stored the value at that address.

The loop executed five times, storing the values 5, 6, 7, 8, and 9 in the first five array elements. The memory contents were examined in Venus to verify the results.

**Instructions used:** `.data`, `.word`, `la`, `addi`, `slli`, `add`, `sw`, `blt`

### Task 8 – Implementation of Nested Loops

In this task, nested loops were implemented using RISC-V branch instructions. The outer loop controlled the variable stored in register `s1`, while the inner loop used register `s2` as its counter.

The inner loop executed twice for each outer loop iteration, and the outer loop executed three times. As a result, the inner loop body executed six times in total. The `add` instruction updated register `s0`, while `blt` controlled the repetition of both loops.

The program was simulated in Venus to observe the execution flow and register updates across all iterations.

**Instructions used:** `addi`, `add`, `blt`

### Software Used

- Venus RISC-V Simulator

### Conclusion

This lab provided practical experience with RISC-V control instructions using the Venus simulator. The tasks demonstrated how branching and jumping instructions control program execution, how loops and nested loops implement repetitive operations, and how shift instructions manipulate binary values. Array memory operations also helped develop an understanding of address calculation and data storage. The programs were simulated to observe execution flow and verify register and memory values.
