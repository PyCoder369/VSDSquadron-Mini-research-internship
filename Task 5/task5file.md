# Implementing 4x1 mux using VSQSquadron mini board

- Overview:

A 4x1 multiplexer (MUX) is a combinational circuit that selects one of four input lines based on two selection lines and routes it to a single output.
Inputs: Four data inputs (I0, I1, I2, I3) and two selection lines (S1, S0).
Output: The selected data input is routed to the output (Y).

- Implementation Steps:

Hardware Mapping:

Inputs (I0, I1, I2, I3) are controlled via two switches acting as selection lines (S1, S0).
The output (Y) is displayed on a 7-segment LED for visualization.

- Software Simulation:

PlatformIO IDE is used to simulate and program the multiplexer logic on the VSDSquadron Mini board.
The program reads the selection lines and determines the active input to display the corresponding output on the LED.

- Components Required

VSDSquadron Mini
2 x switch for Input of binary data
7 segment display
Resistors
Breadboard
Jumper Wires
VS Code for Software Development
PlatformIO multi framework professional IDE

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/dc52e2a379a99b3ed9a8d84cd153f68744b9654b/circuit_image.png)

4x1 Multiplexer Truth Table
The 4x1 multiplexer selects one of four input lines (I<sub>0</sub>, I<sub>1</sub>, I<sub>2</sub>, I<sub>3</sub>) based on the selection lines S<sub>1</sub> and S<sub>0</sub>.


