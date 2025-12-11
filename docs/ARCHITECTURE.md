# System Architecture

## High-Level Overview

глаз перепелятника uses a three-stage detection pipeline to identify shadow fleet vessels:

\`\`\`
┌─────────────────────────────────────────────────────────────┐
│                    DATA SOURCES (External)                   │
│  • Global Fishing Watch AIS Archive                         │
│  • Equasis Vessel Registry                                  │
│  • Port Authority Lists                                     │
└───────────────────────┬─────────────────────────────────────┘
                        │
┌───────────────────────▼─────────────────────────────────────┐
│                CONTAINERIZED ANALYSIS SYSTEM                │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐    │
│  │   STAGE 1   │    │   STAGE 2   │    │   STAGE 3   │    │
│  │ Static      │───▶│ Behavioral  │───▶│ Contextual  │    │
│  │ Filter      │    │ Analysis    │    │ Scoring     │    │
│  └─────────────┘    └─────────────┘    └─────────────┘    │
└───────────────────────┬─────────────────────────────────────┘
                        │
┌───────────────────────▼─────────────────────────────────────┐
│                 INTELLIGENCE OUTPUTS                        │
│  • active_alerts.json    (Real-time dashboard)              │
│  • vessel_dossiers/      (Forensic histories)              │
│  • investigation_ready/  (Prioritized targets)             │
└─────────────────────────────────────────────────────────────┘
\`\`\`

## Component Descriptions

### 1. Data Ingestion Layer
- **GFW AIS Archive**: Historical and real-time vessel positions
- **Equasis Registry**: Vessel metadata (age, flag, ownership)
- **Port Databases**: Geographic boundaries for false-positive filtering

### 2. Processing Pipeline
- **Stage 1 - Static Filtering**: Identifies vessels with shadow fleet characteristics
- **Stage 2 - Behavioral Analysis**: Detects AIS gaps and suspicious movements
- **Stage 3 - Contextual Scoring**: Applies geographic and historical risk weighting

### 3. Output Layer
- **JSON APIs**: Machine-readable alerts and vessel data
- **Web Dashboard**: Interactive map and investigation interface
- **Export Formats**: CSV, GeoJSON for integration with other tools

## Deployment Architecture

The system is containerized using Docker with two main services:

1. **Backend Analyzer**: Python-based detection algorithms
2. **Frontend Web**: FastAPI/Leaflet.js dashboard

See [Deployment Guide](./DEPLOYMENT.md) for detailed setup instructions.