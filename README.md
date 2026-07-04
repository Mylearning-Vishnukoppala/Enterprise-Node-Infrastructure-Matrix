# Enterprise-Node-Infrastructure-Matrix
Enterprise infrastructure monitoring dashboard built using Grafana 13, Prometheus, and Node Exporter.
# Enterprise Node Infrastructure Matrix (Grafana 13 & Prometheus)

[![Grafana Version](https://img.shields.io/badge/Grafana-v13.1.0-orange.svg?style=flat-square&logo=grafana)](https://grafana.com/)
[![Prometheus Support](https://img.shields.io/badge/Prometheus-TSDB-blue.svg?style=flat-square&logo=prometheus)](https://prometheus.io/)
[![Platform Support](https://img.shields.io/badge/Platform-Linux%20%7C%20macOS%20(Darwin)-lightgrey.svg?style=flat-square)](#)
[![Developer Profile](https://img.shields.io/badge/Developer-Mylearning--Vishnukoppala-blue?style=flat-square&logo=github)](https://github.com/Mylearning-Vishnukoppala)

A production-ready, high-density infrastructure observability dashboard architected using **Grafana v13** and **Prometheus TSDB**. This dashboard delivers deep-dive hardware diagnostics, network footprints, storage metrics, and real-time operational triage summaries.

---

## 📸 Dashboard Preview

<img width="2462" height="881" alt="Screenshot 2026-07-05 at 3 21 17 AM" src="https://github.com/user-attachments/assets/a959d459-75d0-4021-b931-259db3a1addc" />
<img width="2465" height="874" alt="Screenshot 2026-07-05 at 3 21 09 AM" src="https://github.com/user-attachments/assets/01d9a860-8ac7-4c98-83c7-9f0a6efe192e" />


*🚀 **Portfolio Tip:** Replace this placeholder with a clean, high-resolution screenshot of your active Grafana dashboard once you take it!*

---

## 🛠️ Tech Stack & Key Competencies
* **Grafana 13 (Dashboard API v2 Format)** – Utilizing modern layout structures, nested rows, dynamic thresholds, and advanced field configurations.
* **Prometheus & PromQL** – Custom multi-variable functions, rate evaluation windows (`$__rate_interval`), and logical fallbacks (`|| vector(0)`) to maintain strict panel resilience.
* **Node Exporter & Cross-Platform Support** – Built with robust, hardware-agnostic queries tailored to bridge OS-level telemetry differences across Linux (`/proc`) and macOS (`Darwin` active/wire/inactive memory models).

---

## 🌟 Core Features & Architecture

### 1. 👑 Executive Management Summary & KPIs
Provides immediate, high-level business logic status. Tracks server runtime status (`up`), dynamic uptime metrics, core load averages (`node_load1`), and a system hardware footprint panel (`node_uname_info`).

### 2. ⚙️ Resource Trends (Clean Production View)
Isolates noise and visual clutter by filtering out non-essential kernel interrupts (like `nice`, `irq`, and `softirq`). Focuses specifically on high-signal user and system process workloads alongside a tailored, cross-platform RAM breakdown history.

### 3. 📂 Process Subsystem, Switches & Scaling
Measures deep OS internals. Tracks context-switching velocities (`rate(node_context_switches_total)`), live open file descriptor limits (`node_filefd_allocated`), and Prometheus P99 scraping latency targets to detect monitoring bottlenecks early.

### 4. 💾 Storage & Network Data Footprints
A highly compatible multi-filesystem data table that catches modern Apple File System (`apfs`) architectures as well as traditional enterprise partitions (`ext4`, `xfs`, `btrfs`). Pairs real-time drive-read throughput curves with granular interface error tracking.

### 5. 🚨 NOC Alerts Triage Summary
Simulates real-time operation center alert evaluation matrices. Using PromQL conditional counting, these panels instantly return a bright, solid green `OK` status under normal conditions and shift to a critical red state when hard infrastructure thresholds are breached:
* **High CPU Utilization** (>85%)
* **High RAM Saturation** (>90%)
* **Storage Array Exhaustion** (>80%)
* **Host Offline / Drop State**

---

## 🌐 Local Verification Footprint
During development, staging, and live verification loops, the active panel variable topology routes across the following target landscape:

* **Staging Environment URI:** `http://localhost:3000/d/enterprise-node-core-matrix/enterprise-node-infrastructure-core-matrix`
* **Assigned Datasource GUID:** `afr4iil5dg5c0a`
* **Telemetry Targets:** `job=node_exporter` | `node=localhost:9100`

---

## 🚀 How to Import & Deploy

1. Ensure **Prometheus** and **Node Exporter** are actively scraping metric targets in your local environment.
2. In your Grafana instance, navigate to **Dashboards** ➡️ **New** ➡️ **Import**.
3. Copy the raw dashboard JSON from this repository's [`dashboard.json`](./dashboard.json) file.
4. Paste it directly into the **Import via panel json** textbox field.
5. Select your local active **Prometheus** data source drop-down menu mapping and click **Import**.

---
*Maintained by [Mylearning-Vishnukoppala](https://github.com/Mylearning-Vishnukoppala).*
