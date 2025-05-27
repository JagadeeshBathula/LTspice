# FULL ADDER

To design a full adder in LTspice using only logic gates, we break the circuit into its basic logic expressions: Sum = A ⊕ B ⊕ Cin and Cout = (A·B) + (Cin·(A⊕B)). In LTspice, we use built-in digital logic gate components—XOR, AND, and OR—from the "Digital" component library. First, we generate input signals A, B, and Cin using PULSE voltage sources to cycle through all possible input combinations over time. The circuit is constructed by first computing A ⊕ B using an XOR gate, then XORing that result with Cin to get the Sum. For the carry-out (Cout), two AND gates are used to compute A·B and Cin·(A⊕B), and their outputs are combined using an OR gate. A transient simulation is run using the .tran directive, and the outputs Sum and Cout are plotted over time to verify correct operation against the full adder truth table. This gate-level approach provides a clear, modular, and simulation-friendly method for designing and testing a full adder in LTspice without dealing with transistor-level complexity.

✅ Goal
Design a 1-bit Full Adder using only:

XOR gates

AND gates

OR gates

Inputs:
A, B, Cin

Outputs:
Sum = A ⊕ B ⊕ Cin

Cout = (A·B) + (Cin·(A⊕B))

🧱 Step-by-Step in LTspice (Gate-Level)
📥 Step 1: Create Inputs
Use PULSE sources to apply input combinations.

spice
Copy
Edit
V_A A 0 PULSE(0 1 0ns 1ns 1ns 10ns 20ns)
V_B B 0 PULSE(0 1 0ns 1ns 1ns 20ns 40ns)
V_Cin Cin 0 PULSE(0 1 0ns 1ns 1ns 40ns 80ns)
This sequence will cycle through all 8 combinations of A, B, and Cin.

⚙️ Step 2: Use Logic Gates
Use LTspice’s digital gates from the library Digital.

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

🧪 Step 4: Add Simulation Command
Use a transient analysis command:

spice
Copy
Edit
.tran 0 100n
📊 Step 5: Run & Plot
After running:

Plot Sum and Cout vs time.

Compare waveform with full adder truth table.


