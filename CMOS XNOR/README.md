# CMOS XNOR

## 🔧 Goal:

Design a 2-input XNOR gate using CMOS transistors (PMOS and NMOS) in LTspice and simulate its behavior.

## Circuit

![Image](https://github.com/user-attachments/assets/87779fad-7a6a-415d-afec-33759781b825)

✅ Step-by-Step Guide

🟩 Step 1: Understand the XNOR Logic

XNOR Logic Expression:

A⊙B= (A⊕B)'

🟩 Step 2: Open LTspice

Launch LTspice.

Go to File > New Schematic.

🟩 Step 3: Add Components

You need:

6 NMOS transistors

6 PMOS transistors

3 voltage sources (VDD, A, B)

Ground  (GND)

To add components:

Press F2 or click the component symbol.

Search for and place:

nmos4 (generic NMOS)

pmos4 (generic PMOS)

voltage (for inputs and VDD)

🟩 Step 4: Build the Circuit

Option 1: CMOS XNOR 

To make XNOR:



⬇️ Transistor-Level XNOR (8 Transistors)


Build the XNOR using NMOS and PMOS transistors arranged to output HIGH only when A = B.

Connect the two pmos's in parallel and connect another two pmos's in parallel and in series with earlier pmos network

connect two nmos's in series and connect other two nmos's in parallel to the erlier nmos's 

check the connections with the schematic

## Schematic Diagram

![Image](https://github.com/user-attachments/assets/5d2d29d7-bf0f-4791-8d33-2e246edf971b)




🟩 Step 5: Add Input Sources

Add A and B Input Signals:

Press F2, place two voltage sources.

Right-click each:

Source A:

PULSE(0 2 4 0.001 0.001 4 8)

Source B:

PULSE(0 2 2 0.001 0.001 2 4)

This will create different timing patterns for A and B.

Add VDD (Power Supply):

Place another voltage source

Set it to DC = 2V

Label it VDD and connect it to PMOS source.

🟩 Step 6: Ground the Circuit

Press G or click the ground symbol.

Connect all appropriate sources to ground.

🟩 Step 7: Name Nodes (Optional)

Press F4 to label nodes.

Label A, B, XNOR_OUT for clarity.

🟩 Step 8: Add Simulation Command

Go to Simulate > Edit Simulation Cmd

Choose Transient

Stop time: 8


Click OK, place on schematic

🟩 Step 9: Run Simulation

Click the running man icon (Run).

After simulation:

Click on nodes A, B, and XNOR_OUT

View waveforms and verify the truth table.

🟩 Step 10: Analyze Output

Check that XNOR output is:

## Truth Table

| A |	B |	XNOR_Out |
|---|---|----------|
| 0 |	0 |    	1    |
| 0 |	1 |   	0    |
| 1 |	0 |   	0    |
| 1 |	1 |   	1    |

## Output Waveform

![Image](https://github.com/user-attachments/assets/d1bb0fb6-57fb-4347-9662-619a72ed99d5)

🧠 Tips
Always cross-check your connections: Source to VDD (PMOS), Source to GND (NMOS)


To avoid manual design, you can also write a behavioral XNOR using a voltage-controlled source:

📁 Project Files

`xnor.asy` — LTspice schematic

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

This project demonstrates how to build and verify a basic CMOS XNOR gate in LTspice using fundamental CMOS principles. It serves as a foundational example for understanding digital logic gates in analog simulation tools.

