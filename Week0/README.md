# 🛠️ Task 0: System Check and Tool Installation

<div align="center">

![Task](https://img.shields.io/badge/Task-0-brightgreen?style=for-the-badge)
![Tools](https://img.shields.io/badge/Tools-3%20Installed-blue?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Linux-red?style=for-the-badge&logo=linux)

</div>

This task involves installing and verifying three essential open-source EDA tools: **Yosys**, **Iverilog**, and **GTKWave** on Ubuntu Linux. Each tool installation is documented with commands, error resolution, and verification steps.

---

## 📋 **Table of Contents**

- [🎯 Overview](https://github.com/Hrishik31/RISC-V-SOC-TAPEOUT/blob/main/Task0/README.md#-overview)
- [⚙️ System Requirements](https://github.com/Hrishik31/RISC-V-SOC-TAPEOUT/blob/main/Task0/README.md#%EF%B8%8F-system-requirements)  
- [🎛️ Yosys Installation](https://github.com/Hrishik31/RISC-V-SOC-TAPEOUT/blob/main/Task0/README.md#%EF%B8%8F-yosys-installation---rtl-synthesis-tool)
- [🖥️ Iverilog Installation](https://github.com/Hrishik31/RISC-V-SOC-TAPEOUT/blob/main/Task0/README.md#%EF%B8%8F-iverilog-installation---verilog-simulator)
- [📊 GTKWave Installation](https://github.com/Hrishik31/RISC-V-SOC-TAPEOUT/blob/main/Task0/README.md#-gtkwave-installation---waveform-viewer)
- [🔧 Troubleshooting](https://github.com/Hrishik31/RISC-V-SOC-TAPEOUT/blob/main/Task0/README.md#-troubleshooting-guide)
- [✅ Installing Verification](https://github.com/Hrishik31/RISC-V-SOC-TAPEOUT/blob/main/Task0/README.md#-installation-verification)
- [📁 Repository Structure](https://github.com/Hrishik31/RISC-V-SOC-TAPEOUT/blob/main/Task0/README.md#-repository-structure)

---

## 🎯 **Overview**

This repository contains step-by-step instructions for installing the essential VLSI design toolchain:

Each tool serves a specific purpose in the digital design flow:
- **Yosys**: RTL synthesis and optimization
- **Iverilog**: Verilog simulation and compilation  
- **GTKWave**: Waveform visualization and analysis

---

## ⚙️ **System Requirements**

<div align="center">

| **Specification** | **Minimum Requirement** | **My System** |
|-------------------|-------------------------|---------------|
| **OS** | Ubuntu 20.04+ (or compatible Linux) | Ubuntu 24.04.3 LTS |
| **RAM** | 4GB+ recommended | 16GB DDR5 RAM |
| **Storage** | 2GB+ free space | 100GB NVMe SSD |
| **CPU** | Dual-core processor | 12 cores, 16 threads |
| **Internet** | Required for package downloads | ✅ Available |

</div>

---

## 🎛️ **Yosys Installation - RTL Synthesis Tool**

### 📖 **About Yosys**
Yosys is a framework for RTL synthesis that converts Verilog HDL designs into gate-level netlists with various optimization capabilities.

### 🛠️ **Installation Steps**

```bash
# Step 1: Update system packages
sudo apt-get update

# Step 2: Clone Yosys repository
git clone https://github.com/YosysHQ/yosys.git
cd yosys

# Step 3: Install make (if not present)
sudo apt install make

# Step 4: Install required dependencies
sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev

# Step 5: Configure for GCC
make config-gcc

# Step 6: Build Yosys
make

# Step 7: Install system-wide
sudo make install
