# 🦎 Project Fire-Gecko: UWB Through-Wall Radar Antenna

[English](#english) | [中文](#chinese)

<a name="english"></a>

## 🎯 Project Goal
This module is the **RF Front-end Design** for the *Fire-Gecko* through-wall radar system (based on Zynq-7000 FPGA + High-speed ADC/DAC).
The objective is to design a **1.2 GHz center frequency** Ultra-Wideband (UWB) pulse antenna with **directional radiation** characteristics.

## 🛠️ Design Evolution

### v1.0: Initial Attempt (Failure)
- **Structure**: Trapezoidal Dipole + Shallow Cavity
- **Result**: Severe S11 mismatch (0dB), total reflection.
- **Analysis**: Impedance mismatch at the feed point; phase cancellation due to insufficient cavity depth.
- ![v1_s11_fail](images/v1_fail.png)

### v2.0: Resonance Exploration
- **Improvement**: Introduced **Teardrop Taper** structure; optimized cavity depth.
- **Result**: Distinct resonance observed, but bandwidth was extremely narrow (-38dB sharp dip).
- **Issue**: The structure acted as a high-Q resonator rather than a broadband antenna, making it unsuitable for nanosecond pulse transmission.
- ![v2_narrow](images/v2_narrow.png)

### v3.0: Final Release (Success)
- **Final Specs**:
  - **Antenna Arm**: L = 40mm (Teardrop Taper)
  - **Cavity**: Depth = 50mm (Matched to 1/4 wavelength @ 1.5GHz)
  - **Resistive Loading**: R_load = 12 ohm (To broaden the bandwidth)
- **Performance**:
  - **S11**: < -20dB @ 1.2GHz (Peak -50dB)
  - **Bandwidth**: 0.9 GHz - 1.8 GHz
  - **Directivity**: Excellent Front-to-Back ratio (Unidirectional).
- ![final_s11](images/final_s11.png)
- ![radiation_pattern](images/pattern.png)

## 📂 Files
- `/HFSS_Model`: Ansys HFSS simulation source files (.aedt)
- `/Hardware`: PCB manufacturing files (Gerber/DXF)

---
<a name="chinese"></a>

# 🦎 项目代号 Fire-Gecko: 超宽带穿墙雷达天线设计

## 🎯 项目目标
本项目是基于 **Zynq-7000 FPGA** + **高速 ADC/DAC** 构建的穿墙探测雷达系统的一部分，主要负责**天线射频前端设计**。
设计目标是一款 **1.2 GHz 中心频率**、具有**定向辐射**特性的超宽带 (UWB) 脉冲天线。

## 🛠️ 设计演进

### v1.0: 原始尝试 (Failure)
- **结构**: 梯形偶极子 (Trapezoidal Dipole) + 浅背腔
- **结果**: S11 严重失配 (0dB)，全反射。
- **原因分析**: 馈电处阻抗突变，且背腔深度不当导致相位抵消。

### v2.0: 谐振探索 (Resonance)
- **改进**: 引入水滴形渐变结构 (Teardrop Taper)，优化背腔深度。
- **结果**: 出现明显谐振点，但带宽极窄 (-38dB 尖峰)。
- **问题**: 这是一个高 Q 值谐振器，而非宽带天线，无法传输纳秒级脉冲信号。

### v3.0: 最终定型 (Final Release)
- **最终方案**:
  - **天线尺寸**: L_arm = 40mm (水滴形)
  - **背腔**: H_cavity = 50mm (匹配 1.5GHz 1/4波长)
  - **加载**: R_load = 12 ohm (电阻加载展宽频带)
- **性能指标**:
  - **S11**: < -20dB @ 1.2GHz (峰值 -50dB)
  - **带宽**: 0.9 GHz - 1.8 GHz
  - **方向性**: 单向辐射，前后比极佳 (3D Gain Plot)

## 📂 文件说明
- `/HFSS_Model`: Ansys HFSS 仿真源文件 (.aedt)
- `/Hardware`: PCB 制造文件 (Gerber/DXF)
