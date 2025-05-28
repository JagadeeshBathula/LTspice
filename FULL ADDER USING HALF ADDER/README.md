# FULL ADDER USING HALF ADDERS

## ✅ Overview

A Full Adder adds three inputs: A, B, and Cin (Carry In), and produces two outputs: Sum and Cout (Carry Out). The Boolean equations are:

Sum = A ⊕ B ⊕ Cin

Cout = (A ⋅ B) + (Cin ⋅ (A ⊕ B))

We’ll use two Half Adders:

First Half Adder: Adds A and B → produces Sum1 = A ⊕ B, Carry1 = A ⋅ B

Second Half Adder: Adds Sum1 and Cin → produces Sum = Sum1 ⊕ Cin, Carry2 = Sum1 ⋅ Cin

Final Cout = Carry1 + Carry2

![Image](https://github.com/user-attachments/assets/1d188a89-e0b9-4cae-884a-437f8e7801a5)

## 🛠 Step-by-Step LTspice Design

### Step 1: Design Basic Gates

Before building a Half Adder, you need to design:

XOR gate

AND gate

OR gate

You can use CMOS transistor-level designs or behavioral logic gates using *.subckt definitions. Let's proceed with behavioral modeling (for simplicity).

Option 1: Behavioral Logic Using Voltage Sources and Vswitch

Or

Option 2: Use .subckt macros for gates (recommended)

Step 2: Create Half Adder Subcircuit

A Half Adder has:

Inputs: A, B

Outputs: Sum (A ⊕ B), Carry (A ⋅ B)

Create a subcircuit like:

* Half Adder Subcircuit
  
.subckt HALF_ADDER A B SUM CARRY

X1 A B XOR1 SUM  ; XOR gate

X2 A B AND1 CARRY ; AND gate

.ends HALF_ADDER

Step 3: Create Full Adder Using Two Half Adders

* Full Adder Using Two Half Adders
  
.subckt FULL_ADDER A B Cin SUM Cout

* Internal nets
  
.node SUM1 C1 C2

* First Half Adder
  
XHA1 A B SUM1 C1 HALF_ADDER

* Second Half Adder
  
XHA2 SUM1 Cin SUM C2 HALF_ADDER

* OR gate for Cout
  
XOR1 C1 C2 Cout

.ends FULL_ADDER

Step 4: Top-Level Testbench in LTspice

* Testbench
  
Vdd Vdd 0 DC 2

VinA A 0 PULSE(0 2 8 0.001 0.001 8 16)

VinB B 0 PULSE(0 2 4 0.001 0.001 4 8)

VinCin Cin 0 PULSE(0 2 2 0.001 0.001 2 4)

XFA A B Cin SUM Cout FULL_ADDER

.tran 16

.control

run

## CIRCUIT DESIGN

![Image](https://github.com/user-attachments/assets/a643585a-d78d-4a2e-bd42-6f41d7e49343)


plot V(A) V(B) V(Cin) V(SUM) V(Cout)

.endc

.end

## Full Adder Truth Table

| A | B | Cin | Sum | Cout |
|---|---|-----|-----|------|
| 0 | 0 |  0  |  0  |  0   |
| 0 | 0 |  1  |  1  |  0   |
| 0 | 1 |  0  |  1  |  0   |
| 0 | 1 |  1  |  0  |  1   |
| 1 | 0 |  0  |  1  |  0   |
| 1 | 0 |  1  |  0  |  1   |
| 1 | 1 |  0  |  0  |  1   |
| 1 | 1 |  1  |  1  |  1   |


# OUTPUT WAVEFORM

![Image](https://github.com/user-attachments/assets/5c0fc2fc-20e2-48f8-b895-3005b55c019e)


##📚 References

Digital Design – M. Morris Mano

A foundational textbook that explains combinational circuits, logic gates, and adder circuits in detail.

LTspice Documentation – Analog Devices

https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html

Official documentation and download page for LTspice.

CMOS Digital Logic Design Tutorials

Various online resources for CMOS-based logic gate design (e.g., All About Circuits, Electronics Tutorials).

##✅ Conclusion

This project demonstrates how a Full Adder can be constructed using two Half Adders in LTspice. By breaking down the logic into reusable components and simulating them, we gain practical insights into digital logic design and circuit behavior. It’s a great example of modular design and verification using simulation tools.

Feel free to fork, modify, or build on this project. Contributions and suggestions are always welcome!

🔗 Connect

If you found this useful or have suggestions, feel free to reach out or connect with me on LinkedIn – I’d love to hear your feedback or collaborate on similar projects!

LinkedIn : http://www.linkedin.com/in/jagadeesh-bathula-246aba300

Mail : jagadeeshbattula0@gmail.com 

## 🪪 License

This project is licensed under the [MIT License](LICENSE).

📁 Project Files

`FA BY HA.asc` LTspice schematic

README.md — Project overview and instructions







