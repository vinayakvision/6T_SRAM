# 6T SRAM Cell Design in Cadence Virtuoso

## 📌 Overview
This repository contains the **6T SRAM Cell Design** implemented in **Cadence Virtuoso**. The project includes:
- **Schematic Design**
- **Testbench Simulation**
- **DRC (Design Rule Check)**
- **LVS (Layout vs. Schematic Check)**
- **RC Extraction**
- **Performance Analysis**

## 🛠 Design Steps
### 1️⃣ Schematic Design
- The **6T SRAM Cell** is designed using **Cadence Virtuoso Schematic Editor**.
- It consists of **6 transistors** (2 NMOS, 2 PMOS in cross-coupled inverters, and 2 access NMOS transistors).

### 2️⃣ Testbench Simulation
- A **testbench** is created to verify the **Read and Write operations**.
- **Stimulus signals** are applied to the **Word Line (WL)** and **Bit Lines (BL, BL̅)**.

### 3️⃣ DRC (Design Rule Check)
- Ensures the schematic and layout follow **fabrication rules**.
- Checked using **Cadence Assura / Calibre DRC**.

### 4️⃣ LVS (Layout vs. Schematic)
- Ensures the **layout matches the schematic**.
- Verified using **Cadence Assura / Calibre LVS**.

### 5️⃣ RC Extraction
- Extracts **parasitic resistance and capacitance** to analyze the impact on performance.
- Performed using **Cadence Quantus**.

### 6️⃣ Performance Analysis
- Analyzed **Read/Write Delay, Power Consumption, and Stability**.
- Performed **Transient and DC Analysis** in **Cadence Spectre**.

## ⚙️ 6T SRAM Cell Operation
The **6T SRAM Cell** operates in three modes:

### ✅ **1. Hold State (Idle Mode)**
- **Word Line (WL) = 0**, both access transistors **OFF**.
- Cross-coupled inverters **retain data** at **Q and Q̅**.

### ✅ **2. Write Operation**
1. Apply **Word Line (WL) = 1** (Turns ON access transistors).
2. Force data on **Bit Lines (BL & BL̅)**:
   - **BL = 1, BL̅ = 0** → Stores **'1'**.
   - **BL = 0, BL̅ = 1** → Stores **'0'**.
3. Inverters switch states accordingly.
4. **WL = 0** (Turns OFF access transistors), data is latched.

### ✅ **3. Read Operation**
1. Precharge **BL and BL̅ to VDD**.
2. Enable **WL = 1** (Turns ON access transistors).
3. Stored value at **Q or Q̅ discharges the corresponding bitline**.
4. **Sense amplifier detects the small voltage difference and amplifies it**.
5. Read operation completes when **WL = 0**.

## 📂 Project Structure
```
📦 6T-SRAM-Cell
 ┣ 📜 schematic/          # Cadence Virtuoso schematic files
 ┣ 📜 testbench/          # Testbench setup for simulations
 ┣ 📜 drc_lvs/            # DRC & LVS reports
 ┣ 📜 extraction/         # RC Extraction files
 ┣ 📜 analysis/           # Power & Performance analysis reports
 ┣ 📜 README.md           # Project Documentation
```

## 🚀 How to Run Simulations
1. **Open Cadence Virtuoso**.
2. Load the **6T SRAM Cell Schematic**.
3. Open the **Testbench** and apply Read/Write stimulus.
4. Run **Transient Analysis** using **Spectre Simulator**.
5. Perform **LVS and DRC checks**.
6. Run **RC Extraction** and analyze delays.

## 📢 Future Improvements
- **Low-Power Design Optimization** (High-Vt Transistors, Sleep Mode Transistors)
- **Bitline Precharge Optimization**
- **Multi-Port SRAM for High-Performance Computing**

---
### 🔗 **Author:** [Vinayak Venkappa Pujeri](https://github.com/vinayakvision)
📧 Contact: vision.vinayak12@gmail.com
