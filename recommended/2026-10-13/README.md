# 2026-10-13 논문 추천

> 모든 추천은 의사의 검토가 필요합니다.

- **조사 날짜:** 2026-10-13 (Asia/Seoul 기준 어제)
- **실제 검색 기간:** 1일(결과 0건) → 7일 2026-10-07 ~ 2026-10-13 (적합 논문 1건, 부족) → 30일 2026-09-14 ~ 2026-10-13
- **검색어:** `chest radiograph deep learning` (30일 창에서 `chest X-ray`로도 보완 검색; 검색 서버 속도 제한으로 일부 재조회는 실패)
- **축:** 기관 간 일반화 / 임상 활용성 / 소규모 코호트 평가 신뢰도 / 허위 상관·교란

## 코호트 요약 (집계 수준)

- 마스킹된 흉부 X선 영상 272건, 소견 라벨 포함.
- 약 53%가 "No Finding"; 나머지는 침윤, 무기폐, 결절, 흉수, 섬유화, 기흉 등 단독·복합 소견이며 롱테일 분포.
- 성별 균등, 연령 9~87세, PA가 AP보다 많음.
- 5개 기관 코드, 9개 장비, 영상 크기 다양(이질성). 환자 약 150명에 추적 검사 포함.

## 논문

### Artificial intelligence for opportunistic osteoporosis screening on chest radiographs
- 링크: https://doi.org/10.1038/s41746-026-03333-7 (npj Digital Medicine, 2026-10-08)
- **관련성:** 흉부 X선에서 골다공증을 예측하며 병원 시간 분리 코호트와 2개 건강검진 코호트에서 외부 검증(AUROC 0.88~0.93). 임상가가 활용 가능한 코호트 기반 근거.
- **우리 데이터의 근거:** 다기관·다장비 흉부 X선과 연령·성별 정보가 있어 기관 간 일반화 논의와 맞닿음.
- **한계:** 우리 데이터에는 DXA/BMD 라벨이 없어 직접 검증 불가. 소견 라벨은 폐·흉막 중심.

### Performance uncertainty in medical image analysis: a large-scale investigation of confidence intervals
- 링크: https://doi.org/10.1016/j.media.2026.104349 (Medical Image Analysis, 2026-10-01)
- **관련성:** 성능 지표 신뢰구간의 신뢰성을 대규모로 조사한 연구.
- **우리 데이터의 근거:** 272건 중 희귀 소견은 1~7건에 불과해 점추정만으로는 해석이 위험함.
- **한계:** 초록이 제공되지 않아 `abstract`를 비웠고 제목·메타데이터만으로 판단함. 결과는 원문 확인 필요. 임상 코호트 연구가 아닌 방법론 논문.

### Beyond Explanation: Debugging Medical Imaging Models via Concept Intervention
- 링크: http://arxiv.org/abs/2610.09031v1 (MICCAI, 2026-10-06)
- **관련성:** 개념 병목 모델로 인과적 개념과 허위 상관을 구분하고 CheXpert 5x200에서 검증.
- **우리 데이터의 근거:** AP/PA, 기관·장비 차이가 허위 상관의 잠재 원천.
- **한계:** 방법론 중심, 판독자 연구·전향 검증 없음. 우리 데이터에서의 효과는 알 수 없음.

## 비고

환자 수준 값은 기록하지 않았으며, 모든 추천은 의사의 검토가 필요합니다.
