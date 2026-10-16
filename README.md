# 1.8V Two-Stage Miller-Compensated CMOS Operational Amplifier

[![MATLAB R2026a](https://img.shields.io/badge/MATLAB-R2026a-orange.svg)](https://www.mathworks.com/)
[![LTspice](https://img.shields.io/badge/Simulation-LTspice-blue.svg)](https://www.analog.com/)
[![Process](https://img.shields.io/badge/Process-180nm%20CMOS-green.svg)]()
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A complete, specification-driven **1.8V Two-Stage Miller-Compensated CMOS Operational Amplifier** designed using the industry-standard **$g_m/I_D$ methodology** in a $180\text{nm}$ BSIM3v3 process. This repository contains automated MATLAB design scripts, self-contained SPICE model libraries, LTspice testbenches for open-source verification, and PVT corner analysis reports.

---

## Key Performance Specifications

| Performance Metric | Target Specification | Achieved Simulation Result (27°C) |
| :--- | :--- | :--- |
| **Open-Loop DC Gain ($A_{v0}$)** | $\ge 80.0\text{ dB}$ | **$81.2\text{ dB}$** ($11,450\text{ V/V}$) |
| **Unity-Gain Bandwidth ($f_u$ / GBW)** | $\ge 25.0\text{ MHz}$ | **$30.0\text{ MHz}$** (driving $10\text{ pF}$) |
| **Phase Margin (PM)** | $\ge 60.0^\circ$ | **$65.1^\circ$** (nominal) |
| **Worst-Case Corner Phase Margin** | $\ge 55.0^\circ$ | **$58.4^\circ$** (at $125^\circ\text{C}$, Slow Corner) |
| **Slew Rate (SR)** | $\ge 20.0\text{ V/}\mu\text{s}$ | **$23.3\text{ V/}\mu\text{s}$** (rising / falling) |
| **$0.1\%$ Settling Time ($t_s$)** | $\le 80.0\text{ ns}$ | **$58.2\text{ ns}$** ($0.5\text{ V}$ step pulse) |
| **Static Power Dissipation** | $\le 1.00\text{ mW}$ | **$0.86\text{ mW}$** (at $1.8\text{ V}$ supply) |

---

## Repository Directory Structure

```text
Miller_OpAmp/
├── build_miller_opamp_project.m   # Automated MATLAB R2026a builder & plotter script
├── cmos180nm.lib                  # Self-contained 180nm BSIM3v3.3 (LEVEL=8) model card
├── tb_1_gmid_extract.cir          # LTspice gm/Id and current density characterization deck
├── tb_2_opamp_ac_pvt.cir          # LTspice Open-Loop AC stability & PVT corner testbench
├── tb_3_opamp_tran_sr.cir         # LTspice Unity-Gain large-signal transient step testbench
├── fig1_gmid_curves.png           # Extracted JD and fT*Av vs. gm/Id curves
├── fig2_bode_pvt.png              # Bode Magnitude & Phase across temperature corners
├── fig3_step_response.png         # Closed-loop 0.5V step response & 0.1% settling band
└── fig4_rz_nulling_sweep.png      # RHP zero cancellation via nulling resistor Rz
