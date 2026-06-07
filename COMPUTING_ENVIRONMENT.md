# Computing Environment

Canonical shared notes about the machines available to Hermes/Codex agents.
This is the machine map for the whole workspace, so every machine can read the same source of truth.

## Usage

- Read this when deciding which machine to use for a task.
- Keep it public, markdown-only, and free of secrets.
- Update it when a machine's hostname, OS, role, or availability changes.

## Machines

### Rock 5B
- **Device:** Radxa Rock 5B (ARM SBC)
- **OS:** Ubuntu Desktop 24.04
- **Hostname:** `rock5b`
- **Tailscale:** `rock5b.tail49b05.ts.net`
- **IP:** `100.88.123.29`
- **Role:** ARM-based always-on service host
- **Best use:** Persistent lightweight automation and ARM-native services

### Nvidia DGX Spark
- **Device:** Nvidia DGX Spark
- **OS:** DGX OS based on Ubuntu 24.04 LTS
- **Hostname:** `jhm-spark`
- **Tailscale:** `jhm-spark.tail49b05.ts.net`
- **IP:** `100.65.206.95`
- **Role:** Local-model / GPU-heavy machine
- **Best use:** Local LLMs, heavy inference, and GPU workloads

### Apple MacBook Air M5
- **Device:** Apple MacBook Air M5
- **OS:** macOS Tahoe 26.5
- **Hostname:** `jamess-m5-macbook-air`
- **Tailscale:** `jamess-m5-macbook-air.tail49b05.ts.net`
- **IP:** `100.91.49.40`
- **Role:** Interactive Hermes / Codex machine
- **Best use:** Interactive coding, agentic work, and Hermes-driven tasks

### Apple Mac mini M4
- **Device:** Apple Mac mini
- **OS:** macOS 26.5.1 (25F80)
- **Hostname:** `mac-mini`
- **Tailscale:** `mac-mini.tail49b05.ts.net`
- **IP:** `100.104.106.122`
- **Role:** Primary control and development workstation
- **Best use:** Main coding work and coordination of other agents via SSH or Telegram

## Shared workspace notes

- **Workspace root:** `/Users/james/Documents/GitHub`
- **GitHub namespace:** `james-beep-boop`
- **Repo for these notes:** this `workstreams` repository
- **All four machines:** permanently reachable over Tailscale
- **Preferred control machine:** Mac mini M4
- **Preferred interactive Hermes machine:** MacBook Air M5

## Source of truth

This file is intended to be the shared computing-environment reference for all machines.
If the setup changes, update this file first and then sync the repo.
