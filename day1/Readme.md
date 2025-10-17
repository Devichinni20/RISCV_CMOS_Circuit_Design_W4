
## CMOS Circuit Design and SPICE Simulations

### 📘 Overview

This project focuses on **CMOS circuit design** and **SPICE-based simulations** to analyze circuit behavior and performance metrics.

---

### ⚙️ SPICE Simulations in Electronic Circuit Design

SPICE (Simulation Program with Integrated Circuit Emphasis) is used to model and verify electronic circuits before fabrication.

### 💡 Why Use SPICE Simulations?

It helps predict circuit performance, identify design issues, and optimize parameters without physical prototyping.

### 🔁 Example: Inverter Circuit

A **CMOS inverter** is used as the basic test case for simulation and analysis.

### 🧩 Role of SPICE in Inverter Design

SPICE validates the inverter’s switching behavior, voltage transfer characteristics (VTC), and delay parameters.

### ⚡ CMOS Inverter Circuit Diagram

Consists of a **PMOS** and **NMOS** transistor connected in a complementary configuration.
<img width="1920" height="1080" alt="Screenshot (185)" src="https://github.com/user-attachments/assets/717e2c63-b2c6-4d20-9368-eccd6d4a9995" />

### 🧠 Operation Summary

* Input high → NMOS ON, PMOS OFF → Output low
* Input low → PMOS ON, NMOS OFF → Output high

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


