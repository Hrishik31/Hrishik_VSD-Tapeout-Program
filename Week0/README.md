# 🛠️ Task 0: System Check and Tool Installation

<div align="center">

![Task](https://img.shields.io/badge/Task-0-brightgreen?style=for-the-badge)
![Tools](https://img.shields.io/badge/Tools-3%20Installed-blue?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Linux-red?style=for-the-badge&logo=linux)

</div>

This task involves installing and verifying three essential open-source EDA tools: **Yosys**, **Iverilog**, and **GTKWave** on Ubuntu Linux. Each installation step, error resolution, and verification is documented here.

---

## 📋 **Table of Contents**

- [🎯 Overview](#-overview)
- [⚙️ System Requirements](#️-system-requirements)  
- [🎛️ Yosys Installation](#️-yosys-installation---rtl-synthesis-tool)
- [🖥️ Iverilog Installation](#️-iverilog-installation---verilog-simulator)
- [📊 GTKWave Installation](#-gtkwave-installation---waveform-viewer)
- [🔧 Troubleshooting](#-troubleshooting-guide)
- [✅ Installation Verification](#-installation-verification)
- [📁 Repository Structure](#-repository-structure)

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
| **RAM** | 4GB+ | 16GB DDR5 |
| **Storage** | 2GB+ | 100GB NVMe SSD |
| **CPU** | Dual-core | 12C/16T |
| **Internet** | Required | ✅ Available |

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

### ⚠️ Error Fix

If you see:
```bash
make: *** [Makefile:811: check-git-abc] Error 1
```

Run:
```bash
git submodule update --init
make
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

## 🔧 **Troubleshooting Guide**

| **Issue**            | **Tool**  | **Solution**                       |
|----------------------|-----------|-----------------------------------|
| Git submodule error  | 🎛️ Yosys | `git submodule update --init`      |
| Missing dependencies | 🎛️ Yosys | Install `build-essential` packages |
| Permission denied    | All       | Run with `sudo`                    |
| Package not found    | All       | `sudo apt-get update` first        |

---

## ✅ **Installation Verification**

<div align="center">

| **Tool**         | **Purpose**            | **Status**      |
|------------------|------------------------|-----------------|
| 🎛️ Yosys        | RTL Synthesis          | ✅ Installed    |
| 🖥️ Iverilog     | Verilog Simulation     | ✅ Installed    |
| 📊 GTKWave       | Waveform Debugging     | ✅ Installed    |

</div>

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

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
