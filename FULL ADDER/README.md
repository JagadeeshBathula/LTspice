# FULL ADDER

To design a full adder in LTspice using only logic gates, we break the circuit into its basic logic expressions: Sum = A ⊕ B ⊕ Cin and Cout = (A·B) + (Cin·(A⊕B)). In LTspice, we use built-in digital logic gate components—XOR, AND, and OR—from the "Digital" component library. First, we generate input signals A, B, and Cin using PULSE voltage sources to cycle through all possible input combinations over time. The circuit is constructed by first computing A ⊕ B using an XOR gate, then XORing that result with Cin to get the Sum. For the carry-out (Cout), two AND gates are used to compute A·B and Cin·(A⊕B), and their outputs are combined using an OR gate. A transient simulation is run using the .tran directive, and the outputs Sum and Cout are plotted over time to verify correct operation against the full adder truth table. This gate-level approach provides a clear, modular, and simulation-friendly method for designing and testing a full adder in LTspice without dealing with transistor-level complexity.

## HAND NOTES

![Image](https://github.com/user-attachments/assets/018099cc-8870-47cc-af2b-a4b9ab3def8b)

![Image](https://github.com/user-attachments/assets/e965decd-45d0-4289-b54b-da052e91be93)

### ✅ Goal

Design a 1-bit Full Adder using only:

XOR gates

AND gates

OR gates

Inputs:

A, B, Cin

Outputs:

Sum = A ⊕ B ⊕ Cin

Cout = (A·B) + (Cin·(A⊕B))

### 🧱 Step-by-Step in LTspice (Gate-Level)

📥 Step 1: Create Inputs

Use PULSE sources to apply input combinations.

spice

V_A A 0 PULSE(0 2 8 0.001 0.001 8 16)

V_B B 0 PULSE(0 2 4 0.001 0.001 4 8)

V_Cin Cin 0 PULSE(0 2 2 0.001 0.001 2 4)

This sequence will cycle through all 8 combinations of A, B, and Cin.

⚙️ Step 2: Use Logic Gates

Use LTspice’s digital gates from the library Digital or external ()

You can insert these by:

Press F2 → Digital

Choose:

xor (XOR gate)

and (AND gate)

or (OR gate)

🔧 Step 3: Build the Full Adder Logic

Circuit structure:

xor1_out = A ⊕ B

Sum = xor1_out ⊕ Cin

and1_out = A · B

and2_out = Cin · xor1_out

Cout = and1_out + and2_out

How to wire it:

Connect A and B to XOR1 → output: xor1_out

Connect xor1_out and Cin to XOR2 → output: Sum

Connect A and B to AND1 → output: and1_out

Connect xor1_out and Cin to AND2 → output: and2_out

Connect and1_out and and2_out to OR → output: Cout

## circuit Design

![Image](https://github.com/user-attachments/assets/6dd023c9-e1ea-458b-abfd-bae41284ab5d)


🧪 Step 4: Add Simulation Command

Use a transient analysis command:

spice

.tran 16

📊 Step 5: Run & Plot

After running:

Plot Sum and Cout vs time.

Compare waveform with full adder truth table.

## output Waveform

![Image](https://github.com/user-attachments/assets/0bae8e56-fdf4-412d-98f9-994d63d1a330)

## ✅ Conclusion

Designing a full adder in LTspice using logic gates provides a clear and effective way to understand and simulate digital arithmetic circuits. By implementing the full adder with basic gates—XOR, AND, and OR—we can directly model the logical expressions for Sum and Carry-out (Cout). Using PULSE voltage sources, we systematically apply all possible input combinations of A, B, and Cin to verify the circuit’s functionality over time. Additionally, implementing the full adder using two half adders demonstrates modular design, where smaller building blocks are combined to form more complex systems. LTspice's transient simulation and built-in digital components make it a powerful tool for verifying digital logic behavior before physical implementation. This gate-level simulation approach serves as a strong foundation for further exploration in VLSI, digital design, and logic verification.




