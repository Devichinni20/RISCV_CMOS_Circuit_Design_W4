
## CMOS Circuit Design 
## 📑 Table of Contents

1. CMOS Circuit Design and SPICE Simulations(#cmos-circuit-design-and-spice-simulations)
   - [Overview](#-overview)
   - [SPICE Simulations in Electronic Circuit Design](#-spice-simulations-in-electronic-circuit-design)
   - [Why Use SPICE Simulations?](#-why-use-spice-simulations)
   - [Example: Inverter Circuit](#-example-inverter-circuit)
   - [Role of SPICE in Inverter Design](#-role-of-spice-in-inverter-design)
   - [CMOS Inverter Circuit Diagram](#-cmos-inverter-circuit-diagram)
   - [Operation Summary](#-operation-summary)
   - [SPICE Simulation Results](#-spice-simulation-results)

2. NMOS Transistor Operation and Characteristics(#️-nmos-transistor-operation-and-characteristics)
   - [Introduction to NMOS in Circuit Design](#-1-introduction-to-nmos-in-circuit-design)
   - [Body Effect (Substrate Bias Effect)](#-2-body-effect-substrate-bias-effect)
   - [Resistive (Linear) Region of Operation](#-3-resistive-linear-region-of-operation)
   - [Drift Current Theory](#-4-drift-current-theory)
   - [Drain Current Model – Linear Region](#-5-drain-current-model--linear-region)
   - [Pinch-Off Condition](#-6-pinch-off-condition)
   - [Saturation Region of Operation](#-7-saturation-region-of-operation)

3. Basic SPICE Setup(#basic-spice-setup)
   - [Circuit Description in SPICE Syntax](#circuit-description-in-spice-syntax)
   - [SPICE Lab with Sky130 Models](#spice-lab-with-sky130-models)
   - [SPICE Simulation Example: day1_nfet_idvds_L2_W5.spice](#day1_nfet_idvds_l2_w5spice)
   - [Plotting Waveforms in Ngspice](#plotting-waveforms-in-ngspice)

---


### 📘 Overview

This project focuses on **CMOS circuit design** and **SPICE-based simulations** to analyze circuit behavior and performance metrics.

---

### ⚙️ SPICE Simulations in Electronic Circuit Design

SPICE (Simulation Program with Integrated Circuit Emphasis) is used to model and verify electronic circuits before fabrication.

### 💡 Why Use SPICE Simulations?

1. **Verify Circuit Functionality:**
   - Ensure that circuits, like logic gates, perform as expected.

2. **Analyze Performance:**
   - Check speed and signal delays to confirm the circuit meets timing requirements.

3. **Evaluate Power Consumption:**
   - Assess how much power the circuit uses and optimize for energy efficiency.

4. **Optimize Design:**
   - Experiment with different configurations to improve circuit performance.

### 🔁 Example: Inverter Circuit

A **CMOS inverter** is used as the basic test case for simulation and analysis.
An inverter is a simple circuit that reverses the input signal:

- **Setup:**
  - Uses two transistors: PMOS and NMOS.
  - PMOS connects to the power supply (VDD), NMOS connects to ground (GND).
  - Both transistors have their gates connected to the input and their drains connected to the output.

- **Operation:**
  - When the input is high, the NMOS transistor conducts, making the output low.
  - When the input is low, the PMOS transistor conducts, making the output high.

### 🧩 Role of SPICE in Inverter Design

SPICE validates the inverter’s switching behavior, voltage transfer characteristics (VTC), and delay parameters.
- **Functionality Check:**
  - Verify that the inverter correctly flips the input signal.

- **Timing Analysis:**
  - Measure how quickly the inverter responds to changes in the input.

- **Power Analysis:**
  - Determine the power usage of the inverter during operation.

SPICE simulations are essential for designing circuits that are reliable and efficient. They help identify issues early and allow for optimization before the physical circuit is built.

### ⚡ CMOS Inverter Circuit Diagram

Consists of a **PMOS** and **NMOS** transistor connected in a complementary configuration.
- **Vin** is applied to both PMOS and NMOS gates.
- **Vout** is taken at the common drain node.
- **PMOS** connects from **VDD** to the output.
- **NMOS** connects from the output to **VSS (GND)**.
- **CL** represents the load capacitance, mimicking the next stage or parasitic load.

<img width="1920" height="1080" alt="Screenshot (185)" src="https://github.com/user-attachments/assets/717e2c63-b2c6-4d20-9368-eccd6d4a9995" />

### 🧠 Operation Summary


| Vin       | PMOS State | NMOS State | Vout     |
|-----------|------------|------------|----------|
| Low (0 V) | ON         | OFF        | High (VDD) |
| High (VDD)| OFF        | ON         | Low (GND)  |

This forms the basis of digital NOT gates used in logic families.

### 📊 SPICE Simulation Results

Simulation shows **VTC curve**, **transient response**, and verifies correct logic operation.
<img width="1920" height="1080" alt="Screenshot (189)" src="https://github.com/user-attachments/assets/1a1c1fbe-6615-49d6-bbe1-4580ad14e448" />

## ⚙️ NMOS Transistor Operation and Characteristics  

### 🧩 **1. Introduction to NMOS in Circuit Design**  
The **NMOS transistor** is a key device in CMOS design, acting as a **switch** or **amplifier** in digital and analog circuits.
<img width="1920" height="1080" alt="Screenshot (155)" src="https://github.com/user-attachments/assets/9e4b6dbb-8c03-4245-a5a0-6b1067db47fd" />

---

### ⚡ **2. Body Effect (Substrate Bias Effect)**  
A change in **body-to-source voltage (V<sub>BS</sub>)** modifies the **threshold voltage (V<sub>th</sub>)**, influencing the transistor’s conduction behavior.

---<img width="1920" height="1080" alt="Screenshot (159)" src="https://github.com/user-attachments/assets/5332aefa-2a5b-4d8c-8d24-b058b6e37461" />

<img width="1920" height="1080" alt="Screenshot (160)" src="https://github.com/user-attachments/assets/f1b68942-0f11-4a85-95e4-05d61b51916d" />
<img width="1920" height="1080" alt="Screenshot (161)" src="https://github.com/user-attachments/assets/6841d381-371c-4d9e-88b4-79d323c9942c" />

### 🔋 **3. Resistive (Linear) Region of Operation**  
When **V<sub>GS</sub> > V<sub>th</sub>** and **V<sub>DS</sub>** is small, the NMOS behaves like a **voltage-controlled resistor**, allowing **linear I–V** behavior.

---<img width="1920" height="1080" alt="Screenshot (162)" src="https://github.com/user-attachments/assets/c964b626-e2f7-4bd0-a116-c42eb73258b1" />


### 🔬 **4. Drift Current Theory**  
The **drain current (I<sub>D</sub>)** mainly results from **electron drift** under the **electric field** between the drain and source terminals.

---

### 📈 **5. Drain Current Model – Linear Region**  
In the resistive region:  
**I<sub>D</sub> ≈ μ<sub>n</sub>C<sub>ox</sub>(W/L)[(V<sub>GS</sub> − V<sub>th</sub>)V<sub>DS</sub> − (V<sub>DS</sub>²/2)]**  
→ current increases **linearly** with **V<sub>DS</sub>**.



### 🚧 **6. Pinch-Off Condition**  
At **V<sub>DS</sub> = V<sub>GS</sub> − V<sub>th</sub>**, the **channel near the drain is pinched off**, marking the **transition** from linear to saturation operation.

<img width="1920" height="1080" alt="Screenshot (163)" src="https://github.com/user-attachments/assets/4cdf04f7-95a8-4748-b859-078e07126978" />
<img width="1920" height="1080" alt="Screenshot (164)" src="https://github.com/user-attachments/assets/5aeeda98-d6ec-4d1a-85d0-8210c6c16fba" />


### 🔥 **7. Saturation Region of Operation**  
For **V<sub>DS</sub> ≥ V<sub>GS</sub> − V<sub>th</sub>**, the current becomes **constant**:  
**I<sub>D</sub> ≈ ½ μ<sub>n</sub>C<sub>ox</sub>(W/L)(V<sub>GS</sub> − V<sub>th</sub>)²**  
→ transistor acts as a **constant current source**.

---
<img width="1920" height="1080" alt="Screenshot (165)" src="https://github.com/user-attachments/assets/3d864351-555d-4281-826c-bf7ae24b8e0c" />
<img width="1920" height="1080" alt="Screenshot (166)" src="https://github.com/user-attachments/assets/00b89101-a866-4943-8756-887f0bd71444" />

### `Basic SPICE Setup`

Fabricating ICs is expensive and time-consuming — even minor silicon revisions can cost millions.  
Simulation tools help designers explore the design space and verify circuits **before fabrication**, saving time and cost.
<img width="1920" height="1080" alt="Screenshot (167)" src="https://github.com/user-attachments/assets/e88dd211-a05d-439f-96cf-f792b0d2be7a" />

Simulators operate at different abstraction levels:

- **Process simulators** (e.g., SUPREME) model how fabrication steps affect device characteristics.
- **Circuit simulators** (e.g., SPICE, Spectre) predict voltages, currents, performance, and power at the transistor level.
- **Logic simulators** (e.g., VCS, ModelSim) verify digital logic written in HDL.
- **Architecture simulators** model high-level behavior (throughput, memory access).

VLSI designers primarily use **circuit** and **logic** simulation.  

**SPICE** (Simulation Program with Integrated Circuit Emphasis), developed at UC Berkeley, solves nonlinear equations for devices such as transistors, resistors, and capacitors.  
Modern SPICE tools include both free versions (Ngspice, LTSpice) and commercial tools (HSPICE, PSPICE).  

SPICE simulators read an input file called a _SPICE deck_, containing:

- **Netlist**: Components and connectivity  
- **Device models & parameters**  
- **Initial conditions**  
- **Inputs (stimulus)**  
- **Simulation options and analysis commands**
<img width="1920" height="1080" alt="Screenshot (168)" src="https://github.com/user-attachments/assets/251dc963-c8f6-40b2-b167-1a2f6062082a" />

<img width="1920" height="1080" alt="Screenshot (167)" src="https://github.com/user-attachments/assets/a1c6c62c-82de-4acf-9e62-6180575a7947" />


<img width="1920" height="1080" alt="Screenshot (170)" src="https://github.com/user-attachments/assets/c4005716-e728-4a94-98a6-090c9aa6802e" />
<img width="1920" height="1080" alt="Screenshot (171)" src="https://github.com/user-attachments/assets/9052d29e-6622-4b6d-a956-549c1c9ea33c" />


The simulator produces waveforms and reports — allowing designers to validate and optimize their circuits before taping out to silicon.

**Analysis Types supported by SPICE:**
| Analysis Type | Details |
|:---|:---|
| DC Analysis | Find the DC operating point of the circuit i.e., all voltages and currents |
| AC Small-Signal Analysis | AC analysis is limited to analog nodes and represents the small signal, sinusoidal solution of the analog system described at a particular frequency or set of frequencies.
| Transient Analysis | Transient analysis is an extension of DC analysis to the time domain. In other words, it solves a DC Analysis for each timestep based on initial conditions. |
| Pole-Zero Analysis | Computes the poles and/or zeros in the small-signal ac transfer function. |
| Small-Signal Distortion Analysis | Computes steady-state harmonic and intermodulation products for small input signal magnitudes. |
| Sensitivity Analysis | Calculate either the DC operating-point sensitivity or the AC small-signal sensitivity of an output variable with respect to all circuit variables, including model parameters. |
| Noise Analysis | Measures the device-generated noise for a given circuit. |
<br>

The following images show how a SPICE deck is written to perform DC analysis of an NMOS transistor:
### `Circuit description in SPICE syntax`

<img width="1920" height="1080" alt="Screenshot (172)" src="https://github.com/user-attachments/assets/7c77aa9e-45b1-4277-88da-42393e613b1f" />


| Line in Netlist | Explanation |
| --------------- | ----------- |
| `M1 vdd n1 0 0 nmos W=1.8u L=1.2u` | Defines NMOS transistor `M1`. Node order: **Drain (vdd), Gate (n1), Source (0), Bulk (0)** — sequence **D G S B**. Model name `nmos` comes from technology file. `W` = gate width (1.8µm), `L` = gate length (1.2µm). |
| `R1 in n1 55` | Series resistor `R1` of 55 ohms between input node `in` and gate node `n1`. |
| `Vdd vdd 0 2.5` | Voltage source `Vdd` applying 2.5V between `vdd` and ground. |
| `Vin in 0 2.5` | Voltage source `Vin` applying 2.5V between input node `in` and ground. |

**Purpose:** This circuit biases an NMOS transistor using `Vin` and `Vdd`, allowing SPICE simulation of its I<sub>D</sub>-V<sub>DS</sub> behavior under specified geometry (W/L) and resistive input.

ℹ️**Note:**  To simulate transistor behavior accurately, SPICE requires a **technology file** that defines the physical and electrical parameters of NMOS/PMOS devices.These parameters include:

- **Threshold voltage** (V<sub>t</sub>)
- **Body effect coefficient** (γ)
- **Oxide thickness** (TOX)
- **Carrier mobility** (U<sub>0</sub>)
- Other technology-specific constants.

In this example:

- The `.include` or `.LIB` command loads the **technology model file** into the simulation (`xxxx_025um_model.mod`).
- The NMOS/PMOS **model names** (like `nmos`, `pmos`) used in the netlist must match those defined in the technology file.

**Simulation goal:**  
To observe how the drain current (I<sub>D</sub>) varies with drain-source voltage (V<sub>DS</sub>) for a fixed gate-source voltage (V<sub>GS</sub>).  

Here:

- V<sub>GS</sub> is fixed at **2.5 V**.
- V<sub>DS</sub> is swept from **0 V to 2.5 V**.
  
### `SPICE Lab with sky130 models`

To use SPICE with sky130 technology, you can clone the relevant GitHub repository containing sky130 models and circuits for simulation.

- **Clone the repo**:  
  Clone the repository with the following command:  
  ```bash
  git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop.git
<img width="1920" height="923" alt="VirtualBox_opensource_tool_ubuntu_14_10_2025_12_04_08" src="https://github.com/user-attachments/assets/df5529fc-2476-4958-9940-96deb688905b" />

  ```

**Important Files in the Repo**:

1. `/sky130CircuitDesignWorkshop/design/sky130_fd_pr/cells/nfet_01v8/sky130_fd_pr__nfet_01v8__tt.pm3.spice`  
   This file contains the SPICE model for the NFET in the sky130 process at typical (tt) conditions.

2. `/sky130CircuitDesignWorkshop/design/sky130_fd_pr/cells/nfet_01v8/sky130_fd_pr__nfet_01v8__tt.corner.spice`
   This file provides the corner model for the NFET, used for simulating different process variations.

3. `/sky130CircuitDesignWorkshop/design/sky130_fd_pr/models/sky130.lib.pm3.spice` 
   This library file contains all the SPICE models for components in the sky130 process node.
```
ℹ️Note: You will find all the SPICE example files inside the **`design`** directory.

```shell
devichinni20@devi-VirtualBox:~/Desktop/sky130CircuitDesignWorkshop/design$ ls
day1_nfet_idvds_L2_W5.spice      day2_nfet_idvgs_L015_W039.spice  day3_inv_vtc_Wp084_Wn036.spice        day5_inv_devicevariation_wp7_wn042.spice  sky130_fd_pr
day2_nfet_idvds_L015_W039.spice  day3_inv_tran_Wp084_Wn036.spice  day4_inv_noisemargin_wp1_wn036.spice  day5_inv_supplyvariation_Wp1_Wn036.spice
```


<img width="1920" height="923" alt="VirtualBox_opensource_tool_ubuntu_14_10_2025_11_59_55" src="https://github.com/user-attachments/assets/30ac8ab8-8de7-443d-a802-f2cc895b0f53" />
<img width="1920" height="923" alt="VirtualBox_opensource_tool_ubuntu_14_10_2025_12_05_09" src="https://github.com/user-attachments/assets/9d381757-c099-4cb4-8d23-7e63e0cc921d" />
<img width="1920" height="923" alt="VirtualBox_opensource_tool_ubuntu_14_10_2025_12_17_57" src="https://github.com/user-attachments/assets/ebb43a67-97be-47dc-84ae-5fba19914464" />

<img width="1920" height="923" alt="VirtualBox_opensource_tool_ubuntu_14_10_2025_13_10_10" src="https://github.com/user-attachments/assets/5630a717-7bfd-4d2d-ad73-fce519216551" />




### 'day1_nfet_idvds_L2_W5.spice'

```
*** Model Description ***
.param temp=27

*** Including sky130 library files ***
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*** Netlist Description ***
XM1 vdd n1 0 0 sky130_fd_pr__nfet_01v8 w=5 l=2
R1 n1 in 55
Vdd vdd 0 1.8
Vin in 0 1.8

*** Simulation Commands ***
.op
.dc Vdd 0 1.8 0.1 Vin 0 1.8 0.2

.control
run
display
setplot dc1
.endc

.end
```



<img width="1920" height="923" alt="VirtualBox_opensource_tool_ubuntu_14_10_2025_13_16_09" src="https://github.com/user-attachments/assets/6753ec2c-13bc-43e8-9710-bb18242ffff9" />



📈**plot the waveforms in ngspice**

```shell
vim day1_nfet_idvds_L2_W5.spice
ngspice day1_nfet_idvds_L2_W5.spice
plot -vdd#branch
```
<img width="1920" height="923" alt="VirtualBox_opensource_tool_ubuntu_14_10_2025_13_44_51" src="https://github.com/user-attachments/assets/e0298dd4-1383-46ab-b175-44a43c6b592f" />


<img width="1920" height="923" alt="VirtualBox_opensource_tool_ubuntu_14_10_2025_13_52_55" src="https://github.com/user-attachments/assets/08361e11-e706-4ecc-a7d2-c07cf60da4be" />

**Id vs Vds for different Vgs - sky130 NMOS (W=5um, L=2um)**


