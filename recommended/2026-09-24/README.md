# Daily paper recommendations — 2026-09-24

## 검색 개요

- **연구 기준일**: 2026-09-24 (요청된 `REQUESTED_DATE` 없음 → Asia/Seoul 기준 어제 날짜 사용)
- **실제 검색 창**: 단일 일자(2026-09-24)와 7일 창(2026-09-17~2026-09-24)에서는 관련 논문이 검색되지 않아, 규칙에 따라 30일 창(2026-08-25~2026-09-24)까지 확대했습니다.
- **검색어**: `chest radiograph AI diagnosis` (선행 시도: `chest radiograph deep learning multi-institution diagnosis`, `chest X-ray thoracic disease classification`)
- MICCAI, CVPR, NeurIPS, IPMI, ICLR(arXiv 경유)는 이번 실행에서 지속적으로 406/429 오류를 반환해 결과에 포함되지 못했습니다. 이는 검색 인프라의 일시적 제약이며, 저널 소스(OpenAlex 경유)만으로도 최소 3편의 관련 논문을 확보했습니다.

## 코호트 요약 (환자 단위 값 없음)

- 총 272건의 흉부 X-ray 스터디(전량 합성/`is_synthetic = true` 데이터셋)
- 성별 분포: 남성 136건, 여성 136건
- 연령: 평균 약 48.7세(남) / 54.3세(여), 범위 9–87세
- 촬영 자세: PA 184건, AP 88건
- 소견 라벨: "No Finding" 145건, 이어서 Infiltration(21), Atelectasis(16), Nodule(7), Effusion(6), Fibrosis(6), Pneumothorax(5) 등 다양한 조합 라벨 존재
- 5개 기관 코드(INST01–INST05)에 걸쳐 48–62건씩 비교적 고르게 분포 — 다기관 일반화 검증에 적합한 구조
- 영상 크기는 2500×2048, 2048×2500, 2992×2991 등 여러 해상도가 혼재

## 축 (Axes)

1. **합성 영상 신뢰도** — 합성/생성 영상이 임상 판단 워크플로우에서 실제 데이터처럼 오인될 위험
2. **영상 기반 임상 판단 한계** — 영상·다중모달 추론에서 현재 AI/VLM이 보이는 성능 격차
3. **다중 질환 진단 정확도** — 여러 질환/소견을 동시에 다루는 진단 모델의 정확도와 일관성
4. **기관 내 배치 신뢰도** — 병원 내부(온프레미스) 배치 환경에서의 신뢰도·불확실성 추정

## 채택 논문

### 1. Staged purpose-blinded evaluation of provenance risk from a general-purpose generator in breast ultrasound
**축**: 합성 영상 신뢰도, 영상 기반 임상 판단 한계

- **관련성**: 본 코호트가 전량 합성 흉부 X-ray로 구성되어 있어, "합성 영상이 임상 판독자에게 실제 영상처럼 받아들여질 수 있는가"라는 질문과 직접 맞닿아 있습니다.
- **우리 데이터로 뒷받침되는 점**: 272건 전체가 `is_synthetic = true`로 표시되어 있음에도 판독 워크플로우(소견 라벨, 리포트 텍스트 등)가 실제 임상 데이터처럼 구조화되어 있어, 논문이 지적한 "사전 검증 취약성(pre-verification vulnerability)"이 동일하게 적용될 수 있습니다.
- **한계**: 유방 초음파 영상에 대한 결과이며 흉부 X-ray로의 직접 일반화는 검증되지 않았습니다. 또한 진단 정확도나 임상적 동등성을 주장하지 않는 예비 연구입니다.

### 2. On-premise medical AI agents for reliable clinical decision-making
**축**: 기관 내 배치 신뢰도, 다중 질환 진단 정확도

- **관련성**: 5개 기관에 걸쳐 분포된 본 코호트는 병원 내부(온프레미스) 배치 시나리오에 부합하며, 다중 질환 라벨(최대 4개 소견 동시 발생) 구조는 논문의 다중 질환 진단 과제와 유사합니다.
- **우리 데이터로 뒷받침되는 점**: 기관 코드별로 48–62건씩 비교적 균등하게 분포해 기관 간 신뢰도 프레임워크 검증에 활용할 수 있는 구조를 갖추고 있습니다.
- **한계**: 원 연구는 MIMIC-IV 기반 텍스트/구조화 데이터에 대한 것으로, 흉부 영상 자체에 대한 진단 신뢰도는 검증되지 않았습니다.

### 3. The illusion of clinical reasoning: a benchmark reveals the pervasive gap in vision-language models for clinical competency
**축**: 영상 기반 임상 판단 한계, 다중 질환 진단 정확도

- **관련성**: 본 데이터셋은 영상 해석과 다중 소견 판단이 결합된 과제이며, 이 논문은 정확히 그러한 "영상 해석 + 진단 생성" 결합 과제에서 VLM의 성능 저하를 보고합니다.
- **우리 데이터로 뒷받침되는 점**: 우리 코호트의 소견 라벨 다수가 단일이 아닌 복합 조합(예: Atelectasis+Infiltration, Effusion+Pneumothorax)으로 구성되어 있어, 논문이 지적한 "구조화된 선택형 문제에서는 높은 정확도, 개방형 다중모달 통합 과제에서는 급격한 성능 저하" 패턴이 실제 임상 적용 시 위험 요인이 될 수 있음을 시사합니다.
- **한계**: 원 연구는 정형외과/스포츠의학(B&J 벤치마크) 영역이며, 흉부영상 도메인에 대한 직접적 검증 결과는 아닙니다.

## 참고 및 검토 안내

- Provenance risk: https://doi.org/10.1038/s41746-026-03209-w
- On-premise agents: https://doi.org/10.1038/s41591-026-04609-x
- Illusion of clinical reasoning: https://doi.org/10.1038/s41746-026-03191-3

**본 추천 목록은 자동 생성된 초안이며, 임상 적용 전 반드시 담당 의료진의 검토와 판단이 필요합니다.**
