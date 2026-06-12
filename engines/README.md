# Engines

엔진별 평가 포인트, 평가 결과 로그, 버전별 분석 보고서를 정리하는 공간입니다.

## 사용 방법

1. 새 엔진을 추가할 때 `engines/_template`을 복사합니다.
2. 폴더 이름은 가능한 한 제품/엔진 식별이 쉬운 소문자 kebab-case로 작성합니다.
3. `key-evaluation-points.md`에 해당 엔진에서 중요한 판단 포인트를 먼저 정리합니다.
4. 버전별 보고서는 `reports/` 아래에 저장합니다.
5. 각 평가 결과 요약은 `result-log.md`에 한 줄씩 누적합니다.

## 엔진 목록

| Engine ID | Engine Name | 대상 제품 | 최신 평가 버전 | 최신 최종 의견 | 비고 |
| --- | --- | --- | --- | --- | --- |
| `research-ana-23` | ACR research/ana-23 | TBD | `37915` | Conditional Pass | Oracle K8s smoke 성공. `literal_json` input manifest와 `engine_resources_json` result artifact 계약 필요 |
| `research-cls-06` | ACR research/cls-06 | TBD | `37914` | Hold | `--help` probe 성공. 실제 input/output schema와 Oracle result normalization 계약 추가 필요 |
| `research-seg-05` | ACR research/seg-05 | TBD | `37744` | Hold | default entrypoint probe에서 `libGL.so.1` 누락 확인. image dependency 보정 전 실행 보류 |
| `research-seg-11` | ACR research/seg-11 | TBD | `38014` | Hold | default entrypoint probe에서 `torchio` 누락 확인. image dependency 보정 전 실행 보류 |

## Oracle K8s 실행 계약 요약

ACR 연구용 Docker는 `neurophet.azurecr.io/research/<repo>:<tag>` 형식으로 실행한다.
Oracle profile에는 Docker repository/tag와 함께 backend별 실행 계약을 정확히 저장해야 한다.

K8s research image profile의 최소 계약:

- `execution.backend: k8s_research_image`
- `execution.inference_runtime.image_repository`
- `execution.inference_runtime.image_tag`
- `execution.inference_runtime.entrypoint_mode`
- `execution.inference_runtime.command` 또는 `args`
- `<oracle_input_manifest>`를 쓰면 `input_manifest.format`
- `<oracle_output_dir>`를 쓰면 `output_artifact.format`과 `filename` 또는 `filenames`

현재 Oracle은 input/output format을 추정하지 않는다.
허용 format은 `literal_json`, `oracle.research.input_manifest.v1`, `engine_resources_json`, `oracle_result_json`뿐이다.
