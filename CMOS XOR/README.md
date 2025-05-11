# CMOS XOR 

A CMOS XOR (Exclusive OR) gate is a digital logic gate built using CMOS (Complementary Metal-Oxide-Semiconductor) technology that outputs 1 only when the number of high inputs is odd. For a 2-input XOR gate, this means it outputs 1 when inputs differ.

🧠 Characteristics

* Higher transistor count than NAND/NOR.

* Used in: Adders (e.g., half adder, full adder), parity generators, and comparators.

* Low power and high speed in CMOS transmission-gate designs.

## 📘 CMOS XOR Gate in LTspice 

This guide explains how to design and simulate a CMOS XOR gate at the transistor level using LTspice.

🛠️ Prerequisites

LTspice installed (e.g., LTspice XVII)

Basic understanding of CMOS circuits

Familiarity with LTspice schematic editor

📐 Step-by-Step Design Instructions

🔹 Step 1: Create a New Schematic

Open LTspice.

Go to File → New Schematic.

🔹 Step 2: Add Components

Press F2 to open the component browser.

Add the following components:

NMOS transistors (nmos)

PMOS transistors (pmos)

Voltage sources (voltage)

Ground (gnd)

Place at least 8 transistors for a standard CMOS XOR configuration (see below).

🔹 Step 3: Arrange the Transistor-Level XOR Circuit

Use the XOR logic equation:

𝑌 = (A'.B + A.b')

Use pull-up and pull-down networks with PMOS and NMOS transistors.

Connect:

PMOS transistors to VDD (typically 5V or 3.3V).

NMOS transistors to GND.

Gate terminals receive logic inputs A and B.

Output node is the XOR result (Y).

📌 Tip: Keep the PMOS in parallel for OR functionality, NMOS in series for AND-like logic.

🔹 Step 4: Add Input Voltage Sources

Press F2 → add voltage sources.

Set them as pulse generators for time-varying input:

Right-click → Advanced → Choose PULSE.

 configurations:

V_A: PULSE(0 2 4 0.001 0.001 4 8)

V_B: PULSE(0 2 2 0.001 0.001 2 4)

🔹 Step 5: Add Power Supply and Ground

Add a DC voltage source for VDD (2V).

Add GND (important for simulation).

🔹 Step 6: Connect the Circuit

Connect inputs (A and B)(A' and B') to transistor gates.

Connect drains and sources correctly between PMOS/NMOS.

Tie VDD and GND where required.

Connect output (Y) to a label or probe point.

🔹 Step 7: Label Nets

Press F4 to label key nodes:

A, B, and Y (output)

Optional: label intermediate nodes for debugging

🔹 Step 8: Add Simulation Command

Press .op or type .tran in the schematic:

.tran 8

Place it on the schematic.

🔹 Step 9: Run the Simulation

Click the "Running Man" icon.

After simulation, click the output node to view the XOR waveform.

### ✅ Expected Behavior(Truth table)
| A |	B |	Y (A ⊕ B) |
|---|---|------------|
| 0 |	0 |   	0      |
| 0 |	1 |   	1      |
| 1 |	0 |   	1      |
| 1 |	1 |   	0      |

