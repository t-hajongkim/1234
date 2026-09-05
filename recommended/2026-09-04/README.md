# Daily paper recommendations — 2026-09-04

**Research date:** 2026-09-04 (Asia/Seoul, since `REQUESTED_DATE` was not set, yesterday's date was used)

**Search windows tried:** 1 day (2026-09-04 to 2026-09-04, timed out / no usable results), 7 days
(2026-08-29 to 2026-09-04, only 1 weak methodological hit), 30 days (2026-08-06 to 2026-09-04, used
for final selection).

**Search queries used:** "chest X-ray classification" and "chest radiograph deep learning diagnosis"
(30-day window). A subsequent narrower query ("pulmonary nodule detection radiologist reader study",
"external validation deep learning imaging diagnostic accuracy") returned no results because of
upstream rate limiting (HTTP 429) on most journal sources.

## Cohort summary (masked, aggregate only)

The `llm.hospital` view holds 272 studies from 153 masked patients across 5 institutions
(INST01–INST05, roughly evenly distributed, 48–62 studies each). Patients are evenly split by sex
(136 M / 136 F), ages 9–87 (mean ≈ 51.5). Imaging is frontal chest radiography, mostly PA (184)
with some AP (88). Findings labels are dominated by "No Finding" (145), followed by Infiltration (21),
Atelectasis (16), Nodule (7), Fibrosis (6), Effusion (6), Cardiomegaly (5), Pneumothorax (5), and
various multi-label combinations (Effusion+Infiltration, Atelectasis+Infiltration, etc.) — a typical
multi-institutional, multi-label chest X-ray screening cohort.

## Retained papers

### 1. Impact of Commercial AI on Radiologist Reading Time for Pulmonary Nodule Evaluation at Chest CT (Radiology)
**Why relevant:** Reports real-world clinical impact (reduced reporting time) of a commercial
AI tool for pulmonary nodule assessment — directly actionable evidence for how AI assistance
changes radiologist workflow, relevant given our cohort includes Nodule-labeled studies.
**What our data supports:** Our cohort contains a modest number of Nodule cases (7/272), so the
paper's workflow-efficiency finding is a plausible but not directly testable extension — we lack
timing data ourselves.
**What it cannot tell us:** It is a CT (not radiograph) study and reports only reading-time impact,
not diagnostic accuracy or generalization across institutions; it does not address multi-label
chest radiograph interpretation as seen in our data.

### 2. A Multimodal LLM-based triage tool for osteoporotic vertebral compression fractures using posture/movement videos (npj Digital Medicine)
**Why relevant:** Demonstrates external validation with negligible AUC degradation across an
independent, geographically distinct cohort — a strong methodological template for evaluating
whether AI tools generalize across institutions, directly applicable to our 5-institution cohort.
**What our data supports:** Our multi-institution structure (5 sites, uneven case mix) offers a
similar external-validation opportunity for future chest X-ray classifiers trained on our data.
**What it cannot tell us:** The clinical target (vertebral fracture triage from video) and modality
(posture/video, not radiography) are unrelated to our chest X-ray findings; results cannot be
directly transferred to our diagnostic labels.

### 3. Automatic extraction of structured information from brain MRI reports using an open-weight LLM (European Radiology)
**Why relevant:** Shows an open-weight LLM can reliably structure free-text radiology reports
across variables with high balanced accuracy — relevant because our dataset includes free-text
`report_text`/`clinical_info` fields that could similarly benefit from automated structuring for
research use.
**What our data supports:** Our cohort's mixed structured labels and free-text fields parallel the
"free text vs structured variable" gap the paper addresses, though for a different anatomic region.
**What it cannot tell us:** The paper evaluates Dutch neuroradiology (brain MRI) reports, not chest
radiograph reports; extraction accuracy may not transfer to different reporting styles or
pathologies represented in our cohort.

## Notes for the reviewing physician

- These are automatically retrieved candidates; **all recommendations require physician review**
  before any clinical or research action.
- Duplicate papers already present under `recommended/2026-08-20/` (spine imaging LLM, AbdomenNet)
  and `recommended/2026-08-24/` (RayDINO) were excluded from this round.
- Source links: see each paper's `paper.json` `url` field (DOI links).
