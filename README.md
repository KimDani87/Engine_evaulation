# Engine Evaluation Knowledge Base

뉴로핏 인공지능 기술 검증을 위한 보고서 양식과 기술별 판단 기준을 정리하는 문서 저장소입니다.

이 저장소는 Oracle 기반 정성검증과 눈검증 기반 정량검증을 함께 다루며, 제품/엔진별 release 판단에 필요한 근거를 Markdown 문서로 축적합니다.

## 목적

- 엔진 분석 보고서 양식 표준화
- 엔진별 주요 평가 포인트 정리
- 정량검증 결과와 정성검증 판단을 같은 release decision 흐름 안에서 연결
- Good / Moderate / Warning / Critical / NA 등급 기준과 주요 근거를 누적
- 검증자, 의료진, 개발자가 같은 판단 포인트를 보고 논의할 수 있는 문서 기반 마련

## 문서 원칙

- 기본 문서는 Markdown(`.md`)으로 작성합니다.
- 수치, case review, release 판단은 근거가 되는 데이터/실험/run/report를 함께 남깁니다.
- 정량검증과 정성검증을 분리하되, 최종 판단에서는 하나의 종합 의견으로 연결합니다.
- 엔진별 특성에 따라 공통 체크포인트를 유지하면서도 추가 판단 포인트를 확장할 수 있게 작성합니다.

## 초기 양식

| 문서 | 용도 |
| --- | --- |
| `docs/templates/engine-analysis-report-template.md` | 엔진 버전별 분석 보고서 양식 |
| `docs/templates/engine-key-evaluation-points-template.md` | 엔진별 주요 평가 포인트 정의 양식 |
| `docs/templates/engine-result-log-template.md` | 엔진별 평가 결과 누적 로그 양식 |

## 엔진별 결과 정리 공간

엔진별 실제 결과와 판단 포인트는 `engines/` 아래에 정리합니다.

```text
engines/
  README.md
  _template/
    README.md
    key-evaluation-points.md
    result-log.md
    reports/
      .gitkeep
```

새 엔진을 추가할 때는 `engines/_template` 폴더를 복사해서 `engines/<engine-id>/`로 만들고, 아래 문서를 채웁니다.

| 파일 | 용도 |
| --- | --- |
| `README.md` | 엔진 개요와 최신 평가 상태 |
| `key-evaluation-points.md` | 해당 엔진에서 특히 중요한 평가 포인트 |
| `result-log.md` | 버전별 정량/정성 평가 결과 누적 |
| `reports/` | 버전별 엔진 분석 보고서 |

## 권장 작성 흐름

1. 엔진별 주요 평가 포인트를 먼저 작성합니다.
2. 해당 기준에 따라 엔진 분석 보고서를 작성합니다.
3. 엔진 분석 보고서를 `engines/<engine-id>/reports/`에 저장합니다.
4. 결과 요약을 `engines/<engine-id>/result-log.md`에 누적합니다.
5. Warning / Critical 항목을 release decision에 연결합니다. Warning은 release 자체를 막지는 않지만 조치가 권장되는 상태로 기록하고, Critical은 보류/반려 의견으로 다룹니다.
6. 최종 의견을 `Pass`, `Conditional Pass`, `Hold`, `Reject` 중 하나로 남깁니다.
