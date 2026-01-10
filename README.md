# UWB-AED-Radar-Antenna
**Design of Antipodal Elliptical Dipole Antenna for Through-Wall Radar**
**(Formerly Fire-Gecko UWB Antenna / 原火壁虎穿墙雷达天线)**

[![Status](https://img.shields.io/badge/Status-Optimization_Complete-brightgreen)]()
[![Frequency](https://img.shields.io/badge/Frequency-0.5~2.5GHz-blue)]()
[![Type](https://img.shields.io/badge/Type-Antipodal_Elliptical_Dipole-orange)]()

[English Version](#english-introduction) | [中文介绍](#chinese-introduction)

---

## 🦎 English Introduction

### 🎯 Project Context
This project serves as the Radio Frequency (RF) front-end subsystem for a **Through-Wall Life Detection Radar**. Designed for post-disaster rescue missions, the antenna aims to detect vital signs (heartbeat/respiration) of stationary targets behind walls using Stepped Frequency Continuous Wave (SFCW) radar technology.

### 🔄 Major Design Iteration (V4 Update)
To overcome the bandwidth limitations and assembly complexity of the previous coplanar dipole design, the project has evolved into an **Antipodal Elliptical Dipole (AED)** architecture.

* **Old Design (V3)**: Coplanar Teardrop Dipole. Required a balun chip, difficult to solder, and had limited bandwidth (0.9-1.8 GHz).
* **New Design (V4)**: **Antipodal Elliptical Dipole (AED)**. 
    * **No Balun Needed**: The antipodal structure naturally transitions from unbalanced microstrip to balanced slotline.
    * **Easy Assembly**: SMA connectors can be soldered directly to the feed line.
    * **Ultrawide Bandwidth**: Frequency coverage expanded to **0.5 - 2.5 GHz**, enabling higher range resolution.

### 🧬 Technical Specifications (V4)
* **Architecture**: Antipodal Elliptical Dipole with Back Cavity.
* **Frequency Range**: **0.5 GHz - 2.5 GHz** (S11 < -10 dB).
* **Key Parameters**:
    * Size: $175 \text{ mm} \times 100 \text{ mm}$ arms.
    * Impedance Matching: Optimized with **120Ω loading** and **4.0 mm offset**.
    * Back Cavity: 60mm depth with absorbing material to eliminate back radiation.

### 📂 Repository Structure
* `models/`: Ansys HFSS simulation files (`.aedt`).
* `docs/`: **[Engineering Log](docs/Engineering_Log.md)** (Full design history from V1 failure to V4 success).
* `hardware/`: Gerber files for PCB manufacturing.(temporarily unavailable)

---

## 🦎 中文介绍 (Chinese Introduction)

### 🎯 项目背景
本项目是**穿墙生命探测雷达**的天线子系统，适用于本科毕业设计或工程实践。针对废墟搜救场景，设计了一款高穿透力、高距离分辨率的定向天线。

### 🔄 重大设计迭代 (V4 更新)
针对上一代（V3）同面偶极子天线存在的带宽受限和巴伦芯片焊接困难问题，本项目采用了全新的**反正交椭圆偶极子 (Antipodal Elliptical Dipole, AED)** 架构。

* **旧方案 (V3)**: 电阻加载水滴形偶极子。需要由巴伦芯片进行不平衡-平衡转换，PCB 工艺要求高，且带宽仅覆盖 0.9-1.8 GHz。
* **新方案 (V4)**: **反正交椭圆偶极子 (AED)**。
    * **去除巴伦**: 利用 Antipodal 结构天然实现从微带线到槽线的模式转换，**无需额外的巴伦芯片**。
    * **易于安装**: SMA 接头可直接侧向焊接，结构稳固，适合手工焊接调试。
    * **超宽带性能**: 工作频段扩展至 **0.5 - 2.5 GHz**，大幅提升了雷达的距离分辨率和穿透能力。

### 🧬 技术指标 (V4)
* **架构**: 带背腔的反正交椭圆偶极子。
* **核心指标**: **0.5 GHz - 2.5 GHz** 全频段 S11 < -10 dB。
* **设计亮点**: 
    * 采用 **120Ω 大电阻** 与 **4.0mm 大开口 (Offset)** 配合，完美解决了 AED 天线在 0.7-1.0 GHz 频段常见的“模式切换震荡”问题。
    * 引入 **60mm 深背腔** 与吸波材料，有效抑制后向辐射，净化雷达信号。

### 📂 目录说明
* `models/`: HFSS 仿真源文件 (`.aedt`) 及结构图。
* `docs/`: **[工程设计日志](docs/Engineering_Log.md)** (包含从 V1 到 V4 的完整调试记录、参数扫描分析及 S11 对比图)。
* `hardware/`: PCB 打样制造文件 (Gerber)。(暂时不可用)

---
**Maintainer**: Dr. Charley Chang
