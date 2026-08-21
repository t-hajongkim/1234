# Daily paper recommendations — 2026-08-20

**Research date:** 2026-08-20 (yesterday in Asia/Seoul).

**Search window used:** 2026-07-21 to 2026-08-20 (30 days). The same-day window
(2026-08-20) and the 7-day window (2026-08-14–2026-08-20) both returned zero
results, so the search was widened per the escalation rule until at least
three clinically relevant papers were found.

**Search queries used:**
- `chest X-ray multi-institution deep learning diagnosis` (same-day and 7-day windows, 0 hits)
- `chest X-ray multi-institution deep learning diagnosis` (30-day window)
- `thoracic imaging AI generalization external validation` (30-day window, supplementary)

## Cohort summary (masked, aggregate only)

The `llm.hospital` view contains 272 chest radiograph studies (all flagged
`is_synthetic = true`) drawn from 5 institutions (INST01–INST05, 48–62 studies
each). Sex is balanced (136 M / 136 F), mean age ~48.7 (M) / ~54.3 (F). Views
are PA-dominant (184 PA vs. 88 AP). Findings labels are multi-label and
long-tailed: "No Finding" (145), Infiltration (21), Atelectasis (16), Nodule
(7), Fibrosis (6), Effusion (6), Cardiomegaly (5), Pneumothorax (5), plus many
low-frequency co-occurring combinations (e.g., Effusion+Infiltration,
Atelectasis+Infiltration). This mirrors a small, multi-site, multi-label CXR
screening cohort with an imbalanced, long-tailed disease distribution.

## Retained papers

### 1. AbdomenNet — foundation model for acute abdomen triage on NCCT (Nature Communications)
**Why relevant:** Demonstrates the full pipeline our cohort's structure calls
for — a foundation model fine-tuned on a modest annotated set, then validated
across independent external institutional cohorts with a reader study
measuring real diagnostic and workflow impact.
**Support from our data:** Our cohort's multi-institution design (5 sites)
directly parallels AbdomenNet's external multi-cohort validation, and its
reader-study framework (AI-assisted vs. unassisted radiologists) is a template
for evaluating AI support on our imbalanced, multi-label CXR findings.
**Limitations:** Different modality (NCCT vs. CXR) and organ system (abdomen
vs. thorax); cannot be directly transferred without re-validation on chest
radiographs.

### 2. Multicenter evaluation of four LLMs for spine imaging diagnosis (npj Digital Medicine)
**Why relevant:** A multicentre, cross-institutional generalizability study
with an explicit finding that model precision degrades sharply for
low-prevalence conditions — precisely the long-tailed finding distribution
present in our cohort (most labels have single-digit counts).
**Support from our data:** Our findings distribution is long-tailed
(Nodule=7, Fibrosis=6, Cardiomegaly=5, Pneumothorax=5, and many combinations
with n≤2), so the paper's warning about long-tail precision loss and the need
for prevalence-aware deployment is directly actionable for any model trained
on this cohort.
**Limitations:** Studies text-based LLM report analysis on spine imaging, not
image-based CXR classification; institution count and modality differ from
ours.

### 3. UniMedDiff — knowledge-enhanced diffusion model for CXR generation from reports (npj Digital Medicine)
**Why relevant:** Directly targets chest X-ray data scarcity and multi-label
pathology imbalance via report-guided synthetic image generation, explicitly
evaluated on 11 pulmonary pathologies and shown to boost downstream
classification with minimal real data.
**Support from our data:** Our cohort is small (272 studies) with several
findings represented by only 1–7 cases; UniMedDiff's demonstrated ability to
augment low-prevalence pathology classes with synthetic CXRs is a plausible
mitigation for this scarcity.
**Limitations:** Generation quality and downstream utility were validated on
the authors' own multi-source datasets, not on our specific cohort or
institutions; synthetic augmentation still requires local validation before
any clinical use.

## Axes

- **기관 간 일반화** (cross-institutional generalization): AbdomenNet, spine LLM paper
- **저빈도 소견 성능** (low-prevalence finding performance): spine LLM paper
- **판독 보조 효과** (reader-assistance impact): AbdomenNet
- **다중 소견 라벨링 / 데이터 증강** (multi-label / data augmentation): UniMedDiff

## Note

These are automated literature suggestions based on masked, cohort-level
aggregates. They require review and clinical judgment by a physician before
any action is taken; no patient-level data was used or disclosed in this
process.
