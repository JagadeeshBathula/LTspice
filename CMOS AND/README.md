# AND Gate 

This repository contains the schematic, simulation, and analysis of a basic AND logic gate implemented using LTspice. The AND gate is designed using transistor-level components to demonstrate how digital logic can be realized through analog simulation tools.

## 🛠️ Tools Required

- [LTspice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html) (Free SPICE-based simulation software from Analog Devices)

## 🧠 Project Overview

### Objective

Design and simulate a two-input AND gate using transistors in LTspice. The gate should follow the truth table:

### Circuit Diagram

![Image](https://github.com/user-attachments/assets/28d3747f-3102-4827-92a5-6efd5dc8e7b3)

### ⚙️ CMOS AND Gate Design in LTspice

🧱 1. Understand the CMOS AND Gate Logic

A 2-input AND gate can be built using a combination of N-MOSFETs and P-MOSFETs:

Output is high only when both inputs are high

You can use DeMorgan’s theorem:

A AND B = NOT (NOT A OR NOT B)

So, an AND gate = Invert the output of an OR gate with inverted inputs.

### 🔧 2. Set Up the Circuit in LTspice

a. Open LTspice and create a new schematic.

b. Add components:

2 × nmos transistors

2 × pmos transistors

2 × voltage sources for inputs A and B

1 × Vdd (e.g., 5V supply)

1 × ground

### c. Build the Circuit:

Connect the 2 pomos parallel and short the source to the vdd supply

Connect the 2 NMOS transistors series to the PMOS then connect to the ground

Take the output fron the center of the transistor(between pull up & pull down network)

### 🧪 3. Add Stimulus

Use PULSE voltage sources for A and B to simulate logic levels.
Example:

scss
Copy
Edit
V1 N001 0 PULSE(0 2 4 0.001 0.001 4 8)

V2 N002 0 PULSE(0 2 2 0.001 0.001 2 4)

These generate combinations of A and B = 00, 01, 10, 11.

### 🖥️ 4. Run the Simulation

Go to Simulate > Edit Simulation Cmd

Choose Transient analysis, e.g., Stop Time = 8

Place the .tran 8 command on the schematic

Run the simulation and plot the output.

### 📈 5. View Results

Click the wire for output and the inputs to see the logic behavior.

You should see output is high only when both inputs are high.

   ### Truth table

| A | B | Output |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   0    |
| 1 | 0 |   0    |
| 1 | 1 |   1    |

## Output Waveform

![Image](https://github.com/user-attachments/assets/01cd4595-199f-4118-bd79-f1625ed73e4f)

## 📚 References

- [CMOS Logic Gate Design Basics](https://en.wikipedia.org/wiki/CMOS)
- [LTspice User Guide](https://www.analog.com/media/en/simulation-models/spice-models/LTspiceGettingStartedGuide.pdf)

## 🔖 License

This project is licensed under the MIT License. See `LICENSE` file for details.

### Contact me 

LinkedIn : http://www.linkedin.com/in/jagadeesh-bathula-246aba300

Mail : jagadeeshbattula0@gmail.com 






