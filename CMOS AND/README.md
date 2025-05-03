# AND Gate Design using LTspice

This repository contains the schematic, simulation, and analysis of a basic AND logic gate implemented using LTspice. The AND gate is designed using transistor-level components to demonstrate how digital logic can be realized through analog simulation tools.

## 📁 Repository Structure


## 🛠️ Tools Required

- [LTspice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html) (Free SPICE-based simulation software from Analog Devices)

## 🧠 Project Overview

### Objective

Design and simulate a two-input AND gate using transistors in LTspice. The gate should follow the truth table:

| A | B | Output |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   0    |
| 1 | 0 |   0    |
| 1 | 1 |   1    |

### Implementation

- Built using **CMOS logic** (PMOS and NMOS transistors)
- Input voltages toggled via pulse sources or voltage steps
- Output verified using transient analysis

### Key Parameters

- VDD: 5V
- Logic High: 5V
- Logic Low: 0V
- Pulse width and delay configured for logic transitions

## ✅ How to Use

1. Clone the repository or download the `.asc` file.
2. Open `AND_Gate.asc` in LTspice.
3. Run a transient simulation (`Simulate > Run`) to view the waveform.
4. Observe the output waveform and compare it with expected logic behavior.

## 🖼️ Example Output

![AND Gate Waveform](screenshots/and_gate_waveform.png)

## 📚 References

- [CMOS Logic Gate Design Basics](https://en.wikipedia.org/wiki/CMOS)
- [LTspice User Guide](https://www.analog.com/media/en/simulation-models/spice-models/LTspiceGettingStartedGuide.pdf)

## 🔖 License

This project is licensed under the MIT License. See `LICENSE` file for details.




