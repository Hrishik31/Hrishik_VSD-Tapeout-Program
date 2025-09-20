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
- [⚙️ System Requirements](#%EF%B8%8F-system-requirements)  
- [🎛️ Yosys Installation](#%EF%B8%8F-yosys-installation---rtl-synthesis-tool)
- [🖥️ Iverilog Installation](#%EF%B8%8F-iverilog-installation---verilog-simulator)
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
⚠️ Error Fix

If you see:
make: *** [Makefile:811: check-git-abc] Error 1
Run:
git submodule update --init
make
sudo make install

✅ Verification
yosys --version

🖥️ Iverilog Installation - Verilog Simulator
📖 About
http://iverilog.icarus.com/ is an IEEE-1364 compliant Verilog simulator used for RTL functional verification.

🛠️ Steps
sudo apt-get update
sudo apt-get install iverilog

✅ Verification
iverilog -v

📊 GTKWave Installation - Waveform Viewer
📖 About
http://gtkwave.sourceforge.net/ is a waveform viewer to analyze simulation results (VCD/FST files).

🛠️ Steps
sudo apt-get update
sudo apt install gtkwave

✅ Verification
gtkwave --version

🔧 Troubleshooting Guide
| **Issue**            | **Tool**  | **Solution**                       |
| -------------------- | --------- | ---------------------------------- |
| Git submodule error  | 🎛️ Yosys | `git submodule update --init`      |
| Missing dependencies | 🎛️ Yosys | Install `build-essential` packages |
| Permission denied    | All       | Run with `sudo`                    |
| Package not found    | All       | `sudo apt-get update` first        |

| Tool         | Purpose            | Status      |
| ------------ | ------------------ | ----------- |
| 🎛️ Yosys    | RTL Synthesis      | ✅ Installed |
| 🖥️ Iverilog | Verilog Simulation | ✅ Installed |
| 📊 GTKWave   | Waveform Debugging | ✅ Installed |
