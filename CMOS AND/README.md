# AND Gate 

This repository contains the schematic, simulation, and analysis of a basic AND logic gate implemented using LTspice. The AND gate is designed using transistor-level components to demonstrate how digital logic can be realized through analog simulation tools.

## 🛠️ Tools Required

- [LTspice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html) (Free SPICE-based simulation software from Analog Devices)

## 🧠 Project Overview

### Objective

Design and simulate a two-input AND gate using transistors in LTspice. The gate should follow the truth table:

### Circuit Diagram

![Image](https://github.com/user-attachments/assets/28d3747f-3102-4827-92a5-6efd5dc8e7b3)



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

   ### Truth table

| A | B | Output |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   0    |
| 1 | 0 |   0    |
| 1 | 1 |   1    |

## 📚 References

- [CMOS Logic Gate Design Basics](https://en.wikipedia.org/wiki/CMOS)
- [LTspice User Guide](https://www.analog.com/media/en/simulation-models/spice-models/LTspiceGettingStartedGuide.pdf)

## 🔖 License

This project is licensed under the MIT License. See `LICENSE` file for details.

### Contact me 

LinkedIn : http://www.linkedin.com/in/jagadeesh-bathula-246aba300

Mail : jagadeeshbattula0@gmail.com 






