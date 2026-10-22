# 2026-10-21 논문 추천

> 모든 추천은 의사의 검토가 필요합니다.

- 연구 날짜: 2026-10-21 (Asia/Seoul 기준 어제)
- 실제 검색 기간: 2026-09-22 ~ 2026-10-21 (1일 → 7일 → 30일로 확대)
- 검색어: `chest radiograph deep learning` (보조 확인: `chest x-ray`, `radiograph AI reader study`)

## 코호트 요약 (집계 수치만)

마스킹된 `llm.hospital` 뷰, 272개 영상. 흉부 X선(PA/AP)이며 5개 기관에서 수집되었다. 남녀가 모두 포함되고 성인 위주이나 소아·고령도 일부 있다. 라벨은 Atelectasis, Effusion, Infiltration, Cardiomegaly 등 다중 소견이며 복수 소견이 흔하다. 추적 검사 번호가 있어 동일 환자의 반복 촬영이 포함된다.

## 선정 결과

1일, 7일, 30일 창에서 중복 제외 후 임상적으로 관련 있는 논문은 1편뿐이었다. 기준을 낮추지 않았으므로 목표인 3편에 못 미친다. 이미 추천된 논문(신생아 CXR 지속학습, 흉부 X선 골다공증 선별 등)은 제외했다.

### 1. Expertise modulates automation bias and sentinel behavior in human–AI collaborative diagnosis of neonatal pneumoperitoneum
- 축: 의사-AI 협업, 자동화 편향
- 링크: https://doi.org/10.1038/s41746-026-03399-3 (npj Digital Medicine, 2026-10-20)
- 관련성: 방사선 사진 판독에서 AI 보조 효과가 판독자 숙련도에 따라 달라짐을 다독자 교차 연구(1750건 판독)로 보였다. 임상의가 실제로 참고할 수 있는 판독자 연구이다.
- 우리 데이터의 근거: 다중 소견 흉부 X선이 있어 AI 보조 판독 평가를 설계할 수 있다.
- 한계: 대상이 신생아 복강 내 공기(pneumoperitoneum)로 성인 흉부 소견과 질환·연령이 다르다. 전문의가 3명뿐이라 저자들도 가설 생성 수준이라 밝혔다. 우리 데이터로 자동화 편향을 검증할 수는 없다.

## 제외한 항목

방법론 위주이거나 흉부 X선 소견과 무관한 논문(적대적 공격 탐지, 연합학습 프라이버시, 척추 라벨링, 의학교육 리뷰 등)은 임상 판독 결과가 없거나 데이터와 맞지 않아 제외했다.
