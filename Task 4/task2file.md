# Functional Simulation

# Installing iverilog and gtkwave:

Open terminal and type following:

- sudo apt-get update
- sudo apt-get install iverilog gtkwave

To clone the repository and download the netlist files for simulation , type the following commands in your terminal:

- git clone https://github.com/PyCoder369/VSDSquadron-Mini-research-internship.git
- cd rv32icode

Type the following to simulate and run verilog code:

- iverilog -o rv32icode iiitb_rv32i.v iiitb_rv32i_tb.v
- ./rv32icode

To check output waveform type:

- gtkwave rv32icode.vcd

# Output Waveform

Choose these waveforms

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/1ce79ce5cf739489e242edbe14157d500010aa01/4a.png)

- Instruction 1: ADD R6, R2, R1

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/3c42926b641c19d27697a3e5d5c62838204d5d80/4b.png)

- Instruction 2: SUB R7, R1, R2

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/d39c944b1da9939e7a22e5b63afaf378e265e0cd/4c.png)

- Instruction 3: AND R8, R1, R3

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/14b8aa8894fdda4887b2822d0bdbc381fb5c4c2f/4d.png)

- Instruction 4: OR R9, R2, R5

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/a58468173e5cd1be6ca397f2dd9284921449a69f/4e.png)

- Instruction 5: XOR R10, R1, R4

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/19d1419f9d5902fd79f0473b96d231754c47e636/4f.png)

- Instruction 6: SLT R1, R2, R4

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/7fb5f48e2b0de18d64e61d13f29d983c47ba4271/4g.png)

- Instruction 7: ADDI R12, R4, 5

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/4920a8f1ea53d4b877eb6db47016dd4e43b0360e/4h.png)

- Instruction 8: BEQ R0, R0, 15

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/d2da8a155010ee6de75eb0d1f91c52f70c6e5795/4i.png)

- Instruction 9: BNE R0, R1, 20

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/66bacfd53f47f7c384bee169cc2da0e7b336ec2a/4j.png)

