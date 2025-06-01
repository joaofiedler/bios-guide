# ⚡ Low Latency BIOS Guide

<div align="center">

![Hardware](https://img.shields.io/badge/Hardware-Z690_UD-blue?style=for-the-badge)
![CPU](https://img.shields.io/badge/CPU-i9_14900KF-red?style=for-the-badge)
![GPU](https://img.shields.io/badge/GPU-RTX_3070_Ti-green?style=for-the-badge)
![RAM](https://img.shields.io/badge/RAM-32GB_B--die-orange?style=for-the-badge)

**High school hardware enthusiast here. I went deep into BIOS tweaking for at least 3 years chasing better performance.**

</div>

---

- [🎯 What this does? ](#-what-this-does)
- [📊 Monitoring & Validation](#-monitoring--validation)
- [⚠️ Important Notes](#-important-notes)
- [📞 Support](#-support)
- [📚 Additional Resources](#-additional-resources)
---

## 🎯 What This Does

- **Disables CPU power saving** → consistent performance
- **Optimizes memory timings** → faster data access  
- **Removes PCIe latency** → direct GPU communication
- **Eliminates USB polling delays** → responsive peripherals

**Result:** Smoother mouse movement, better hit registration, consistent frame times.

---

## 🚀 Quick Setup (5 mins)

1. Enter BIOS (Delete key)
2. Load optimized defaults
3. Apply these core settings:

```yaml
XMP Profile: Enabled
CPU C-States: Disabled  
Intel SpeedStep: Disabled
Fast Boot: Disabled
PCIe Power Management: Disabled
```

4. Save & exit

**You'll notice the difference immediately.**

---

## 🔧 Advanced Configuration

### CPU Settings
**Path:** `Tweaker → Advanced CPU Settings`

```yaml
# Power Management OFF
Intel SpeedStep (EIST): Disabled
CPU C States: Disabled
Package C State Limit: C0/C1
Enhanced SpeedStep: Disabled

# Performance ON  
Intel Turbo Boost: Enabled
Hyper-Threading: Disabled (only if you have more than 6 cores)
```

**For 14th gen specifically:**
```yaml
Active Turbo Ratios: All cores to 57 (5.7GHz)
AVX Offset: 0
Ring Ratio: 47-50
CPU Voltage: 1.35V-1.40V
```

### Memory Optimization
**Path:** `Tweaker → XMP`

```yaml
XMP Profile: Enabled
Command Rate: 1T  # Critical for latency
Memory Frequency: Highest stable
```

**B-die timings (if you have good RAM):**
```yaml
CAS Latency: 30-32
tRCD: 36-38
tRP: 36-38  
tRAS: 76-80
DRAM Voltage: 1.40V-1.45V
```

### Power Management
**Path:** `Settings → Platform Power`

```yaml
# Disable ALL power saving
RC6 GPU Power Saving: Disabled
C1E Support: Disabled
Energy Efficient Turbo: Disabled
Speed Shift: Disabled
Hardware P-States: Disabled
```

### PCIe & Connectivity
```yaml
Above 4G Decoding: Enabled (test off tho)
Resizable BAR: Enabled  
PCIe Link State Power Management: Disabled
ASPM Support: Disabled
```

### USB Optimization
```yaml
Legacy USB Support: Disabled (will make ur mouse un-usable when installing a new windows through windows (windows media creation tool)
XHCI Hand-off: Enabled
USB Transfer Timeout: 1 sec
Unused USB ports: Disabled
```

### Disable Unnecessary Features
```yaml
Internal Graphics: Disabled
Onboard Audio: Disabled (use USB/external DAC)
WiFi: Disabled (ethernet only)
Virtualization: Disabled
Secure Boot: Disabled (needed for fortnite competitive and w11)
```

---

## 📊 Monitoring & Validation

### 🔍 Stability Testing
1. **MemTest86** - 4+ passes for RAM
2. **Prime95** - 30min small FFTs for CPU
3. **Game for 2+ hours** - real world test

### 📈 Benchmarking Tools
- **Input Lag**: RTSS Frame Time Analysis
- **Memory**: AIDA64 Memory Benchmark  
- **CPU**: OCCT, Linkpack
- **Gaming**: 3DMark Time Spy

### Warning Signs
- Random crashes during gaming or benchmark
- Visual artifacts
- BSOD errors
- Inconsistent performance

---

## ⚠️ Important Notes

**You NEED good cooling.** These settings disable thermal protection.

**Test everything step by step.** Don't apply all settings at once.

---

## 📞 Support

- **Discord:** @pingofv | https://discord.gg/jkkQR6tu37

---

### 📚 Additional Resources
- [Intel Overclocking Guide](https://www.intel.com/content/www/us/en/gaming/overclocking-intel-processors.html)
- [Memory Overclocking Guide](https://github.com/integralfx/MemTestHelper)

---

<div align="center">

### ⭐ If this guide helped you, please give it a star!

**Made by me for the hardware enthusiast community**

</div>
