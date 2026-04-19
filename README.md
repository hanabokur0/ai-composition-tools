# ai-composition-tools
# GHR — Golden Harmony Ratio Image Analyzer

GHR Analyzer v0

A measurement-oriented composition analyzer based on:

- Fixed golden-ratio geometry
- Fixed weighting structure
- Fixed judgment bands
- Auto-estimated FR (with human override)

Output:
Priority / Normal / Hold
(compatible with CAG / IAD workflows)

---

## What is GHR

GHR is a structural measurement tool that evaluates image composition against golden ratio harmony.

It does not judge aesthetics.
It measures structural fit.

---

## Core Concept

Every composition has a measurable distance from golden ratio equilibrium.
GHR quantifies that distance across four independent axes.

```
Score = weighted Gaussian fit across 4 parameters
      → single harmony index (0–100)
```

---

## Four Parameters

| Parameter | What it measures | Optimal |
|-----------|-----------------|---------|
| **FR** (Focal Ratio) | Area occupied by primary subject | 35% |
| **SC** (Sub-element Count) | Number of secondary compositional elements | 5 |
| **NSR** (Negative Space Ratio) | Proportion of breathing room | 25% |
| **DL** (Depth Layers) | Number of perceptual depth planes | 3.5 |

Each parameter is evaluated by Gaussian fit against its optimal value.
Deviation is continuous, not binary.

---

## Scoring

```
GHR = 0.40·FR_fit + 0.25·SC_fit + 0.20·NSR_fit + 0.15·DL_fit

where fit(x) = exp(-(x - optimal)² / 2σ²)
```

| Score | Grade |
|-------|-------|
| 80+ | 優秀 — strong golden ratio alignment |
| 60–79 | 良好 — adjustable toward harmony |
| 40–59 | 要改善 — primary composition issues |
| <40 | 不安定 — far from golden ratio structure |

---

## Features

- Upload image → overlay 38.2% / 61.8% golden grid
- Fibonacci spiral hint overlay
- Selectable focus corner (NW / NE / SW / SE)
- Manual parameter adjustment with real-time scoring
- Improvement suggestions derived from parameter deviation
- Export annotated PNG

---

## Why Manual Input

GHR does not automate parameter estimation.

The observer determines FR, SC, NSR, DL by visual judgment.
This is intentional:

- Automated estimation introduces model-dependent bias
- Manual observation trains compositional awareness
- The tool measures structure, not pixels

Future extension may add optional automated estimation (segmentation / saliency detection) as a secondary input — not a replacement.

---

## Structural Analogy

The four parameters generalize beyond image composition:

| GHR Parameter | Prompt/Protocol Equivalent |
|---------------|---------------------------|
| FR (Focal Ratio) | Subject占有率 — how much of the instruction is the core task |
| SC (Sub-element Count) | 補助情報数 — number of supporting constraints |
| NSR (Negative Space Ratio) | 未指定領域 — room left for executor discretion |
| DL (Depth Layers) | 意味の階層数 — levels of abstraction in the instruction |

A prompt with FR=90%, SC=15, NSR=0%, DL=6 will collapse for the same structural reason an image with those values does: overloaded, no breathing room, too many layers.

---

## Position in LoPAS Architecture

```
Layer 0  Data / Observation
Layer 1  DoQ / CCI / TRS / SCI / BCDI
Layer 2  CHD / CGM / HGD
         GHR  ← THIS TOOL (observation aid)
Layer 3  LCA
Layer 4  Protocol Refinement / Intervention
```

GHR is an observation tool, not a protocol.
It sits alongside Layer 1–2 as a structural measurement instrument.

---

## Files

```
README.md          — this file
index.jsx          — React component (standalone)
```

---

## Compatibility

- LoPAS-SEED v1.15+
- Standalone use (no LoPAS dependency required)

---

## Author

花黒子 (Hanabokur0)
Part of the LoPAS Civilization OS initiative.

## License

MIT
