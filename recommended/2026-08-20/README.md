# Daily paper recommendations — 2026-08-20

## 검색 정보

- **연구 기준일**: 2026-08-20 (Asia/Seoul 기준 어제 날짜, `REQUESTED_DATE` 미지정)
- **실제 검색 창**: 2026-07-22 ~ 2026-08-20 (당일 및 7일 창에서 결과 없음, 30일 창으로 확대)
- **검색 쿼리**: `chest radiograph deep learning multi-institution diagnosis`

## 코호트 요약 (환자 단위 값 제외)

- 총 272건의 흉부 X-ray 판독 레코드
- 성별: 남성 136 / 여성 136, 평균 연령 남 48.7세 / 여 54.3세
- 촬영 자세: PA 184건, AP 88건
- 소견 라벨(다중 라벨 가능): No Finding 145건, Infiltration 21건, Atelectasis 16건, Nodule 7건, Fibrosis 6건, Effusion 6건, Cardiomegaly 5건, Pneumothorax 5건, 그 외 복합 라벨(Effusion+Infiltration, Atelectasis+Infiltration 등) 다수
- 5개 기관(INST01–05)에서 48–62건씩 분포, 판독 상태는 preliminary/final/amended/addendum이 고르게 섞여 있음
- 전체 레코드는 합성(is_synthetic=true) 데이터

## 선정 근거

당일·7일 창에서는 관련 논문이 없어 30일 창으로 확대했고, 그중 방법론만 있는 순수 알고리즘 논문(예: 리뷰형 파운데이션 모델 개관, 인과 그래프 신경망)은 제외하고 **환자 코호트 기반 검증 또는 다기관 평가가 있는 임상 실행 가능성 높은 논문 3편**을 선정했다.

### 1. Grounding Radiology Report Findings into Medical Image Segmentation (CF2Seg)
자유텍스트 판독 소견만으로 병변을 픽셀 단위 분할하는 프레임워크로, 53,386건의 다기관 벤치마크에서 검증되었다. 우리 코호트는 report_text와 findings_label이 함께 존재하고 5개 기관에 걸쳐 분포되어 있어 이 접근을 적용해볼 토대가 된다. 다만 우리 데이터에는 픽셀 단위 전문가 주석이 없어 분할 정확도를 직접 검증할 수는 없다.

### 2. CLEAR: an auditable foundation model for radiology grounded in clinical concepts
0.87M 규모의 이미지-보고서 쌍으로 학습한 개념 기반 임베딩 모델이 4개 대륙 외부 데이터셋에서 검증되었으며, 예측을 소견 단위로 분해해 감사 가능하게 한다. 우리 코호트의 다소견 복합 라벨(Effusion+Infiltration 등) 해석에 유용할 수 있으나, 규모 차이(수십만 vs 272건)로 동일 성능 재현 여부는 확인 불가.

### 3. Multicenter evaluation of four large language models for automated spine imaging diagnosis
3개 기관, 20,277건의 실제 판독 보고서로 4개 LLM을 비교한 결과, 전반적 성능은 높았으나 저빈도 소견에서 정밀도가 19–42%p 하락하는 롱테일 문제를 확인했다. 우리 코호트도 No Finding이 53%를 차지하고 Nodule, Fibrosis, Pneumothorax 등 저빈도 소견이 다수라 유사한 위험이 시사되나, 대상 장기(척추 vs 흉부)가 달라 수치를 직접 적용할 수는 없다.

## 공통 축 (axes)

- **기관 간 일반화**: 다기관 데이터에서의 성능 안정성/재현성
- **희귀 소견에서의 성능 저하**: 저빈도 진단에서 나타나는 정밀도 손실
- **소견-보고서 연계** / **설명가능성/감사가능성**: 자유텍스트 판독 소견을 구조화된 예측 근거로 연결

## 주의

이 추천은 자동 검색·요약 결과이며 **반드시 임상의의 검토를 거쳐야** 합니다. 각 논문의 관련성(relevance)과 한계(caveat)는 코호트 수준 통계에 근거한 추정이며, 개별 환자 사례에 대한 결론이 아닙니다.
