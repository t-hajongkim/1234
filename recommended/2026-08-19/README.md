# Daily paper recommendations — 2026-08-19

**Research date:** 2026-08-19 (from `REQUESTED_DATE`)
**Actual search window used:** 2026-07-21 to 2026-08-19 (30-day window; the same-day and 7-day windows returned no results)
**Search query:** `chest X-ray deep learning multi-institution generalization`

## Cohort context (aggregate only)

The masked `llm.hospital` view contains 272 chest radiograph studies, roughly
balanced by sex (136 M / 136 F, mean age ~49–54) and imaging view (PA 184 /
AP 88). Studies are drawn from 5 institutions (48–62 studies each) and 9
imaging devices (15–40 studies each), spanning acquisition dates from 2010 to
2021. Findings are dominated by "No Finding" (145), with the remainder
covering infiltration, atelectasis, nodule, fibrosis, effusion, cardiomegaly,
pneumothorax, emphysema, pleural thickening and several multi-label
combinations. This is a small, multi-site, multi-device, multi-pathology
chest X-ray cohort — well suited to evaluating cross-institution
generalization and robustness of chest-X-ray AI systems, not to training or
validating single-center classifiers.

## Retained papers

### 1. CLEAR: an auditable foundation model for radiology grounded in clinical concepts (Nature Biomedical Engineering)
**Relevance:** CLEAR is a chest X-ray foundation model externally validated on
four large, physician-annotated datasets spanning the US, Europe, and Asia —
directly analogous to the multi-institution, multi-device structure of our
cohort. Its concept-bottleneck design also targets exactly the
"black-box distrust" problem relevant to a small, heterogeneous local
dataset.
**Supported by our data:** Our 5-institution, 9-device, multi-pathology
cohort is a natural candidate for testing whether such externally validated,
auditable models transfer to a new site without local fine-tuning.
**What it cannot tell us:** It cannot establish that CLEAR's concept
attributions remain calibrated on our specific label set (many of our
findings are multi-label combinations not explicitly enumerated in the
paper), nor does it confirm performance for the AP-view subset, which is
under-represented in typical training data.

### 2. QoQ-Med3: a multimodal reasoning foundation model for clinical analysis (npj Digital Medicine)
**Relevance:** The paper explicitly evaluates transferability across
held-out datasets from different clinical sites and robustness to cross-site
heterogeneity — the core methodological concern for our 5-institution,
9-device cohort with visible imbalance in device representation (15–40
studies per device).
**Supported by our data:** Our dataset's device/institution heterogeneity
provides a realistic scenario for testing the claimed robustness to
cross-site variation, and our modest sample size (272) mirrors the
"held-out external site" evaluation setting the authors used.
**What it cannot tell us:** The reported balanced accuracy (71.3%) is a
population-level, multi-modality figure; it does not indicate expected
performance on our specific findings distribution, which is dominated by
"No Finding" and long-tail low-prevalence labels (e.g., single-digit counts
for nodule, fibrosis, pneumothorax).

### 3. Grounding Radiology Report Findings into Medical Image Segmentation — CF2Seg (npj Digital Medicine)
**Relevance:** CF2Seg links free-text radiology findings to spatial
segmentation across a 53,386-study, multi-institution, multi-pathology
benchmark, and reports stability under distribution shift and annotation
scarcity — both directly applicable given our small (272-study), unevenly
distributed cohort.
**Supported by our data:** Our dataset pairs `findings_label` with imaging
studies but has no pixel-level annotations, making a report-grounded
segmentation approach potentially useful for retrospective spatial analysis
without new manual annotation effort.
**What it cannot tell us:** Their benchmark diagnoses differ in label
granularity from ours; the paper does not demonstrate performance under our
exact combination of low case counts (e.g., 3–7 cases for several findings)
and cannot guarantee segmentation quality on such small per-label samples.

## Axes

- **기관 간 일반화** (cross-institution generalization): how each method's
  external, multi-site validation relates to our 5-institution, 9-device
  cohort.
- **다기관 검증 / 이질적 데이터 강건성** (multi-site validation and
  robustness to heterogeneous data): explicit cross-site robustness testing,
  relevant given our device/site imbalance.
- **텍스트-영상 정합** (text–image grounding): using free-text findings to
  derive spatial or conceptual structure, relevant since our data has
  findings labels but no pixel annotations.
- **설명가능성** (explainability): concept-level auditability, relevant for
  clinical trust in a small, heterogeneous cohort.

## Review note

These are automated literature suggestions generated from OpenAlex search
results and dataset-derived heuristics. **They require physician review**
before being used to guide any clinical, research, or deployment decision.
No patient-level data was included in this analysis; all figures above are
cohort-level aggregates from the masked `llm.hospital` view.
