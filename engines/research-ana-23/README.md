# research-ana-23

## Engine 개요

| 항목 | 내용 |
| --- | --- |
| Engine Name | ACR `research/ana-23` |
| Docker image | `neurophet.azurecr.io/research/ana-23:37915` |
| 대상 제품 | TBD |
| 임상 목적 | TBD |
| 입력 데이터 | ANA-23 RAW_VOLUME resource JSON |
| 주요 출력 | `result.json`의 `resources[]` 기반 HOC regression 값 |
| Owner | TBD |

## Oracle 실행 계약

| 항목 | 내용 |
| --- | --- |
| Backend | `k8s_research_image` |
| Entry point | `image_default` |
| Args template | `--input <oracle_input_manifest> --output <oracle_output_dir> --age <age> --sex <sex> --race <race>` |
| Input format | `literal_json` |
| Required payload | `resources[].code == RAW_VOLUME`, index `112`, `105`, `212`, `205` |
| Output format | `engine_resources_json` |
| Output artifact | `result.json` |
| Oracle profile | `profiles/research-ana-23-smoke.yaml` |

## 최신 평가 상태

| 항목 | 내용 |
| --- | --- |
| 최신 평가 버전 | `37915` |
| 최신 평가일 | 2026-06-12 |
| 정량검증 결과 | NA |
| 정성검증 결과 | NA |
| 최종 의견 | Conditional Pass |
| 최신 보고서 | Oracle K8s smoke 기록 |

## 확인된 결과

- `--help` probe 성공.
- default entrypoint + ConfigMap input manifest + K8s output collector 경로 성공.
- strict I/O 계약에서 `input_manifest.format=literal_json`, `output_artifact.format=engine_resources_json`, `output_artifact.filename=result.json`이 명시된 경우에만 실행 가능.
- 운영 K8s smoke에서 `hoc_calculation=0.7208476490424381`, Pod node `gn139`, image digest `sha256:56c8cc4635572cfb773eb8b7373c85b6b79007d201f0f458d1fe5de19fe9f948` 확인.

## 남은 일

- 실제 제품/임상 목적과 owner 입력.
- RAW_VOLUME JSON schema를 엔진 owner 기준 문서로 확정.
- HOC regression 외 output normalization 기준 확장 여부 확인.
