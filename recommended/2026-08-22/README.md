# Daily paper recommendations — 2026-08-22

- **연구 기준일**: 2026-08-22 (KST 전일 기준)
- **실제 검색 창**: 2026-07-24 ~ 2026-08-22 (1일, 7일 창에서 3편 미달로 30일 창까지 확대)
- **검색어**: `chest X-ray classification external validation generalization`
  (1차 시도: `chest radiograph deep learning multicenter diagnosis`, 1일/7일 창에서
  각 0건/1건만 반환되어 재검색)

## 코호트 요약 (환자 단위 값 없음)

- 총 272건, 성별 남 136 / 여 136, 연령 9–87세 (평균 51.5세)
- 촬영 자세: PA 184건, AP 88건
- 기관 5곳(INST01–05), 기관별 48–62건으로 비교적 고르게 분포
- 소견 라벨: No Finding 145건, Infiltration 21건, Atelectasis 16건, Nodule 7건,
  Fibrosis 6건, Effusion 6건, Cardiomegaly 5건, Pneumothorax 5건 등 (복합 라벨 다수)
- 판독 상태: preliminary 68 / addendum 70 / final 76 / amended 58

## 선정 논문

### 1. Advancing human-centric AI for robust X-ray analysis through holistic self-supervised learning (Nature Communications, 2026)
- **축**: 기관 간 일반화, 인구통계 편향
- 840,000장으로 학습하고 12개 공개 데이터셋 82,000장으로 평가한 자기지도 흉부 X-ray
  인코더(RayDINO)를 제시하며, 연령·성별 편향까지 분석했다.
- 우리 코호트는 5개 기관, 남녀 균등 분포, 넓은 연령대(9–87세)를 가지고 있어 이 논문이
  강조하는 기관 간 일반화·인구통계 편향 분석 프레임을 그대로 적용해볼 수 있다.
- 다만 272건 규모의 단일 연구 코호트로는 논문 수준의 대규모 외부 검증을 재현할 수 없다.
- 링크: https://doi.org/10.1038/s41467-026-76076-4

### 2. A foundation model for acute abdomen diagnosis stratification and triage on noncontrast CT (Nature Communications, 2026)
- **축**: 기관 간 일반화, 판독의 보조 및 워크플로
- 복부 응급질환 파운데이션 모델(AbdomenNet)을 3개 독립 외부 코호트에서 검증하고,
  판독의 보조 시 정확도·판독 시간 개선까지 정량화했다.
- 우리 데이터의 다기관 구성과 다양한 report_status(예비/추가/최종/수정)는 이 논문의
  다기관 외부 검증·판독 워크플로 개선이라는 주제와 맞물린다.
- 모달리티가 복부 CT로 우리의 흉부 X-ray 코호트와 달라, 임상 정확도 수치를 직접
  검증할 수는 없다.
- 링크: https://doi.org/10.1038/s41467-026-76634-w

### 3. Automatic extraction of structured information from brain MRI reports using an open-weight LLM (European Radiology, 2026)
- **축**: 보고서 텍스트 구조화, 판독의 보조 및 워크플로
- 개방형 LLM(LLaMA 3.1)으로 네덜란드어 뇌 MRI 판독문 947건에서 30개 변수를 few-shot
  프롬프팅으로 자동 추출한 결과를 보고했다.
- 우리 코호트의 report_text/clinical_info 자유 텍스트 필드와 다단계 판독 상태 관리는
  LLM 기반 자동 구조화 적용 가능성을 시사한다.
- 언어(네덜란드어)와 모달리티(뇌 MRI 대 흉부 X-ray)가 달라 이 논문의 정확도 수치를
  그대로 우리 데이터에 적용할 수 없다.
- 링크: https://doi.org/10.1007/s00330-026-12821-z

## 검토 안내

이 추천 목록은 자동 검색·요약 결과이며, 실제 임상 적용 여부는 반드시 담당 의료진의
검토와 판단을 거쳐야 합니다.
