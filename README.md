# no-mad-max-dataset

[No Max Max](https://github.com/jangvis/no-mad-max) 앱이 사용하는 전국 무인교통단속카메라
데이터셋 배포용 저장소입니다. 이 저장소의 파일은 사람이 직접 편집하지 않습니다 — 전부
`no-mad-max` 저장소의 GitHub Actions 워크플로(`.github/workflows/publish-dataset.yml`)가
주기적으로 자동 커밋합니다.

## 구조

- `manifest.json` — 최신 데이터셋 버전 정보(체크섬, 건수, 스키마 버전 등). 앱이 조회하는
  고정 경로입니다.
- `bundles/cameras_<YYYY-MM-DD>.db.gz` — 실제 카메라 DB 번들(압축 SQLite). 버전마다 별도
  파일이며, 최근 몇 개만 보관합니다.
- `dataset-fingerprint.txt` — 내부용(정제 결과 내용 지문). 앱은 이 파일을 쓰지 않습니다.

앱은 GitHub Pages가 아니라 `https://raw.githubusercontent.com/jangvis/no-mad-max-dataset/main/...`
경로로 이 파일들을 직접 받습니다.

## 데이터 출처 및 라이선스

본 데이터셋은 경찰청이 제공하고 공공데이터포털(data.go.kr)이 개방한
"전국무인교통단속카메라표준데이터"를 가공한 것입니다(공공누리 제1유형, 출처표시).
데이터에 제3자 권리가 포함될 수 있으며, 해당 부분은 원 저작권자의 권리가 유지됩니다.

원본: [공공데이터포털](https://www.data.go.kr) — "전국무인교통단속카메라표준데이터"
(`tn_pubr_public_unmanned_traffic_camera_api`)
