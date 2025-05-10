## CMOS OR GATE

🧠 About CMOS OR Gate
A CMOS OR gate is a digital logic gate built using Complementary Metal-Oxide-Semiconductor (CMOS) technology. However, CMOS logic gates like OR and AND are not implemented directly because CMOS naturally favors NAND and NOR gates due to their simple transistor-level design.

Instead, an OR gate in CMOS is typically constructed using a NOR gate followed by an inverter

## circuit 

![Image](https://github.com/user-attachments/assets/8f56d3d7-5f5d-4eb9-9537-8659f55026ef)

## CMOS OR Gate Design in LTspice

This project demonstrates how to design a 2-input CMOS OR gate using LTspice. The OR gate is built using a NOR gate followed by an inverter, based on De Morgan's law. We will also simulate the gate to verify its functionality with different input combinations.

🔧 Tools : LTspice 

Components Used :

CMOS Transistors: PMOS and NMOS

Voltage Sources: For input and power supply

Grounding: For proper circuit operation

## 🧰 Design Overview

A CMOS OR gate is implemented by:

Constructing a NOR gate using:

2 PMOS transistors in series (Pull-up network)

2 NMOS transistors in parallel (Pull-down network)

Inverting the output of the NOR gate using:

1 PMOS transistor

1 NMOS transistor
 
## 🛠️ Step-by-Step Design Process

1. Create a New Schematic in LTspice

Open LTspice and create a new schematic via File > New Schematic.

2. Place Components
   
Press F2 to open the component library, and place the following components:

2 NMOS transistors (nmos)

2 PMOS transistors (pmos)

2 Voltage sources (for inputs A and B)

1 Voltage source for VDD (positive power supply)

3. Construct the NOR Gate
   
PMOS Network (Pull-up):

Connect the sources of both PMOS transistors to VDD.

Connect the gates of the PMOS transistors to inputs A and B respectively.

Connect the drains together to form the output of the NOR gate.

NMOS Network (Pull-down):

Connect the drains of the two NMOS transistors together at the output node.

The sources of the NMOS transistors should be connected to GND.

The gates of both NMOS transistors are connected to inputs A and B.

The output of this stage will give the NOR logic: 

(A + B)`

4. Add the Inverter
   
PMOS Transistor (for Inverter):

Connect the source of the PMOS to VDD.

Connect the gate of the PMOS to the output of the NOR gate.

The drain of the PMOS goes to the final output of the OR gate.

NMOS Transistor (for Inverter):

Connect the source of the NMOS to GND.

Connect the gate of the NMOS to the NOR output.

The drain of the NMOS connects to the final output node.

This inverter will invert the NOR output, resulting in the OR gate output.

(A + B)

5. Add Input Signals

For inputs A and B, use PULSE voltage sources to generate binary signals (0 to 2V) with appropriate timings.

V1 A 0 PULSE(0 2 4 0.001 0.001 4 8)

V2 B 0 PULSE(0 2 2 0.001 0.001 2 4)

6. Connect VDD and Ground
   
Connect VDD to the power rails and ground symbol to the common ground.

7. Set Up Simulation
   
Go to Simulate > Edit Simulation Cmd.

Select Transient analysis to simulate the logic gate over time, 

.tran 8

Place the simulation command on the schematic.

8. Run the Simulation

Click the Run button to simulate the circuit.

Use the probe tool to view the waveforms for inputs A, B, and the output.

📈 Expected OR Gate Truth Table

| A	| B	| Output (OR) |
|---|---|-------------|
| 0 |	0 |   	0       |
| 0 |	1 |   	1       |
| 1 |	0	|     1       |
| 1 |	1 |   	1       |

📁 Project Files
or_gate.asc — LTspice schematic for the CMOS OR gate.

README.md — Project overview and instructions for users.

CONTACT ME:

LinkedIn : http://www.linkedin.com/in/jagadeesh-bathula-246aba300

Mail : jagadeeshbattula0@gmail.com

LICENSE 

This project is verified under MIT LICENSE 

✅ Conclusion
This project shows the design of a CMOS OR gate using a NOR gate followed by an inverter. It demonstrates how to implement basic digital logic gates in CMOS technology, a widely used method in integrated circuit design.
