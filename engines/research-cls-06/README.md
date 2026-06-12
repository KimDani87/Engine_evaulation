# research-cls-06

## Engine 개요

| 항목 | 내용 |
| --- | --- |
| Engine Name | ACR `research/cls-06` |
| Docker image | `neurophet.azurecr.io/research/cls-06:37914` |
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
| Args template | `--help` probe 결과 기반으로 확정 필요 |
| Input format | TBD |
| Output format | TBD |
| Output artifact | TBD |
| Oracle profile | TBD |

## 최신 평가 상태

| 항목 | 내용 |
| --- | --- |
| 최신 평가 버전 | `37914` |
| 최신 평가일 | 2026-06-12 |
| 정량검증 결과 | NA |
| 정성검증 결과 | NA |
| 최종 의견 | Hold |
| 최신 보고서 | `--help` probe 성공 기록 |

## 확인된 결과

- `--help` probe는 성공.
- 실제 분석용 input schema, output artifact filename, output normalization 계약은 아직 Oracle profile로 고정되지 않음.

## 남은 일

- `docker run --rm neurophet.azurecr.io/research/cls-06:37914 --help` 결과를 기준으로 args template 확정.
- `<oracle_input_manifest>` 사용 여부와 입력 JSON schema 확정.
- `<oracle_output_dir>` 사용 여부, output filename, parser format 확정.
- 확정 후 Oracle K8s smoke Run으로 결과 import까지 검증.
