# YouTube Batch Extractor — 베타 배포

**YouTube Batch Extractor** 베타 버전의 설정 파일과 실행 파일을 배포하는 저장소입니다.
앱 소스 코드는 여기에 없습니다.

## 다운로드

👉 **[최신 버전 받기](../../releases/latest)**

- **Windows**: `...-windows.zip` — 압축을 풀고 `YouTubeBatchExtractor.exe` 실행
- **macOS (Apple Silicon / M1 이상)**: `...-macos-arm64.zip`
- **macOS (Intel)**: `...-macos-intel.zip`

macOS는 압축을 푼 뒤 앱을 **마우스 오른쪽 클릭 → `열기` → 다시 `열기`** 로 실행하세요.
그냥 더블클릭하면 "확인되지 않은 개발자" 경고로 열리지 않습니다.
(개발자 서명을 하지 않은 베타 빌드라서 그렇습니다. 한 번 열면 이후에는 더블클릭으로 열립니다.)

## beta_config.json

앱이 실행될 때 이 파일을 읽어 사용 가능 여부를 확인합니다.
따라서 **앱을 실행하려면 인터넷 연결이 필요합니다.**

| 필드 | 설명 |
|---|---|
| `beta_enabled` | `false`면 즉시 전체 사용 중지 |
| `expire_date` | 이 날짜(UTC)가 지나면 자동으로 사용 중지 |
| `min_app_version` | 이 버전보다 낮으면 실행 차단 (업데이트 필요) |
| `latest_app_version` | 이 버전보다 낮으면 업데이트 안내만 표시 (계속 사용 가능) |
| `download_url` | 새 버전 다운로드 주소 |
| `message` | 사용 중지 시 표시할 안내 문구 |

## 문의

베타 관련 문의는 스레드로 부탁드립니다.
