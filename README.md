# Smart Well Log Visualizer
### AI-Assisted Reservoir Screening Tool

A browser-based petrophysical well log interpretation tool that visualizes GR, RHOB, and NPHI logs, applies industry-standard classification rules to detect reservoir intervals, and generates automated engineering insights for early-stage reservoir screening.

> **No installation required.** Open `index.html` in any modern browser.

---

## Live Demo

Upload the included `sample_well_log.csv`, or click **"Load sample data"** in the toolbar to see the tool in action immediately.

---

## Features

### Core Petrophysics
- **Multi-track log visualization** — Gamma Ray (GR), Bulk Density (RHOB), Neutron Porosity (NPHI), and Zone track rendered on synchronized depth axes
- **Rule-based classification** — Five petrophysical rules classify each depth sample into Reservoir, Clean Sand, Shale, or Transition zones
- **Adjustable cutoff thresholds** — GR, NPHI, and RHOB cutoffs are fully adjustable; re-run screening instantly
- **Estimated porosity** — Neutron porosity-derived porosity estimate displayed per depth point and per zone

### Interpretation & Reporting
- **Confidence score** — Composite 0–100% score based on zone count, GR quality, and reservoir percentage
- **Priority target highlight** — Automatically identifies the best reservoir candidate interval
- **Petrophysical assessment** — Auto-generated narrative explaining log character and formation quality
- **Lithology interpretation** — Shale/sand ratio analysis with porosity classification
- **Engineering recommendation** — Actionable next steps (DST, resistivity logging, core sampling)

### Export
- **Download .txt report** — Full interpretation report including all statistics, zone table, and narrative assessments
- **Export zones CSV** — Annotated CSV with Zone and estimated porosity columns added

### Visualizations
- GR histogram (API distribution)
- RHOB vs. NPHI crossplot (reservoir vs. non-reservoir)
- Zone composition doughnut chart

---

## Classification Logic

| Rule | Condition | Classification |
|------|-----------|----------------|
| 1 | GR < 60 API | Clean Sand |
| 2 | GR > 80 API | Shale |
| 3 | NPHI 0.12–0.30 | Porous Zone |
| 4 | RHOB 2.1–2.5 g/cc | Reservoir Quality |
| **5 (Combined)** | **GR < 60 + NPHI ∈ [0.12,0.30] + RHOB ∈ [2.1,2.5]** | **Reservoir Candidate** |

All cutoffs are user-adjustable in the dashboard.

---

## Input Format

Upload a CSV file with the following columns (column names are case-sensitive):

```csv
Depth,GR,RHOB,NPHI
1000,82,2.62,0.08
1001,78,2.58,0.09
...
```

| Column | Unit | Description |
|--------|------|-------------|
| `Depth` | m (MD) | Measured depth |
| `GR` | API units | Gamma Ray log |
| `RHOB` | g/cc | Bulk Density log |
| `NPHI` | fraction | Neutron Porosity log |

A sample dataset (`sample_well_log.csv`) is included in this repository.

---

## Applicability

- Sandstone reservoir screening
- Early-stage exploration log evaluation
- Educational petrophysics demonstrations
- Quick-look reservoir identification prior to full petrophysical study

> **Disclaimer:** All automated interpretations are screening-level outputs intended to guide, not replace, evaluation by a qualified petrophysicist or petroleum engineer.

---

## Tech Stack

| Component | Technology |
|-----------|------------|
| UI & Logic | Vanilla HTML/CSS/JavaScript |
| Charts | Chart.js 4.4.1 (CDN) |
| Fonts | IBM Plex Mono & Sans (Google Fonts) |
| Data | CSV file upload or drag-and-drop |
| Dependencies | None (no build step, no framework) |

---

## Files

```
well-log-visualizer/
├── index.html             # Main application (single file, self-contained)
├── sample_well_log.csv    # Sample dataset for testing
└── README.md              # This file
```

---

## Usage

1. Clone or download this repository
2. Open `index.html` in your browser
3. Upload a CSV log file or click **"Load sample data"**
4. Adjust cutoff thresholds if needed and click **Apply**
5. Review the reservoir candidates, confidence score, and recommendations
6. Download the interpretation report or export the annotated CSV

---

## Academic Context

> Developed as a petrophysics engineering project demonstrating web-based well log interpretation, automated lithology classification, and reservoir screening using GR, RHOB, and NPHI log suites. Implements standard industry cutoff methodology applicable to clastic sandstone petroleum systems.

**CV / Portfolio description:**
> *Developed a browser-based well log interpretation tool that visualizes GR, RHOB, and NPHI logs, applies rule-based petrophysical classification to identify reservoir zones, estimates porosity, and generates automated engineering recommendations for early-stage sandstone reservoir screening.*

---

## License

MIT License — free to use, modify, and distribute with attribution.
