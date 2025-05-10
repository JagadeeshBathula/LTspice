# CMOS NAND

A CMOS NAND gate is a basic digital logic gate implemented using Complementary Metal-Oxide-Semiconductor (CMOS) technology. It performs the NAND (Not AND) logical operation, which outputs logic high (1) for all input combinations except when all inputs are high (1).

![Image](https://github.com/user-attachments/assets/63cea4aa-4ff6-4566-9df6-b03faffc6823)

# CMOS NAND Gate Design in LTspice

This project demonstrates the step-by-step design and simulation of a 2-input CMOS NAND gate using LTspice. It includes a schematic-based implementation using PMOS and NMOS transistors and verifies the functionality through transient simulation.

## 🔧 Design Overview

A CMOS NAND gate consists of:

Two PMOS transistors in parallel (Pull-up network)

Two NMOS transistors in series (Pull-down network)

The output is driven high unless both inputs are high, which causes the output to go low — implementing the NAND logic.

🧰 Tools Used : LTspice 

CMOS transistor models (pmos, nmos)

## 🛠️ Step-by-Step Design Process

1. Create a New Schematic

Launch LTspice and open a new schematic via File > New Schematic.

2. Place Components

Press F2 and search for:

nmos → Place two NMOS transistors

pmos → Place two PMOS transistors

voltage → Place three voltage sources (VDD, A, B)

gnd → Place ground symbol

3. Construct the CMOS NAND Gate

PMOS Transistors (Pull-up):

Connect sources to VDD.

Connect gates to inputs A and B.

Connect drains together to the output node.

NMOS Transistors (Pull-down):

Connect in series: Source of bottom NMOS to GND, drain of top NMOS to output.

Gates are also connected to A and B.

4. Add Input Signals

For A and B, define PULSE voltage sources to toggle between logic levels.

Example:

V1 A 0 PULSE(0 2 4 0.001 0.001 4 8)

V2 B 0 PULSE(0 2 2 0.001 0.001 2 4)

V3 Vdd 2

6. Set Up Simulation

Click Simulate > Edit Simulation Cmd.

Choose Transient analysis, e.g.:

.tran 8

Place the simulation command on the schematic.

7. Run the Simulation

Click the Run button.

Probe signals on A, B, and the Output to observe logic levels.

📈 Expected NAND Truth Table

| A	| B	| Output |
|---|---|--------|
| 0	| 0	|   1    |
| 0 |	1	|   1    |
| 1	| 0	|   1    |
| 1 |	1 | 	0    |

📁 Project Files
nand.asc — LTspice schematic

README.md — Project overview and instructions

CONTACT ME :

LinkedIn : http://www.linkedin.com/in/jagadeesh-bathula-246aba300

Mail : jagadeeshbattula0@gmail.com 

## 📚 References

- [CMOS Logic Gate Design Basics](https://en.wikipedia.org/wiki/CMOS)
- [LTspice User Guide](https://www.analog.com/media/en/simulation-models/spice-models/LTspiceGettingStartedGuide.pdf)

## 🔖 License

This project is licensed under the MIT License. See ` MIT LICENSE` file for details.


✅ Conclusion : 

This project demonstrates how to build and verify a basic CMOS NAND gate in LTspice using fundamental CMOS principles. It serves as a foundational example for understanding digital logic gates in analog simulation tools.
