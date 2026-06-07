# Computing Environment

Canonical shared notes about the machines available to Hermes/Codex agents.
This is the machine map for the whole workspace, so every machine can read the same source of truth.

## Usage

- Read this when deciding which machine to use for a task.
- Keep it public, markdown-only, and free of secrets.
- Update it when a machine's hostname, OS, role, or availability changes.
- Hardware specs inform local model and workload decisions.

## Machines

### Rock 5B

- **Device:** Radxa Rock 5B (ARM SBC)
- **OS:** Ubuntu Desktop 24.04
- **Hostname:** `rock5b`
- **Tailscale:** `rock5b.tail49b05.ts.net`
- **IP:** `100.88.123.29`
- **Role:** ARM-based always-on service host
- **Best use:** Persistent lightweight automation and ARM-native services

**Hardware:**
- **CPU:** ARM processor (not x86_64)
- **Memory:** 16GB RAM
- **Storage:** 512GB NVMe
- **WiFi:** Intel AX210NGW adapter (power management disabled for stability)

### Nvidia DGX Spark

- **Device:** Nvidia DGX Spark
- **OS:** DGX OS based on Ubuntu 24.04 LTS
- **Hostname:** `jhm-spark`
- **Tailscale:** `jhm-spark.tail49b05.ts.net`
- **IP:** `100.65.206.95`
- **Role:** Local-model / GPU-heavy machine
- **Best use:** Local LLMs, heavy inference, and GPU workloads

**Hardware:**
- **RAM:** 128GB
- **GPU:** GPU-heavy configuration (exact specs TBD)
- **Primary use case:** Local LLMs and heavy inference tasks

### Apple MacBook Air M5

- **Device:** Apple MacBook Air M5
- **OS:** macOS Tahoe 26.5
- **Hostname:** `jamess-m5-macbook-air`
- **Tailscale:** `jamess-m5-macbook-air.tail49b05.ts.net`
- **IP:** `100.91.49.40`
- **Role:** Interactive Hermes / Codex machine
- **Best use:** Interactive coding, agentic work, and Hermes-driven tasks

**Hardware:**
- **Chip:** Apple M5
- **Memory:** TBD
- **Storage:** TBD
- **Services:** Hermes v0.16.0 running

### Apple Mac mini M4

- **Device:** Apple Mac mini
- **OS:** macOS 26.5.1 (25F80)
- **Hostname:** `mac-mini`
- **Tailscale:** `mac-mini.tail49b05.ts.net`
- **IP:** `100.104.106.122`
- **Role:** Primary control and development workstation
- **Best use:** Main coding work and coordination of other agents via SSH or Telegram

**Hardware:**
- **Model:** Mac16,10 / MU9E3LL/A
- **Chip:** Apple M4
- **CPU:** 10 cores (4 performance, 6 efficiency)
- **GPU:** Built-in Apple GPU (Metal 4)
- **Memory:** 16GB RAM
- **Display:** DELL U2723QE (5120 × 2880; UI at 2560 × 1440 @ 60 Hz)
- **Control tools:** Codex, Claude Code
- **Dashboards:** Hermes, NanoClaw

## Shared workspace notes

- **Workspace root:** `/Users/james/Documents/GitHub`
- **GitHub namespace:** `james-beep-boop`
- **Repo for these notes:** `workstreams` repository
- **All four machines:** permanently reachable over Tailscale
- **All IP addresses (100.x.x.x):** Tailscale addresses; use `rock5b.tail49b05.ts.net`, etc. for hostname-based access
- **Preferred control machine:** Mac mini M4
- **Preferred interactive Hermes machine:** MacBook Air M5

## Source of truth

This file is intended to be the shared computing-environment reference for all machines and agents.
If the setup changes, update this file first and then sync the repo.
