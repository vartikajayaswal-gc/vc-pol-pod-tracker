# VitaCoco POL/POD Mismatch Dashboard

An internal analytics dashboard for tracking and analysing **Tracking POL/POD Mismatch** P0 alerts raised for the VitaCoco account on GoComet.

## Overview

| Metric | Value |
|---|---|
| Total Alert Firings | 4,032 |
| Unique CRNs Affected | 568 |
| Date Range | 24 Jun 2026 10:40 IST → 25 Jun 2026 01:58 IST |
| False Positive Rate | 96.5% |
| Alerts Needing Manual Fix | 20 |

## Key Findings

- **96.5% of alerts are false positives** — caused by port alias naming gaps between GoTrack (terminal-level names) and GoShipment (city/port names)
- **20 CRNs require manual fix** — POL field is missing in GoTrack
- **Top alias pair**: Manila North Harbour ↔ Manila (178 CRNs)
- A single port alias normalization table would eliminate 548/568 alerts

## Dashboard Tabs

| Tab | Description |
|---|---|
| Overview | KPIs, hourly distribution, mismatch breakdown |
| CRN Detail | Row-level table of all 568 CRNs with sort & filter |
| Classification | Alert type breakdown and classification framework |
| Route Analysis | All 47 GoShipment POL → POD trade lanes |
| Root Cause | RCA breakdown and fix complexity |
| Port Aliases | Complete alias mapping table (22 pairs) |
| Recommendations | Prioritised action plan |

## Running Locally

```bash
npm install
npm start
```

Open [http://localhost:3000](http://localhost:3000)

## Tech Stack

- **Backend**: Node.js + Express
- **Frontend**: Vanilla HTML/CSS/JS
- **Charts**: Chart.js v4
- **Data Source**: #vitacoco-p0-alerts Slack channel (GoComet Yoda alerts)
