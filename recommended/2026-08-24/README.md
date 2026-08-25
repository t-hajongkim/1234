# Daily paper recommendations — 2026-08-24

## Research date and search window

- **Requested research date:** 2026-08-24 (no valid `REQUESTED_DATE` was supplied,
  so yesterday's date in Asia/Seoul was used).
- **Search windows tried:** 2026-08-24–2026-08-24 (0 results) →
  2026-08-18–2026-08-24 (1 result) → **2026-07-25–2026-08-24 (final window used,
  10 deduplicated results)**.
- **Search query:** `chest X-ray multi-label classification deep learning`

## Cohort snapshot (aggregate only)

The masked `llm.hospital` view contains **272 chest X-ray studies** from a
roughly balanced cohort (136 male, mean age ≈48.7; 136 female, mean age
≈54.3). Frontal projections are split between PA (184) and AP (88). The
`findings_label` field carries single and multi-label thoracic findings; the
most frequent categories are "No Finding" (145), Infiltration (21),
Atelectasis (16), Nodule (7), Fibrosis (6), Effusion (6), Cardiomegaly (5),
Pneumothorax (5), and several co-occurring multi-label combinations (e.g.
Effusion+Infiltration, Atelectasis+Infiltration), reflecting a long-tailed,
multi-label classification setting typical of chest radiograph screening
datasets. No patient-level values are reported here.

## Retained papers

### 1. RayDINO — Advancing human-centric AI for robust X-ray analysis through holistic self-supervised learning (*Nature Communications*)

**Why relevant:** RayDINO is a large-scale self-supervised visual encoder for
chest X-rays, validated across 82,000 images from 12 public datasets and nine
radiology tasks including multi-label classification, with an explicit
analysis of population, age, and sex bias.

**What our data supports:** Our cohort's balanced sex split and modest age
spread, together with a long-tailed multi-label finding distribution and mixed
AP/PA acquisition, is exactly the kind of population-heterogeneity setting
this paper's bias analysis addresses — a clinician could use RayDINO-style
adapters to check whether a local classifier's performance drifts across our
age/sex subgroups.

**What it cannot tell us:** The paper's bias findings come from its own
external cohorts; it does not certify performance on our specific
institution's scanners, reporting conventions, or disease prevalence, and
would need local validation before clinical use.

### 2. UniMedDiff — a knowledge-enhanced diffusion model for medical image generation from clinical reports (*npj Digital Medicine*)

**Why relevant:** UniMedDiff generates synthetic chest X-rays for 11 pulmonary
pathologies from clinical reports and shows near full-data classification
performance when augmenting with only 1% real data — directly relevant to
rare/tail findings.

**What our data supports:** Many findings in our cohort (Nodule, Fibrosis,
Pleural_Thickening, multi-label combinations) each have single-digit case
counts. A report-conditioned augmentation approach like UniMedDiff is
plausible support for improving classifier robustness on these low-prevalence
labels without needing to collect many more real cases.

**What it cannot tell us:** The reported gains are from the authors' own
datasets and pathology vocabulary; it does not establish that synthetic
augmentation preserves diagnostic fidelity for our specific label taxonomy or
that a model trained partly on synthetic images would pass local clinical
review.

### 3. CF2Seg — Grounding Radiology Report Findings into Medical Image Segmentation (*npj Digital Medicine*)

**Why relevant:** CF2Seg converts free-text radiology findings into spatial
segmentation masks across a 53,386-exam multi-institution benchmark spanning
diverse thoracic pathologies, remaining stable under distribution shift and
annotation scarcity.

**What our data supports:** Our `report_text`/`clinical_info` and
`findings_label` fields are narrative/label-based rather than pixel-annotated,
matching the exact gap (reports without spatial annotations) this paper
targets; it suggests a path to deriving lesion-location evidence from our
existing report text for findings such as Infiltration, Effusion, and
Atelectasis without new manual annotation.

**What it cannot tell us:** Segmentation quality was validated on the
authors' benchmark institutions, not ours; report style, vocabulary, and
image acquisition differences at our site could affect grounding accuracy,
and any lesion-burden trends would still require expert radiologist
verification.

## Axes

- **기관 간 일반화** (cross-institution generalization): RayDINO, CF2Seg
- **인구통계학적 편향** (demographic bias): RayDINO
- **소수 소견 데이터 증강** (augmentation for rare findings): UniMedDiff
- **라벨 잡음** (label/annotation noise and scarcity): UniMedDiff, CF2Seg

## Sources

- https://doi.org/10.1038/s41467-026-76076-4
- https://doi.org/10.1038/s41746-026-03135-x
- https://doi.org/10.1038/s41746-026-03051-0

**These recommendations are automatically generated and require physician
review before any clinical or research use.**
