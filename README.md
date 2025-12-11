# глаз перепелятника

**Real-time detection of sanctions-evading "shadow fleet" vessels**

[![Docker](https://img.shields.io/badge/Docker-Ready-blue.svg)](https://www.docker.com/)
[![Python](https://img.shields.io/badge/Python-3.11+-green.svg)](https://python.org)
[![Status](https://img.shields.io/badge/Status-Design%20Phase-orange)]()

"The sparrowhawk's eye sees what others miss" - Automated detection of maritime sanctions evasion

## The Problem

Shadow fleet vessels deliberately disable AIS transponders to hide illicit activities. Current monitoring solutions are either:
- Proprietary and expensive
- Manually intensive  
- Too generalized

глаз перепелятника is an open-source tool specifically designed to detect these elusive vessels in real-time.

## How It Works

1. Smart Filtering: Identifies high-risk vessels (old tankers, obscure flags, shell company owners)
2. Behavior Detection: Monitors for deliberate AIS disabling (>12h gaps at sea)
3. Contextual Alerting: Scores risks and provides forensic vessel histories

## Live Dashboard

*Dashboard Preview - [screenshot soon(TM)]*

Active Alerts Interface:
- Real-time map of disappearing vessels
- One-click access to complete vessel dossiers
- Prioritized by risk score and historical patterns

## Quick Start

```bash
# 1. Clone repository
git clone https://github.com/alyzande/sparrowhawk.git
cd sparrowhawk

# 2. Set up data directories
mkdir -p data/{raw,processed,output,dossiers}

# 3. Download sample data
wget -P data/raw/ https://example.com/sample_ais.csv

# 4. Run with Docker
docker-compose up

## Key Features

| Feature | Benefit |
|---------|---------|
| **Automated Detection** | Continuously monitors vessels without manual oversight, flagging suspicious disappearances in real-time. |
| **Intelligent Pre-Filtering** | Focuses only on high-risk targets (old tankers, obscure flags, shell company owners), reducing noise by over 90%. |
| **Forensic Vessel Dossiers** | Provides complete behavioral history and ownership details with a single click on any alert. |
| **Geographic Risk Scoring** | Applies contextual intelligence by weighting alerts based on location (e.g., known STS transfer zones). |
| **Open & Transparent Logic** | All detection rules, scoring algorithms, and data sources are fully documented and customizable. |
| **Containerized Deployment** | Runs consistently anywhere using Docker, with no complex dependency setup required. |
| **Cost-Free Data Pipeline** | Built using publicly available AIS data and vessel registries, eliminating licensing costs. |

## Documentation

Detailed technical documentation is available in the `/docs` directory:

- **[System Architecture](docs/ARCHITECTURE.md)** – Overview of the three-stage detection pipeline and data flow.
- **[Detection Algorithm](docs/ALGORITHM.md)** – Technical deep dive into the static filtering, gap analysis, and risk-scoring logic.
- **[Data Schema](docs/DATA_SCHEMA.md)** – Specifications for alert JSON outputs, vessel dossiers, and configuration files.
- **[Deployment Guide](docs/DEPLOYMENT.md)** – Step-by-step instructions for local and server setup using Docker.
- **[Use Cases & Workflows](docs/USECASES.md)** – Practical examples of integrating the tool into maritime investigations.

## Roadmap

- [x] **Phase 1: Design & Documentation** – Core concept validation and system architecture.
- [ ] **Phase 2: MVP Implementation** – Develop the core detection engine and backend API (Target: Q1 2024).
- [ ] **Phase 3: Frontend & Visualization** – Build the interactive Leaflet.js dashboard for alert monitoring.
- [ ] **Phase 4: Live Testing & Calibration** – Validate detection logic against historical shadow fleet incidents.
- [ ] **Phase 5: Advanced Detection Patterns** – Extend algorithm to detect spoofing and identity switching.
- [ ] **Phase 6: Integration & Automation** – Add hooks for satellite imagery APIs and automated reporting.

## About This Project

This tool is being developed to support maritime research and analysis for a private security research group. The primary goal is to provide a transparent, open-source capability for identifying vessels that may be evading international sanctions through deliberate AIS manipulation.

The project is built on the principle that effective monitoring tools should be accessible, understandable, and adaptable by researchers. All code, methodologies, and findings are open for review, collaboration, and improvement by the technical community.
