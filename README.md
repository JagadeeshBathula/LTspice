# CMOS INVERTER

Designing CMOS INVERTER 

## Tool : LTspice

🛠️ Step-by-Step: Designing CMOS Inverter in LTspice

1. Launch LTspice

Open LTspice

Choose File > New Schematic

2. Add Components

📌 You'll need:

1 × PMOS transistor (pMOS)

1 × NMOS transistor (nMOS)

1 × Vdd (DC voltage source)

1 × Input voltage source (Vin)

1 × Ground

1 × Wire tool

1 × Net name tool (optional for neat labeling)

📌 How to:

Press F2 or click the component symbol (AND gate icon)

Search or scroll to find:

nmos

pmos

Voltage

📌 Build the Inverter Circuit

Connections:

PMOS:

Source → Vdd
Gate → Input (Vin)
Drain → Output node
NMOS:
Source → GND
Gate → Input (Vin)
Drain → Output node (shared with PMOS drain)
Connect Vdd (e.g., 5V) between a voltage source and GND
Connect Vin using a PULSE input for transient or DC sweep for DC analysis
📌 Set Input Voltage Source
For transient simulation, use:
spice
V1 IN 0 PULSE(0 2 2 0.001 0.001 2 4)
0 → low voltage
2 → high voltage
2 → delay
0.001 → rise/fall time
2 → on time
4 → total period
📌 Run Simulations
🧪 DC Sweep:
Click .op → Enter:
spice
.dc V1 0 5 0.01
(If V1 is your input voltage source)
Plot output voltage vs input
⚡ Transient:
Click .tran → Enter:
spice
.tran8
Run the sim, then plot output (V(out)) and input (V(in))
