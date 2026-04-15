# Image Placeholders

Replace each placeholder `<div class="placeholder">` in `index.qmd` with an `<img>` tag
pointing to the file listed below once you generate the images.

---

## 1. `teaser.png` — Hero Teaser Figure
**Used in:** Hero section (top of page)
**Suggested size:** 1640 × 720px (2× for retina)
**Description:**
Split-screen comparison diagram:
- LEFT: A large heavy block labeled "PRM" (e.g. 7B params), shown as a thick solid box in gray/red.
- RIGHT: A tiny glowing chip/probe labeled "ReProbe (<10M params)" attached to the side of an LLM diagram.
- CENTER: A frozen LLM block (hexagonal or rectangular) with "signals" (thin colored lines) flowing OUT of it into the ReProbe chip.
- Below: two arrows — "Best-of-N" and "Beam Search" — pointing toward a checkmark "Best Answer".
- Style: dark background (#0f0c29), purple/violet accent lines, clean technical illustration.

---

## 2. `architecture.png` — ReProbe Architecture Diagram
**Used in:** Method section (architecture diagram)
**Suggested size:** 1400 × 600px
**Description:**
Left-to-right data flow:
1. "Frozen LLM" box → emits 3 streams labeled "Hidden States", "Attention Weights", "Logits"
2. All 3 streams merge → "Linear Projection" layer
3. → "Transformer Encoder (L layers)"
4. → "Token Aggregation" (per-step pooling)
5. → "Classification Head (2-layer MLP)"
6. → Output: "P(step correct)" as a probability bar [0, 1]
Key annotation: "≤10M trainable parameters" badge floating above the probe architecture.
Style: white background, purple (#6C63FF) accent, clean flat technical illustration.

---

## 3. `bon_curves.png` — Best-of-N Scaling Curves
**Used in:** Results section (Best-of-N chart)
**Suggested size:** 1200 × 480px
**Description:**
Two-panel line chart (side by side):
- Panel A: GSM8K (Math, In-Domain) — x-axis: N=1..10, y-axis: accuracy 0→1
- Panel B: ScienceQA (OOD) — same axes
Lines per panel:
  - ReProbe (bold purple, filled markers)
  - Best PRM (dashed gray)
  - Majority Vote (dash-dot orange)
  - Random (dotted light gray)
ReProbe should clearly diverge upward from others, especially at N≥4.
Style: clean academic plot, no clutter, Inter font labels.

---

## 4. `generalization.png` — OOD Generalization Chart
**Used in:** Generalization section
**Suggested size:** 900 × 600px
**Description:**
Radar/spider chart OR grouped bar chart:
- 3 axes / groups: Mathematics, Planning, QA
- 2 series: ReProbe (purple) vs. Best PRM (gray)
ReProbe shows balanced coverage; PRM is high on Math but drops on Planning/QA.
Include annotation: "OOD" arrow pointing at Planning & QA axes.

---

## 5. `favicon.png`
**Suggested size:** 64 × 64px
**Description:**
A minimalist icon: stylized probe/signal symbol — e.g. a small waveform or
oscilloscope trace inside a rounded square, in purple (#6C63FF) on dark background.

---

## How to replace placeholders

In `index.qmd`, find the `<div class="placeholder">` block you want to replace and
swap it with:
```html
<img src="images/teaser.png" alt="ReProbe teaser figure" style="width:100%;display:block;">
```
