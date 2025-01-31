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

- Components Required:

VSDSquadron Mini
2 x switch for Input of binary data
7 segment display
Resistors
Breadboard
Jumper Wires
VS Code for Software Development
PlatformIO multi framework professional IDE

- Pinout:

| **Component**           | **Pin/Signal**      | **GPIO Pin** | **Notes**                              |
|--------------------------|---------------------|--------------|-----------------------------------------|
| **Switch 1**            | PD1                | Input        | Connect with pull-up resistor          |
| **Switch 2**            | PD2                | Input        | Connect with pull-up resistor          |
| **7-Segment Display**   | Segment A          | PC0          | 220Ω current-limiting resistor         |
|                          | Segment B          | PC1         | 220Ω current-limiting resistor         | 
|                          | Segment C          | PC2         | 220Ω current-limiting resistor         |
|                          | Segment D          | PC3         | 220Ω current-limiting resistor         |
|                          | Segment E          | PC4         | 220Ω current-limiting resistor         |
|                          | Segment F          | PC5         | 220Ω current-limiting resistor         |
|                          | Segment G          | PC6         | 220Ω current-limiting resistor         |
| **Common Pin**          | Common Cathode     | GND          | If using common anode, connect to VCC  |

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/dc52e2a379a99b3ed9a8d84cd153f68744b9654b/circuit_image.png)

- 4x1 Multiplexer Truth Table:

The 4x1 multiplexer selects one of four input lines (I₀, I₁, I₂, I₃) based on the selection lines S₁ and S₀.

| S₁ | S₀ | Selected Input | Output (Y) |
|----|----|----------------|------------|
|  0 |  0 | 1             | 1         |
|  0 |  1 | 2             | 2         |
|  1 |  0 | 3             | 3         |
|  1 |  1 | 4             | 4         |


- Code:

```c
#include <stdio.h>
#include <debug.h>
#include <ch32v00x.h>

// 7-Segment Hex Values for Numbers 1, 2, 3, 4 (Active LOW for Common Cathode)
uint8_t segment_codes[] = {
    0x06, // 1
    0x5B, // 2
    0x4F, // 3
    0x66  // 4
};

// Function to configure GPIO Pins
void GPIO_Config(void)
{
    GPIO_InitTypeDef GPIO_InitStructure = {0};

    // Enable Clocks for Port D (Switches) and Port C (7-Segment)
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE); // Switches
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOC, ENABLE); // 7-Segment

    // Configure PD1 and PD2 as Input Pins (Selection Lines)
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_1 | GPIO_Pin_2;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU; // Input Pull-Up
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure PC0 to PC6 as Output Pins (7-Segment Display)
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_0 | GPIO_Pin_1 | GPIO_Pin_2 |
                                  GPIO_Pin_3 | GPIO_Pin_4 | GPIO_Pin_5 | GPIO_Pin_6;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP; // Output Push-Pull
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOC, &GPIO_InitStructure);
}

// Function to Display Number on 7-Segment
void DisplayNumber(uint8_t number)
{
    uint8_t i;
    for (i = 0; i < 7; i++)
    {
        // Write each segment value to GPIO pin
        GPIO_WriteBit(GPIOC, (1 << i), (segment_codes[number] & (1 << i)) ? Bit_SET : Bit_RESET);
    }
}

int main()
{
    uint8_t S1, S0; // Selection Lines

    NVIC_PriorityGroupConfig(NVIC_PriorityGroup_1);
    SystemCoreClockUpdate();
    Delay_Init();
    GPIO_Config();

    while (1)
    {
        // Read Selection Lines from Switches
        S1 = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_1); // Switch 1
        S0 = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_2); // Switch 2

        // Decode MUX Logic for 2-bit input
        if (S1 == 0 && S0 == 0)
        {
            DisplayNumber(0); // Display 1
        }
        else if (S1 == 0 && S0 == 1)
        {
            DisplayNumber(1); // Display 2
        }
        else if (S1 == 1 && S0 == 0)
        {
            DisplayNumber(2); // Display 3
        }
        else if (S1 == 1 && S0 == 1)
        {
            DisplayNumber(3); // Display 4
        }
    }
}

```
![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/7a79e29a754cee738e5c4c925f05e33a054c394d/img.jpg)


# Project video:

[video link](https://drive.google.com/file/d/1Dw59QCXSQjPM-lWMM0FLk_V7L0x5yYKN/view?usp=sharing)
