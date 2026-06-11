# 엔진 분석 보고서 양식

> 정량검증(눈검증)과 정성검증(Oracle)을 함께 기록하는 엔진 버전별 release 판단 보고서 양식입니다.

## 0. 문서 정보

| 항목 | 내용 |
| --- | --- |
| 문서명 |  |
| 작성 버전 |  |
| 작성자 |  |
| 검토자 |  |
| 작성일 |  |
| 검토일 |  |
| 관련 제품 |  |
| 관련 엔진 |  |
| 관련 이슈 / PR / 릴리즈 |  |

## 1. 평가 대상 Engine 정보 및 평가 시점

| 항목 | 내용 |
| --- | --- |
| Engine Name |  |
| Engine Version / Algorithm Version |  |
| Commit hash |  |
| 대상 제품 |  |
| 주요 변경 사항 |  |
| 평가자 / Reviewer |  |
| 평가일 |  |
| 평가 범위 | 정량검증 / 정성검증 / 기타 |
| 평가 데이터 |  |
| 분석 PC 정보 | CPU / RAM / GPU / OS |
| 실행 환경 | local / server / container / 기타 |

## 2. 평가 등급 정의

| 결과 | 의미 |
| --- | --- |
| Good | 좋은 결과로 판단되며, 기존 기준 대비 긍정적이거나 기대 수준을 명확히 충족함 |
| Moderate | 특별한 문제가 없으며, release를 제한할 만한 우려가 확인되지 않음 |
| Warning | release 여부는 선택 가능하나, 보완 조치 또는 후속 모니터링이 권장됨 |
| Critical | release 보류 또는 반려 의견이 필요함 |
| NA | 해당 알고리즘 변경 또는 평가 범위에 적용되지 않음 |

## 3. Executive Summary

| 항목 | 내용 |
| --- | --- |
| 정량검증 요약 |  |
| 정성검증 요약 |  |
| 주요 긍정 사항 |  |
| 주요 우려 사항 |  |
| Critical 항목 여부 | 있음 / 없음 |
| Warning 항목 여부 | 있음 / 없음 |
| 최종 의견 | Pass / Conditional Pass / Hold / Reject |

## 4. 정량검증 결과

정량검증은 original validation set과 주요 artifact 조건에서 validation performance를 확인하여 엔진의 robustness를 평가합니다.

| 구분 | 항목 | 판단 포인트 | 결과 | 근거 |
| --- | --- | --- | --- | --- |
| 정량검증 | Validation performance - Original | 원본 validation set에서 기존 버전 대비 성능이 유지 또는 개선되었는지 확인 | Good / Moderate / Warning / Critical / NA |  |
| 정량검증 | Validation performance - Noise artifact | noise artifact가 포함된 데이터에서 성능 저하가 허용 가능한 수준인지 확인 | Good / Moderate / Warning / Critical / NA |  |
| 정량검증 | Validation performance - FOV artifact | FOV 제한, 잘림 등 field-of-view artifact 상황에서 성능이 강건한지 확인 | Good / Moderate / Warning / Critical / NA |  |
| 정량검증 | Validation performance - Wrapping artifact | wrapping artifact가 있는 데이터에서 잘못된 검출 또는 누락이 증가하지 않는지 확인 | Good / Moderate / Warning / Critical / NA |  |
| 정량검증 | Validation performance - Resolution artifact | 해상도 저하 또는 resolution 차이가 있는 데이터에서 성능이 유지되는지 확인 | Good / Moderate / Warning / Critical / NA |  |
| 정량검증 | Validation performance - Comorbidity | target 질환 이외의 병변이 동시에 있는 데이터에서 성능이 유지되는지 확인 | Good / Moderate / Warning / Critical / NA |  |
| 정량검증 | Computation time | 해당 알고리즘의 분석 시간이 제품/임상 workflow에 허용 가능한지 확인 | Good / Moderate / Warning / Critical / NA |  |

### 4.1 정량검증 주요 수치

| Metric | Baseline / 이전 버전 | 평가 버전 | Delta | Acceptance Criteria | 결과 |
| --- | ---: | ---: | ---: | --- | --- |
|  |  |  |  |  |  |

### 4.2 정량검증 코멘트

| 항목 | 코멘트 | 후속 조치 |
| --- | --- | --- |
| Validation performance - Original |  |  |
| Validation performance - Noise artifact |  |  |
| Validation performance - FOV artifact |  |  |
| Validation performance - Wrapping artifact |  |  |
| Validation performance - Resolution artifact |  |  |
| Validation performance - Comorbidity |  |  |
| Computation time |  |  |

## 5. 정성검증 결과

정성검증은 의료진 사용자 관점에서 case review, 임상적 납득 가능성, 오류 위해도, workflow 적합성을 확인합니다.

| 구분 | 항목 | 판단 포인트 | 결과 | 근거 |
| --- | --- | --- | --- | --- |
| 정성검증 | 임상적 도입 가치 | 의료진 관점에서 병원이 유상으로 도입할 가치가 있는 성능/효용인지 확인 | Good / Moderate / Warning / Critical / NA |  |
| 정성검증 | 오류 케이스 임상 위해도 | 분석 실패나 오류 케이스가 환자에게 미치는 위해 가능성이 허용 가능한 수준인지 확인 | Good / Moderate / Warning / Critical / NA |  |
| 정성검증 | 출력 결과 타당성 | 출력 결과가 의학적으로 납득 가능한 위치, 크기, 개수, 형태, 수치 특성을 보이는지 확인 | Good / Moderate / Warning / Critical / NA |  |
| 정성검증 | 처리 시간 적합성 | 알고리즘 동작 시간이 target 질환의 진료 프로세스에 적합한 범위인지 확인 | Good / Moderate / Warning / Critical / NA |  |

### 5.1 정성검증 Case Review 요약

| Case ID | 입력 데이터 | 주요 관찰 | 임상적 의미 | 결과 | Reviewer |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  | Good / Moderate / Warning / Critical / NA |  |

### 5.2 정성검증 코멘트

| 항목 | 코멘트 | 후속 조치 |
| --- | --- | --- |
| 임상적 도입 가치 |  |  |
| 오류 케이스 임상 위해도 |  |  |
| 출력 결과 타당성 |  |  |
| 처리 시간 적합성 |  |  |

## 6. 주요 오류 / 우려 케이스

| 우려 ID | 구분 | 설명 | 영향도 | 재현 조건 | 권장 조치 | Release 영향 |
| --- | --- | --- | --- | --- | --- | --- |
|  | 정량 / 정성 |  | Low / Medium / High / Critical |  |  | 없음 / 조건부 / 보류 |

## 7. 종합 의견

| 항목 | 내용 |
| --- | --- |
| 정량검증 의견 |  |
| 정성검증 의견 |  |
| 종합 의견 |  |
| 주요 긍정 사항 |  |
| 주요 우려 사항 |  |
| Critical 항목 여부 | 있음 / 없음 |
| Warning 항목 여부 | 있음 / 없음 |
| 최종 의견 | Pass / Conditional Pass / Hold / Reject |

## 8. Follow-up Action Items

| Action ID | 조치 내용 | Owner | Due Date | 상태 |
| --- | --- | --- | --- | --- |
|  |  |  |  | Open / In Progress / Done / Deferred |

## 9. 참고 자료

- 정량검증 report:
- Oracle 정성검증 run / case review:
- 관련 PR / commit:
- 관련 clinical / regulatory 근거:
- 기타:
