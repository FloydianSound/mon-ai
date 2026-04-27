# mon-ai: AI Workstation Telemetry Dashboard

A high-precision, multi-threaded terminal dashboard for monitoring AI workstation telemetry, power efficiency, and service readiness. Designed for professional AI workstations with RTX 3090 Ti and multi-monitor setups.

## Features

### System & Telemetry
- **Hardware-First Monitoring:** Real-time CPU (Intel RAPL), GPU (NVIDIA-SMI), and Disk (NVMe IO Throughput) telemetry.
- **Dynamic Airflow:** Modeled chassis fan power (5W-54W) with airflow (CFM) intake/exhaust balance visualization.
- **Peripheral Precision:** HDR and VRR/Refresh-Rate aware power modeling for multi-monitor setups using `ddcutil` and `kscreen-doctor`.
- **ZRAM/Storage:** Stacked bar visualization of RAM efficiency and storage utilization.

### Energy & Economics
- **Local Utility Rates:** Intelligent, dynamic tier-switching (Tier 1/Tier 2) based on daily projected consumption.
- **Economic Estimates:** Real-time monthly/daily cost projections and CO2 footprint tracking.

### AI Service Monitoring
- **Robust Service Discovery:** Service status (`RDY`/`BOOT`/`OFF`) is determined via systemd service lifecycle tracking and raw TCP socket probes. This ensures the dashboard remains accurate even if the AI application becomes unresponsive.
- **Activity Feed:** Filtered, high-fidelity logs for AI services with visual color-coded markers.
- **System Journal:** Dedicated, noise-filtered feed for all remaining OS-level journal events.

## Dashboard Preview
![mon-ai Dashboard](dashboard.png)
