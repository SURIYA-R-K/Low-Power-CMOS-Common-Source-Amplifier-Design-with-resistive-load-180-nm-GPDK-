# Design and Simulation of a Common-Source Amplifier with Resistive Load  
### Cadence Virtuoso | GPDK 180 nm


This repository contains the **design and simulation files** for a **common-source (CS) amplifier** implemented in **Cadence Virtuoso** using the **GPDK 180 nm** CMOS technology. The amplifier uses a **resistive load** and **voltage divider biasing** to achieve stable operation at **50 µA drain current** from a **1.8 V supply**.

---

##  Tools & Technology
- **EDA Tool**: Cadence Virtuoso (IC6.1.8)
- **Simulator**: Spectre
- **Technology Node**: GPDK 180 nm
- **Supply Voltage**: 1.8 V

---

##  Circuit Description
- **Topology**: NMOS Common-Source Amplifier
- **Load**: Resistive load (**Rd = 18 kΩ**)
- **Bias Current**: 50 µA
- **Biasing Network**: Voltage divider (**R1 = 10 kΩ, R2 = 5.45 kΩ**) for precision gate bias
- **Input Coupling**: 2.2 µF capacitor for AC signal injection
- **Transistor Sizing**: W = 3.9 µm, L = 180 nm

The resistive load provides a simple and predictable design, while the voltage divider ensures accurate biasing independent of process variations. A coupling capacitor isolates the DC bias from the input signal source.

---

##  Characterization & Design Flow
- **NMOS Characterization**: Extracted threshold voltage (**Vth ≈ 542.6 mV**) from DC sweep analysis.
- **Transistor Sizing**: Optimized width to achieve target bias current while maintaining saturation.
- **Biasing Verification**: Confirmed **Vgs ≈ 635 mV**, **Vds ≈ 0.9 V**, ensuring saturation region operation (**Vds > Vov ≈ 92 mV**).
- **Small-Signal Parameters**: Measured **gm = 578 µS**, **ro ≈ 18 kΩ** from operating point analysis.

---

##  Simulations Performed

### 1. DC Operating Point Analysis
- Verified all transistors in saturation.
- Confirmed **Id = 50.01 µA**, **Vout_DC = 0.9 V**.

### 2. AC Small-Signal Analysis
- Measured midband gain: **8.32 V/V (18.4 dB) at 1 kHz**.
- Extracted **-3 dB bandwidth ≈ 2 kHz**.
- Phase response confirmed **180° inversion** (common-source behavior).


### 3. Transient Analysis
- Applied **1 kHz, 10 mVpp** input sine wave.
- Observed **83 mVpp** output swing with clean waveform and **180° phase shift**.
- Verified linear operation with no visible distortion.


---

##  Performance Summary
| Parameter | Value |
|-----------|-------|
| Technology | GPDK 180 nm |
| Supply Voltage | 1.8 V |
| Bias Current | 50 µA |
| Load Resistance (Rd) | 18 kΩ |
| Threshold Voltage (Vth) | 542.6 mV |
| Transconductance (gm) | 578 µS |
| Output Resistance (ro) | 18 kΩ |
| Voltage Gain (AC) | **8.32 V/V (18.4 dB)** |
| Bandwidth (-3 dB) | ~2 kHz |
| Power Consumption | **90 µW** (50 µA × 1.8 V) |

---

