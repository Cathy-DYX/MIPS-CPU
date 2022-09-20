# MIPS-CPU

This project contains a pipelined and a non-pipelined 5-stage MIPS-compatible CPU, programmed using Verilog. It is produced as part of the EIE 2nd year Instruction Architecture coursework.

## To run the code

Run the bash script <code>test/test_mips_cpu_bus.sh</code> or <code>test/test_mips_cpu_bus_pipeline.sh</code>. It takes a required argument specifying a directory containing an RTL CPU implementation, and an optional argument specifying which instruction to test:

For example, the non-pipelined CPU `rtl/mips_cpu_bus.v` can be tested as follows:
```
$ test/test_mips_cpu_bus.sh rtl
addu_1 addu Pass
addu_2 addu Pass
subu_1 subu Pass
subu_2 subu Pass
```
Restricting it to use the addu instruction:
```
$ test/test_mips_cpu_bus.sh rtl addu
addu_1 addu Pass
addu_2 addu Pass
```
Similarly, the pipelined version can be tested by replacing the bash file with <code>test/test_mips_cpu_bus_pipeline.sh</code>.

## Directories

### docs
This folder contains the data-sheet for the 2 CPUs, outlining the overall architecture and design, and the testing procedure.

### requirement
This folder contains the project requirement and implementation details. It contains the template for signal names and interface timings.

### rtl
<code>rtl/mips_cpu_bus.v</code> and <code>rtl/mips_cpu_bus_pipeline.v</code>: Two implementations of the MIPS CPU: non-pipelined and pipelined. The verilog modules are in the folders <code>rtl/mips_cpu</code> and <code>rtl/mips_cpu_pipeline</code> respectively.

### test
<code>test/test_mips_cpu_bus.sh</code> and <code>test/test_mips_cpu_bus_pipeline.sh</code> : A test-bench for each type of CPU.

The folder <code>test/src</code> contains a mock memory module and a top-level testbench for each version of the CPU.

The folder <code>test/cpp_utils</code> contains a instruction generator to generate random test cases, a MIPS disassembler to convert test cases into assembly code, and a custom MIPS simulator to generate the reference output. 
