# 🚀 Ultra Low Latency BIOS Optimization Guide

<div align="center">

![Hardware](https://img.shields.io/badge/Hardware-Z690_UD-blue?style=for-the-badge)
![CPU](https://img.shields.io/badge/CPU-i9_14900KF-red?style=for-the-badge)
![GPU](https://img.shields.io/badge/GPU-RTX_3070_Ti-green?style=for-the-badge)
![RAM](https://img.shields.io/badge/RAM-32GB_B--die-orange?style=for-the-badge)

**Extreme BIOS tweaks for minimum input lag in competitive gaming**

[📖 Documentation](#documentation) • [⚙️ Quick Setup](#quick-setup) • [🛠️ Advanced Tweaks](#advanced-tweaks) • [⚠️ Warnings](#warnings)

</div>

---

## 📋 Table of Contents

- [🎯 Overview](#-overview)
- [💻 Compatible Hardware](#-compatible-hardware)
- [⚡ Quick Setup](#-quick-setup)
- [🔧 Detailed Configuration](#-detailed-configuration)
  - [CPU Settings](#1-cpu-settings-máxima-responsividade)
  - [Memory Optimization](#2-memory-optimization-b-die-extremo)
  - [Power Management](#3-power-management-zero-latência)
  - [PCIe Optimization](#4-pcie-optimization)
  - [USB Settings](#5-usb-settings-ultra-low-latency)
  - [Advanced Tweaks](#8-advanced-tweaks-extremo)
- [🖥️ Windows Optimization](#-windows-optimization)
- [📊 Monitoring & Validation](#-monitoring--validation)
- [⚠️ Important Warnings](#️-important-warnings)
- [🤝 Contributing](#-contributing)

---

## 🎯 Overview

This guide provides **extreme BIOS optimizations** specifically designed to achieve **minimum possible input lag** for competitive gaming. These tweaks disable power-saving features, optimize memory timings, and configure the system for maximum responsiveness.

### 🎮 Target Use Cases
- **Competitive eSports** (CS2, Valorant, Apex Legends)
- **Professional Gaming**
- **Ultra-low latency streaming**
- **High-refresh rate gaming** (240Hz+)

### 📈 Expected Results
- ⚡ **5-15ms reduction** in input lag
- 🔄 **More consistent frame times**
- 🎯 **Improved mouse precision**
- 📊 **Better 1% and 0.1% lows**

---

## 💻 Compatible Hardware

### ✅ Primary Tested Configuration
| Component | Model | Notes |
|-----------|--------|-------|
| **Motherboard** | Gigabyte Z690 UD | BIOS F20+ recommended |
| **CPU** | Intel i9-14900KF | Requires excellent cooling |
| **GPU** | RTX 3070 Ti | Any RTX 30/40 series |
| **RAM** | 32GB Samsung B-die | DDR5-5600+ recommended |

### 🔄 Other Compatible Hardware
- **Z690/Z790 chipset** motherboards
- **12th/13th/14th gen Intel** CPUs
- **Samsung B-die or Hynix A-die** memory
- **RTX 30/40 series** or **RX 6000/7000** GPUs

---

## ⚡ Quick Setup

### 🚀 Fast Track (5 minutes)
1. **Enter BIOS** (Delete key during boot)
2. **Load Optimized Defaults**
3. **Apply these critical settings:**
   ```
   CPU C-States: Disabled
   Intel SpeedStep: Disabled
   XMP Profile: Enabled
   Fast Boot: Disabled
   ```
4. **Save & Exit**

### 📋 Essential Checklist
- [ ] CPU C-States disabled
- [ ] Power management features disabled
- [ ] XMP/EXPO memory profile enabled
- [ ] PCIe power management disabled
- [ ] Fast boot disabled
- [ ] Profile saved to BIOS

---

## 🔧 Detailed Configuration

### 1. CPU SETTINGS (Máxima Responsividade)
**Path: `Tweaker → Advanced CPU Settings`**

#### Basic Configuration
```yaml
Intel SpeedStep (EIST): Disabled
Intel Turbo Boost: Enabled
CPU C States: Disabled
Package C State Limit: C0/C1 State
Hyper-Threading: Disabled (eSports) / Enabled (modern games)
```

#### Advanced for i9-14900KF
```yaml
Active Turbo Ratios: 57 (5.7GHz) - all cores
AVX Offset: 0
Ring/Cache Ratio: 47-50
CPU Load-Line Calibration: Level 6-7
CPU Core Voltage: 1.35V-1.40V
CPU Ring Voltage: Core +0.05V
```

### 2. MEMORY OPTIMIZATION (B-die Extremo)
**Path: `Tweaker → Extreme Memory Profile`**

#### Primary Timings (32GB B-die)
```yaml
Memory Frequency: DDR5-6000+
Command Rate: 1T
CAS Latency (CL): 30-32
RAS to CAS Delay (tRCD): 36-38
Row Precharge (tRP): 36-38
Active to Precharge (tRAS): 76-80
```

#### Secondary Timings
```yaml
tRC: 112-120
tRFC: 350-400
tWR: 24
tRRD_S: 6
tRRD_L: 8
tCWL: 22-24
```

#### Memory Voltages
```yaml
DRAM Voltage: 1.40V-1.45V
CPU VDDQ: 1.30V-1.35V
CPU VDD2: 1.35V-1.40V
```

### 3. POWER MANAGEMENT (Zero Latência)
**Path: `Settings → Platform Power`**

```yaml
RC6 GPU Power Saving: Disabled
C1E Support: Disabled
Enhanced SpeedStep: Disabled
Energy Efficient Turbo: Disabled
Race To Halt: Disabled
Hardware P-States: Disabled
Speed Shift: Disabled
```

### 4. PCIe OPTIMIZATION
**Path: `Settings → IO Ports`**

```yaml
Above 4G Decoding: Enabled
Resizable BAR: Enabled
PCIe Link State Power Mgmt: Disabled
ASPM Support: Disabled
PCIe Slot 1: Gen4 x16 (GPU)
```

### 5. USB SETTINGS (Ultra Low Latency)
**Path: `Settings → IO Ports → USB Configuration`**

```yaml
Legacy USB Support: Disabled
XHCI Hand-off: Enabled
USB Standby Power: Disabled
USB Transfer Timeout: 1 sec
Unused USB Ports: Disabled
```

### 6. INTEGRATED FEATURES
```yaml
Internal Graphics: Disabled
Onboard Audio: Disabled
Onboard LAN: Disabled (use dedicated NIC)
WiFi: Disabled (use Ethernet)
```

### 7. BOOT & SECURITY
```yaml
Fast Boot: Disabled
Ultra Fast Boot: Disabled
CSM Support: Disabled
Secure Boot: Disabled
Intel PTT: Disabled
```

### 8. ADVANCED TWEAKS (Extremo)

#### Memory Sub-timings
```yaml
tREFI: 65535
tRFC2: 250-300
tRFC4: 150-200
tFAW: 32-36
tRTP: 12
tCCD_L: 8
```

#### CPU Advanced Features
```yaml
Virtualization: Disabled
VT-d: Disabled
CFG Lock: Disabled
Overclocking Lock: Disabled
```

---

## 🖥️ Windows Optimization

### ⚡ Essential Commands
```cmd
# High Performance Power Plan
powercfg -setactive 8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c

# Timer Resolution
bcdedit /set disabledynamictick yes
bcdedit /set useplatformclock no
bcdedit /set useplatformtick yes
```

### 🛠️ Recommended Tools
| Tool | Purpose | Setting |
|------|---------|---------|
| **TimerTool.exe** | System timer | 0.5ms resolution |
| **Process Lasso** | CPU priority | Game boost mode |
| **MSI Afterburner** | GPU overclock | +150 core, +500 memory |
| **LatencyMon** | Latency monitoring | DPC analysis |

### 📝 Registry Tweaks
```reg
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\PriorityControl]
"Win32PrioritySeparation"=dword:00000026

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters]
"TcpAckFrequency"=dword:00000001
"TCPNoDelay"=dword:00000001
```

---

## 📊 Monitoring & Validation

### 🌡️ Safe Temperature Limits
| Component | Max Temp | Critical Temp |
|-----------|----------|---------------|
| **CPU** | 85°C | 90°C |
| **Memory** | 50°C | 55°C |
| **VRM** | 90°C | 100°C |

### 🔍 Stability Testing
1. **Memory**: MemTest86 (4+ passes)
2. **CPU**: Prime95 Small FFTs (30 min)
3. **Gaming**: 2+ hours stress gaming
4. **Monitoring**: HWiNFO64 continuous

### 📈 Benchmarking Tools
- **Input Lag**: RTSS Frame Time Analysis
- **Memory**: AIDA64 Memory Benchmark  
- **CPU**: Cinebench R23
- **Gaming**: 3DMark Time Spy

### ⚠️ Instability Signs
- 🔴 BSOD during gaming
- 🔴 Visual artifacts
- 🔴 Random crashes
- 🔴 Inconsistent performance

---

## ⚠️ Important Warnings

### 🚨 CRITICAL SAFETY NOTES

> **⚠️ HIGH RISK CONFIGURATION**
> 
> These settings disable thermal protection and power management. **Excellent cooling is mandatory.**

### 📋 Before You Start
- [ ] **Premium cooling solution** (240mm+ AIO or high-end air)
- [ ] **High-quality PSU** (80+ Gold, 750W+)
- [ ] **Stress testing tools** ready
- [ ] **Temperature monitoring** software installed
- [ ] **BIOS backup** created

### 🔥 Cooling Requirements
- **CPU Cooler**: 250W+ TDP rating
- **Case Airflow**: Positive pressure setup
- **Ambient Temperature**: <25°C recommended
- **VRM Cooling**: Active cooling preferred

### ⚡ Power Requirements
- **PSU Quality**: 80+ Gold minimum
- **Wattage**: 750W+ recommended
- **12V Rail**: Single rail preferred
- **Efficiency**: High efficiency under load

---

## 🤝 Contributing

### 📝 How to Contribute
1. **Fork** this repository
2. **Test** configurations on your hardware
3. **Submit** detailed results with specs
4. **Create** pull requests with improvements

### 🔬 Needed Testing
- [ ] Different Z690/Z790 motherboards
- [ ] Various CPU models (12th/13th gen)
- [ ] Different memory types (Hynix A-die, Micron B-die)
- [ ] AMD platform equivalent settings

### 📊 Reporting Results
Please include:
- **Full hardware specifications**
- **BIOS version**
- **Before/after benchmarks**
- **Stability test duration**
- **Temperature readings**

---

## 📞 Support & Community

### 💬 Discussion
- **Issues**: Use GitHub Issues for bugs/problems
- **Discussions**: Use GitHub Discussions for general questions
- **Discord**: [Link to community server if available]

### 📚 Additional Resources
- [Intel Overclocking Guide](https://www.intel.com/content/www/us/en/gaming/overclocking-intel-processors.html)
- [Memory Overclocking Guide](https://github.com/integralfx/MemTestHelper)
- [Latency Optimization](https://www.reddit.com/r/CompetitiveMinecraft/comments/performance)

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

### ⭐ If this guide helped you, please give it a star!

**Made with ❤️ for the competitive gaming community**

[![GitHub stars](https://img.shields.io/github/stars/username/repo-name?style=social)](https://github.com/username/repo-name/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/username/repo-name?style=social)](https://github.com/username/repo-name/network/members)

</div>