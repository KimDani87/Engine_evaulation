# research-seg-05

## Engine 개요

| 항목 | 내용 |
| --- | --- |
| Engine Name | ACR `research/seg-05` |
| Docker image | `neurophet.azurecr.io/research/seg-05:37744` |
| 대상 제품 | TBD |
| 임상 목적 | TBD |
| 입력 데이터 | TBD |
| 주요 출력 | TBD |
| Owner | TBD |

## Oracle 실행 계약

| 항목 | 내용 |
| --- | --- |
| Backend | `k8s_research_image` |
| Entry point | `image_default` 후보 |
| Args template | dependency 보정 후 probe 필요 |
| Input format | TBD |
| Output format | TBD |
| Output artifact | TBD |
| Oracle profile | TBD |

## 최신 평가 상태

| 항목 | 내용 |
| --- | --- |
| 최신 평가 버전 | `37744` |
| 최신 평가일 | 2026-06-12 |
| 정량검증 결과 | NA |
| 정성검증 결과 | NA |
| 최종 의견 | Hold |
| 최신 보고서 | dependency failure 기록 |

## 확인된 결과

- default entrypoint probe 단계에서 `libGL.so.1` 누락으로 실패.
- 현재 상태에서는 Oracle이 args/input/output 계약을 자동 정리할 수 없음.

## 남은 일

- image owner가 `libGL.so.1` runtime dependency를 Docker image에 포함하거나 base image를 보정.
- dependency 보정 후 `--help` probe 재실행.
- input/output 계약 확정 후 Oracle K8s smoke Run 수행.
