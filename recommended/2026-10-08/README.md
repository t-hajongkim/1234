# 2026-10-08 논문 추천

> 모든 추천은 의사의 검토가 필요합니다.

- **조사 날짜:** 2026-10-08 (Asia/Seoul 기준 어제)
- **실제 검색 기간:** 1일(결과 0건) → 7일(결과 0건) → 30일, 2026-09-09 ~ 2026-10-08 (관련 논문 4건)
- **검색어:** `chest X-ray` (30일 창; 1일·7일 창은 `chest radiograph deep learning`)

## 코호트 요약 (집계 수준)

- 마스킹된 흉부 X선 영상 272건, 소견 라벨 포함.
- 약 53%가 "No Finding"; 나머지는 침윤, 무기폐, 결절, 흉수, 섬유화, 기흉 등 단독·복합 소견이며 다수 소견은 소수 건에 불과한 롱테일 분포.
- 성별은 거의 균등, 연령은 소아·청소년부터 80대까지, PA 촬영이 AP보다 많음.
- 5개 기관 코드, 영상 크기가 다양함(기관/장비 이질성). 추적 검사가 있는 환자 포함.

## 논문

### An open vision-language model for diverse medical applications (MedGemma)
- 링크: https://doi.org/10.1038/s41591-026-04626-w (Nature Medicine, 2026-10-06)
- **관련성:** 흉부 X선 소견 분류에서 기본 모델 대비 15.5–18.1% 향상, 소량 데이터 미세조정에 유리하다고 보고.
- **우리 데이터의 근거:** 272건의 소규모 라벨 데이터는 데이터 효율적 미세조정이 필요한 상황에 해당.
- **한계:** 모델 개발·벤치마크 중심이며 환자 코호트 전향 검증이나 판독자 연구가 아님. 우리 데이터에서의 성능은 알 수 없음.

### Learning to Defer with Guidance on Real World Medical Data
- 링크: http://arxiv.org/abs/2609.26384v1 (MICCAI, 2026-09-22)
- **관련성:** 다수 판독자 주석이 있는 실제 흉부 X선(Collab-CXR, VinDr-CXR, CheXpert)에서 AI 단독·의사 단독·AI 보조 대비 우수한 위임 전략을 보고. 임상 워크플로 관점에서 가장 실용적.
- **우리 데이터의 근거:** 흉부 X선 판독 업무로, 위임(defer) 정책 설계의 대상이 될 수 있음.
- **한계:** 우리 데이터는 판독자별 다중 주석이 없어 직접 재현 불가. 전향적 임상 검증은 아님.

### Anatomy-Structured Hierarchical MIL for Weakly-Supervised Thoracic Disease Detection in Chest X-rays
- 링크: http://arxiv.org/abs/2609.33520v1 (MICCAI, 2026-09-27)
- **관련성:** CXR8과 MIMIC-CXR 교차 도메인에서 박스 주석 없이 병변 위치를 제시.
- **우리 데이터의 근거:** 영상 수준 소견 라벨만 있고 위치 주석이 없는 구성과 부합하며, 라벨 체계가 CXR8 계열과 유사.
- **한계:** 방법론 논문으로 임상 판독자 평가 없음. 소규모·희귀 소견에서의 국소화 신뢰도는 불명.

### CXR-LT 2026 challenge: Multi-center long-tailed and zero shot chest X-ray classification
- 링크: https://doi.org/10.1016/j.media.2026.104340 (Medical Image Analysis, 2026-09-24)
- **관련성:** 다기관 롱테일 및 제로샷 흉부 X선 분류 챌린지.
- **우리 데이터의 근거:** 결절·기흉·탈장·종괴 등 희귀 소견이 극소수인 롱테일 분포와 5개 기관 이질성.
- **한계:** 초록이 제공되지 않아 `abstract`를 비워 두었고 제목·메타데이터만으로 판단함. 결과 내용은 원문 확인 필요.

## 비고

제외: MICCAI 개념 개입 디버깅(초음파·CheXpert 5x200, 임상 근거 약함), GLR-MM(ICU 사망 예측·EHR 결합, 데이터에 EHR 없음), 이미 추천된 논문(흉부 X선 파운데이션 모델 의사 참여, On-premise 의료 AI 에이전트 등), 비흉부·비영상 주제.
