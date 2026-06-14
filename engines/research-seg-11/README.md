# research-seg-11

## Engine 개요

| 항목 | 내용 |
| --- | --- |
| Engine Name | ACR `research/seg-11` |
| Docker image | `neurophet.azurecr.io/research/seg-11:38014` |
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
| Oracle profile | `profiles/research-seg-11-hold.yaml` (실행 불가 사유 기록용, executable 아님) |

## 최신 평가 상태

| 항목 | 내용 |
| --- | --- |
| 최신 평가 버전 | `38014` |
| 최신 평가일 | 2026-06-12 |
| 정량검증 결과 | NA |
| 정성검증 결과 | NA |
| 최종 의견 | Hold |
| 최신 보고서 | dependency failure 기록 |

## 확인된 결과

- default entrypoint probe 단계에서 `torchio` Python dependency 누락으로 실패.
- 현재 상태에서는 Oracle이 args/input/output 계약을 자동 정리할 수 없음.
- ACR tag/profile match API와 온보딩 UI에는 hold profile의 `probe_failure`만 표시하고, 실행 프로파일은 자동 적용하지 않음.

## 남은 일

- image owner가 `torchio` runtime dependency를 Docker image에 포함.
- dependency 보정 후 `--help` probe 재실행.
- input/output 계약 확정 후 Oracle K8s smoke Run 수행.
