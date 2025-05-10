# CMOS NOR

CMOS NOR (Complementary Metal-Oxide-Semiconductor NOR) is a digital logic gate implemented using CMOS technology that performs the NOR (NOT OR) operation. 
A NOR gate logic gate that outputs true (1) only when all inputs are false (0). It is the combination of an OR gate followed by a NOT gate.

## CIRCUIT

![Image](https://github.com/user-attachments/assets/ba37fe25-7851-4e44-9ea7-e5625601cc1f)

## SCHEMATIC

![Image](https://github.com/user-attachments/assets/49866b93-0029-44bf-aea1-1f9e39c02737)

## 🧪 Step-by-Step Design: CMOS NOR Gate in LTspice

✅ Goal

Design a 2-input CMOS NOR gate using:

Two PMOS transistors in series

Two NMOS transistors in parallel

1. Start LTspice and Create a New Schematic

Open LTspice

Go to File → New Schematic

Save your file with a name like cmos_nor.asc

2. Place Components

Press F2 to open the component selector. You will need the following:

a. PMOS Transistors (2x)

Search: pmos

Select the default pmos symbol

Place two PMOS transistors in series

Source of top PMOS → VDD

Drain of top PMOS → source of bottom PMOS

Drain of bottom PMOS → output node

b. NMOS Transistors (2x)

Search: nmos

Select the default nmos symbol

Place two NMOS transistors in parallel

Both sources → GND

Both drains → output node

c. Voltage Sources (3x)

Search: voltage

Place:

VDD (e.g., 2v) → power supply

V_A and V_B → inputs A and B

d. Ground

Press G or choose from the toolbar to place GND

Connect all grounds

Connect VDD to the source of the top PMOS

Tie all GND references together

PMOS Series Network:

Connect drain of bottom PMOS to output node

Connect gate of each PMOS to input signals A and B

NMOS Parallel Network:

Connect both drains to output node

Connect sources to ground

Connect gate of each NMOS to inputs A and B

4. Label Important Nodes

Use the label tool (F4) to label:

Inputs: A, B

Output: Y

VDD: VDD

5. Set Up Input Pulses

Double-click V_A and V_B, set the source type to PULSE.

 PULSE settings 
 
 for V_A:

PULSE(0 2 4 0.001 0.001 4 8)

 for V_B:

PULSE(0 2 2 0.001 0.001 2 4)

These create square waves to test all input combinations (00, 01, 10, 11).

7. Set Up Simulation

Add a .tran command:

Go to Edit → Spice Directive

.tran 8

Place the directive on your schematic.

8. Run the Simulation
Click the Run (Man Running) icon

## truth table

| Input A |	Input B	|	NOR Output (A + B)` |
|---------|---------|---------------------|
|    0    |   0     |		      1           |
|    0    | 	1     |     		0           |
|    1    |  	0  	  |       	0           |
|    1    |  	1     |     		0           |

## OUTPUT WAVEFORM

![Image](https://github.com/user-attachments/assets/fb53e2e9-4319-4188-bb66-12cbb2269d2d)

CONTACT ME :

LinkedIn : http://www.linkedin.com/in/jagadeesh-bathula-246aba300

Mail : jagadeeshbattula0@gmail.com 

## 📚 References

- [CMOS Logic Gate Design Basics](https://en.wikipedia.org/wiki/CMOS)
- [LTspice User Guide](https://www.analog.com/media/en/simulation-models/spice-models/LTspiceGettingStartedGuide.pdf)

## 🔖 License

This project is licensed under the MIT License. See ` MIT LICENSE` file for details.


✅ Conclusion
This project demonstrates how to build and verify a basic CMOS NOR gate in LTspice using fundamental CMOS principles. It serves as a foundational example for understanding digital logic gates in analog simulation tools.

