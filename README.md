# mon-ai: AI Workstation Telemetry Dashboard

A high-precision, multi-threaded terminal dashboard for monitoring AI workstation telemetry, power efficiency, and service readiness. Designed for professional AI workstations featuring high-end hardware (e.g., i9-14900K, RTX 3090 Ti) and multi-monitor creative setups.

## Key Features

### 🖥️ Hardware Telemetry
- **CPU Monitoring:** Real-time utilization, frequency (P-core/E-core aware), and power draw via Intel RAPL.
- **GPU Insight:** NVIDIA-SMI integration for utilization, VRAM allocation (Compute vs. System), temperature, and power consumption.
- **Disk & RAM:** NVMe I/O throughput tracking and ZRAM-aware memory visualization (Physical vs. Compressed).
- **Scheduler & Governor:** Live tracking of the active BPF scheduler (e.g., `scx_lavd`) and CPU power governors.

### ⚡ Energy & Economics
- **Multi-Monitor Power Modeling:** Precise, peripheral-aware modeling for AOC 34" and LG 38" displays.
- **Display Intelligence:** Polling of LG screen states (HDR, VRR, Hz) via `kscreen-doctor` and `ddcutil` to adjust power models dynamically.
- **Local Utility Tiering:** Intelligent cost estimation with dynamic switching between Tier 1 and Tier 2 rates based on consumption.
- **Carbon Footprint:** Real-time CO2 emission tracking and daily/monthly expense projections.
- **Airflow Dynamics:** Modeled chassis fan power with real-time CFM (Cubic Feet per Minute) intake/exhaust balance visualization.

### 🤖 AI Service & Agent Monitoring
- **Service Discovery:** Robust status tracking (`RDY`, `BOOT`, `OFF`) for ComfyUI, SD-WebUI, and Ollama via systemd lifecycle and TCP probe.
- **Agent Integration:** Real-time monitoring of agents like Hermes.
- **Log Narration:** 
  - **Activity Feed:** High-fidelity, color-coded log stream for AI services.
  - **System Journal:** Noise-filtered OS journal events to keep you informed of system-wide changes.

## Commands & Interactivity

The dashboard is fully interactive with real-time stack management:

| Key | Action |
| :--- | :--- |
| `[s]` | **Start AI Stack** (ComfyUI, WebUI, Ollama, Hermes) |
| `[x]` | **Stop AI Stack** (Graceful shutdown & cleanup) |
| `[r]` | **Restart AI Stack** |
| `[y]` | Toggle **ComfyUI** service |
| `[u]` | Toggle **SD-WebUI** service |
| `[o]` | Toggle **Ollama** service |
| `[h]` | Toggle **Hermes Agent** service |
| `[k]` | **Clear** activity feeds |
| `[+/-]` | Increase/Decrease **Polling Rate** (100ms - 2s) |
| `[q]` | **Quit** dashboard |

## Dashboard Preview
![mon-ai Dashboard](dashboard.png)

## Installation & Requirements

1. **Dependencies:** `python3`, `psutil`, `nvidia-smi`, `ddcutil`, `kscreen-doctor`, and `systemctl`.
2. **Setup:** Ensure your AI services are configured as `systemd` user units (e.g., `comfyui.service`).
3. **Usage:** Run `mon-ai` to launch the dashboard.

---
*Developed for the AI-Augmented Creative Workflow.*
