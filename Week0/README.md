# RISC-V Reference SoC Tapeout Program VSD

<div align="center">

[![RISC-V](https://img.shields.io/badge/RISC--V-SoC%20Tapeout-blue?style=for-the-badge&logo=riscv)](https://riscv.org/)
[![VSD](https://img.shields.io/badge/VSD-Program-orange?style=for-the-badge)](https://vsdiat.vlsisystemdesign.com/)
![Participants](https://img.shields.io/badge/Participants-3500+-success?style=for-the-badge)
![India](https://img.shields.io/badge/Made%20in-India-saffron?style=for-the-badge)

</div>

# Program Overview
The RISC-V Reference SoC Tapeout Program, conducted by VSD (VLSI System Design), provides hands-on experience in designing, simulating, and synthesizing a RISC-V based System-on-Chip. Participants learn the complete open-source ASIC flow starting from RTL design to GDSII tapeout.

# Focus Areas:
</div>

This task involves installing and verifying three essential open-source EDA tools: **Yosys**, **Iverilog**, and **GTKWave** on Ubuntu Linux. Each installation step, error resolution, and verification is documented here.

---

## 📋 **Table of Contents**

- [🎯 Overview](#-overview)
- [⚙️ System Requirements](#️-system-requirements)  
- [🎛️ Yosys Installation](#️-yosys-installation---rtl-synthesis-tool)
- [🖥️ Iverilog Installation](#️-iverilog-installation---verilog-simulator)
- [📊 GTKWave Installation](#-gtkwave-installation---waveform-viewer)
- [✅ Installation Verification](#-installation-verification)


---

## 🎯 **Overview**

The **RISC-V Reference SoC Tapeout Program (VSD)** introduces participants to the **RTL → GDSII flow** using **open-source EDA tools**.  

This setup ensures a strong foundation for:  
- **RTL Synthesis (Yosys)**  
- **Simulation & Verification (Iverilog)**  
- **Waveform Debugging (GTKWave)**  

---

## ⚙️ **System Requirements**

<div align="center">

| **Specification** | **Minimum Requirement** | **My System** |
|-------------------|-------------------------|---------------|
| **OS** | Ubuntu 20.04+ | Ubuntu 24.04.3 LTS |
| **RAM** | 4GB+ | 16 GB DDR5 |
| **Storage** | 2GB+ | 512 GB SSD  |
| **CPU** | Dual-core | 14 Cores |
| **Internet** | Required | Available |

</div>

---

## 🎛️ **Yosys Installation - RTL Synthesis Tool**

### 📖 About
[Yosys](https://github.com/YosysHQ/yosys) is an open-source framework for **Verilog RTL synthesis**. It generates gate-level netlists with optimization.  

### 🛠️ Steps
```bash
# Update packages
sudo apt-get update

# Clone Yosys repo
git clone https://github.com/YosysHQ/yosys.git
cd yosys

# Install make (if missing)
sudo apt install make

# Install dependencies
sudo apt-get install build-essential clang bison flex \
  libreadline-dev gawk tcl-dev libffi-dev git \
  graphviz xdot pkg-config python3 libboost-system-dev \
  libboost-python-dev libboost-filesystem-dev zlib1g-dev

# Configure and build
make config-gcc
make

# Install
sudo make install
```


### ✅ Verification
```bash
yosys --version
```
<img width="1038" height="602" alt="yosys" src="https://github.com/user-attachments/assets/f285cced-eb71-4fa2-a290-d906b418d4a3" />


---

## 🖥️ **Iverilog Installation - Verilog Simulator**

### 📖 About
[Iverilog](http://iverilog.icarus.com/) is an IEEE-1364 compliant Verilog simulator used for RTL functional verification.

### 🛠️ Steps
```bash
sudo apt-get update
sudo apt-get install iverilog
```

### ✅ Verification
```bash
iverilog -v
```
<img width="1272" height="708" alt="iverilog" src="https://github.com/user-attachments/assets/fac0cc27-d430-49d9-a51e-17c3fd51ddba" />

---

## 📊 **GTKWave Installation - Waveform Viewer**

### 📖 About
[GTKWave](http://gtkwave.sourceforge.net/) is a waveform viewer to analyze simulation results (VCD/FST files).

### 🛠️ Steps
```bash
sudo apt-get update
sudo apt install gtkwave
```

### ✅ Verification
```bash
gtkwave --version
```
<img width="1267" height="742" alt="gtkwave" src="https://github.com/user-attachments/assets/0d0814fe-bdd4-4574-96e2-36507ca599a8" />


---


---

✅ Setup Validation
Complete Toolchain Status
<div align="center">
ToolPrimary FunctionInstallation StatusVersion Verified🎛️ YosysRTL Synthesis & Optimization✅ Operational✅🖥️ IverilogHDL Simulation Engine✅ Operational✅📊 GTKWaveWaveform Visualization✅ Operational✅
</div>
Environment Readiness Checklist

 All core tools successfully installed
 Version compatibility confirmed
 Dependencies properly resolved
 System integration validated
 Ready for RISC-V development

---



---


## 📝 **Notes**

- Make sure you have sufficient disk space (at least 2GB)
- Internet connection is required for downloading packages
- Installation time may vary based on system specifications
- For WSL users: Ensure X11 forwarding is configured for GTKWave GUI

---

## 🤝 **Contributing**

Feel free to submit issues and enhancement requests!

---

