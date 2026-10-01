# Grabdeck

[English](#english) · [한국어](#한국어)

---

# English

This repository distributes the configuration file and release builds of the **Grabdeck** desktop app. The app's source code is not here.

> The app interface is currently in Korean.

### Features

A research tool for finding, organizing, and saving YouTube content in one app.

- **Research** — Find videos by keyword or channel that match your filters (views, date range, Shorts/long-form) and collect them in a list. You can also import your own subscribed channels.
- **Library** — Save and manage the videos you found. Edit and color cells directly like a spreadsheet, and filter or sort by column.
- **Download** — Paste multiple channel, video, or Shorts URLs at once, download only the videos that match your filters, and export a spreadsheet list (TSV) and merged subtitles (transcripts) per language.
- **Topic saturation** — See at a glance how heavily a topic (keyword) has already been covered, as a thumbnail grid, then drill in with detailed search.

Use the download features only for content you own, content in the public domain, or content you have permission to download. You are responsible for complying with copyright law and the platform's terms.

### Download

Pick the file for your computer:

- 👉 **[Windows](../../releases/latest/download/ViewMine-windows.zip)** — unzip and run `ViewMine.exe`
- 👉 **[macOS (Apple Silicon / M1 or later)](../../releases/latest/download/ViewMine-macos-arm64.zip)**

> These links download the latest version directly.
> The **`Source code (zip/tar.gz)`** files on the release page are not the app — you do not need them.


On macOS, unzip the app, **move it to the Applications folder**, then **right-click → `Open` → `Open`**. (If you run it without moving it, macOS runs it from a temporary quarantined location.) Double-clicking shows an "unidentified developer" warning because the build is not signed. If it still does not open, go to **System Settings → Privacy & Security → "Open Anyway"**. After the first launch, double-clicking works.

### Access code / license key

On first launch, the app asks for the code you received when you purchased. Enter it once — it is saved, and you will not be asked again on that computer. You will need to enter it again after changing computers or reinstalling. Letter case, hyphens, and spaces are ignored (`YTBE-A7K2-M3Q9-X8T5` = `ytbe a7k2 m3q9 x8t5`).

### Windows: what is the `_internal` folder?

It holds the components the app needs (ffmpeg, deno, PyQt5, yt-dlp, and the Python runtime), so you do not have to install Python or ffmpeg separately. **Always keep `ViewMine.exe` and the `_internal` folder together.** To launch from the desktop, right-click the exe → **Create shortcut**, and move the shortcut instead. Moving the whole folder is fine.

### Duplicate-prevention lists

After a run, `downloaded_shorts.txt` and `downloaded_longform.txt` are created in your save folder. They record the IDs of videos you already downloaded so the next run in the same folder skips them. Do not delete them unless you want to download everything again.

### Output files

| File | Description |
|---|---|
| `[uploader_views_date_title_ID].mp4` | Downloaded video |
| `youtube_list_<date>.tsv` | List (opens directly in Google Sheets) |
| `자막_<lang>_<date>.txt` | Subtitles (transcript) merged per language |
| `downloaded_shorts.txt` / `downloaded_longform.txt` | Duplicate-prevention lists |

### beta_config.json

The app reads this file at launch to check whether it may run, so **an internet connection is required**.

| Field | Description |
|---|---|
| `beta_enabled` | `false` stops the app for everyone immediately |
| `trial_days` | The app stops this many days after first launch |
| `min_app_version` | Versions below this are blocked (update required) |
| `latest_app_version` | Versions below this show an update notice only |
| `download_url` | Download URL for the new version |
| `message` | Message shown when the app is stopped |

### Browser cookies

The "use browser cookies" option helps YouTube recognize you as a signed-in user, which reduces blocking. **The app works without it in most cases.** On Windows, Chrome 127 and later encrypt cookies so other apps cannot read them (`Failed to decrypt with DPAPI`); Edge behaves the same. Either continue without cookies, or install Firefox and sign in to YouTube there — the app finds it automatically. Without cookies, very heavy downloading can be temporarily blocked by YouTube; the app pauses 20–40 seconds between videos to reduce this, so slow progress is normal.

### Uninstall

There is no uninstaller.

- **Windows** — delete the app folder (the one with `ViewMine.exe` and `_internal`), then open `Win` + `R` → `%LOCALAPPDATA%` and delete the `ViewMine` folder. Optionally delete the `yt-dlp` cache folder under `%APPDATA%`.
- **macOS** — move `ViewMine.app` to the Trash, then in Finder press `⌘` + `⇧` + `G` → `~/Library/Application Support` and delete the `ViewMine` folder. Optionally delete `~/.cache/yt-dlp`. Empty the Trash.

Files you downloaded stay in your save folder. Deleting the settings folder also deletes your saved access code, so keep your code. If another program also uses yt-dlp, keep the cache folder.

### Contact

skykstarfam@gmail.com

---

# 한국어

**Grabdeck** 데스크톱 앱의 설정 파일과 실행 파일을 배포하는 저장소입니다. 앱 소스 코드는 여기에 없습니다.

### 주요 기능

유튜브 소재를 **찾고 · 정리하고 · 받는 것**을 한 앱에서 하는 리서치 도구입니다.

- **리서치** — 키워드·채널로 조건(조회수·기간·쇼츠/롱폼)에 맞는 영상을 찾아 목록으로 모읍니다. 본인 구독 채널 불러오기도 됩니다.
- **보관함** — 찾은 영상을 목록으로 저장·관리합니다. **구글 시트처럼** 셀을 직접 편집·색칠하고, 열 필터·정렬로 다룹니다.
- **다운로드** — 채널·영상·쇼츠 주소를 한 번에 넣어 **조건에 맞는 영상만 골라** 받고, 스프레드시트용 목록(TSV)과 **언어별 통합 자막(대본)** 까지 뽑습니다.
- **소재 포화도** — 소재(키워드)가 **얼마나 많이 다뤄졌는지** 썸네일 격자로 한눈에 보고, 상세 검색으로 파고듭니다.

다운로드 기능은 본인 소유 콘텐츠, 공공 저작물, 또는 권리자·플랫폼의 허락을 받은 콘텐츠에만 사용하세요. 저작권법과 플랫폼 약관을 지킬 책임은 이용자에게 있습니다.

### 다운로드

자기 컴퓨터에 맞는 것을 눌러 **바로 받으세요:**

- 👉 **[Windows 다운로드](../../releases/latest/download/ViewMine-windows.zip)** — 압축을 풀고 `ViewMine.exe` 실행
- 👉 **[macOS (Apple Silicon / M1 이상) 다운로드](../../releases/latest/download/ViewMine-macos-arm64.zip)**

> 위 버튼은 최신 버전 파일을 곧바로 내려받습니다.
> 릴리스 페이지에 함께 보이는 **`Source code (zip/tar.gz)`** 는 앱이 아니라 개발용 소스라 **받지 않으셔도 됩니다.**


macOS는 압축을 푼 뒤 앱을 **응용 프로그램 폴더로 옮기고**,
**마우스 오른쪽 클릭 → `열기` → 다시 `열기`** 로 실행하세요.
(옮기지 않고 실행하면 macOS가 임시 위치에서 격리 실행합니다)
그냥 더블클릭하면 "확인되지 않은 개발자" 경고로 열리지 않습니다.
위 방식으로도 안 열리면 **설정 → 개인정보 보호 및 보안 → 아래쪽 '그래도 열기'** 를 누르세요.
(개발자 서명을 하지 않은 빌드라서 그렇습니다. 한 번 열면 이후에는 더블클릭으로 열립니다.)

### 참가 코드

앱을 처음 실행하면 **참가 코드**를 한 번 입력받습니다.
구매하실 때 안내받은 코드를 넣어주세요.

- 한 번 입력하면 저장되어 다음부터는 묻지 않습니다
- 컴퓨터를 바꾸거나 새로 설치하면 다시 입력해야 합니다
- 대소문자, 하이픈, 공백은 구분하지 않습니다
  (`YTBE-A7K2-M3Q9-X8T5` = `ytbe a7k2 m3q9 x8t5`)

코드를 잃어버리셨거나 입력해도 통과되지 않으면 문의해 주세요.

### Windows: `_internal` 폴더는 무엇인가요

압축을 풀면 `ViewMine.exe` 옆에 `_internal` 폴더가 함께 나옵니다.
앱이 돌아가는 데 필요한 부품이 들어 있는 폴더입니다.

| 들어있는 것 | 용도 |
|---|---|
| `ffmpeg_bin` | 영상과 음성을 합치는 ffmpeg |
| `js_bin` | 유튜브 서명 처리에 쓰는 deno |
| `PyQt5` | 앱 화면을 그리는 라이브러리 |
| `yt_dlp` | 유튜브 다운로드 엔진 |
| `python*.dll` 등 | 파이썬 실행 환경 |

이것들이 함께 들어 있어서 **파이썬이나 ffmpeg를 따로 설치하지 않아도** 됩니다.
파일 크기가 큰 이유이기도 합니다.

> ⚠️ **`exe` 파일과 `_internal` 폴더는 항상 같은 위치에 함께 두세요.**
> `exe`만 바탕화면 등으로 옮기면 부품을 찾지 못해 실행되지 않습니다.
> 바탕화면에서 실행하고 싶다면 `exe` **우클릭 → 바로 가기 만들기** 후
> 만들어진 바로 가기를 옮기면 됩니다.
> 폴더를 통째로 다른 위치로 옮기는 것은 괜찮습니다.

macOS는 같은 파일들이 `.app` 안에 들어 있어 겉으로 보이지 않습니다.

### 중복 방지 목록 (자동 생성되는 txt 파일)

작업이 끝나면 **저장 폴더 안에** 아래 파일이 생깁니다.

| 파일 | 기록 대상 |
|---|---|
| `downloaded_shorts.txt` | 이미 받은 **쇼츠**(세로형) |
| `downloaded_longform.txt` | 이미 받은 **롱폼**(가로형) |

받은 영상의 ID가 한 줄씩 기록되며, **다음에 같은 폴더로 실행하면 그 영상들은 건너뜁니다.**
같은 채널을 주기적으로 돌릴 때 이미 받은 것을 또 받지 않게 해주는 장치입니다.

- 쇼츠와 롱폼은 **파일이 따로**입니다. 쇼츠만 받았다면 `downloaded_longform.txt`는 생기지 않습니다.
- **지우지 마세요.** 지우면 다음 실행 때 전부 다시 받습니다.
- 반대로 **일부러 다시 받고 싶으면** 이 파일을 지우거나, 다른 폴더를 저장 위치로 지정하면 됩니다.
- 저장 폴더를 바꾸면 새 폴더에는 기록이 없으므로 처음부터 다시 받습니다.

> 건너뛴 영상은 완료 창과 로그에 `이미 받은 영상이라 건너뜀`으로 표시됩니다.
> 다운로드 개수에도 포함되지 않으니, 숫자가 예상보다 적다면 이 경우인지 확인해보세요.

### 결과물로 만들어지는 파일

| 파일 | 설명 |
|---|---|
| `[업로더_조회수_날짜_제목_ID].mp4` | 받은 영상 |
| `youtube_list_<날짜>.tsv` | 목록 (구글 스프레드시트에서 바로 열림) |
| `자막_ko_<날짜>.txt` | 언어별로 합친 자막(대본) |
| `downloaded_shorts.txt` / `downloaded_longform.txt` | 위의 중복 방지 목록 |

영상 파일 이름이 `[` 로 시작해서 폴더 정렬에 따라 위나 아래 끝에 몰릴 수 있습니다.
안 보인다고 느껴지면 이름순 정렬을 확인해보세요.

### beta_config.json

앱이 실행될 때 이 파일을 읽어 사용 가능 여부를 확인합니다.
따라서 **앱을 실행하려면 인터넷 연결이 필요합니다.**

| 필드 | 설명 |
|---|---|
| `beta_enabled` | `false`면 즉시 전체 사용 중지 |
| `trial_days` | 처음 실행일부터 이 일수가 지나면 자동으로 사용 중지 |
| `min_app_version` | 이 버전보다 낮으면 실행 차단 (업데이트 필요) |
| `latest_app_version` | 이 버전보다 낮으면 업데이트 안내만 표시 (계속 사용 가능) |
| `download_url` | 새 버전 다운로드 주소 |
| `message` | 사용 중지 시 표시할 안내 문구 |

### 쿠키를 읽지 못한다고 나올 때

`브라우저 쿠키 사용` 옵션은 유튜브가 여러분을 '로그인한 사용자'로 인식하게 해
차단을 덜 당하게 하는 기능입니다. **없어도 대부분 정상 동작합니다.**

#### Windows에서 Chrome을 쓰시는 경우

**Chrome 127 버전부터는 쿠키를 읽을 수 없습니다.** Chrome이 쿠키를 자기만 풀 수 있는
방식으로 암호화하도록 바뀌었기 때문입니다. Chrome을 완전히 종료해도 해결되지 않습니다.
(오류 메시지: `Failed to decrypt with DPAPI`)

선택지는 두 가지입니다.

| 방법 | 내용 |
|---|---|
| **그냥 쿠키 없이 쓰기** | `쿠키 없이 계속`을 누르면 됩니다. 한 번 누르면 다음부터 묻지 않습니다 |
| **Firefox 사용** | Firefox를 설치해 유튜브에 로그인해 두면 앱이 자동으로 찾아 씁니다 |

> Edge는 Chrome과 같은 구조라 대부분 동일하게 막힙니다. Firefox를 쓰세요.

#### 다시 쿠키를 쓰고 싶을 때

`쿠키 없이 계속`을 누르면 **`브라우저 쿠키 사용` 체크가 자동으로 꺼집니다.**
나중에 다시 쓰시려면 그 체크박스를 켜기만 하면 됩니다.

#### 쿠키 없이 쓸 때 유의할 점

영상을 아주 많이 받으면 유튜브가 접속을 일시적으로 막을 수 있습니다.
앱이 영상마다 20~40초씩 쉬면서 이를 줄이고 있으니, 진행이 느린 것은 정상입니다.

### 삭제하는 방법

별도의 제거 프로그램이 없습니다. 아래 순서대로 지우시면 흔적이 남지 않습니다.

---

#### 🪟 Windows

**1단계 — 앱 폴더 삭제**

압축을 풀어둔 폴더를 통째로 지웁니다.
`ViewMine.exe`와 `_internal` 폴더가 함께 들어 있는 그 폴더입니다.

> 바탕화면에 바로 가기를 만들어 두셨다면 그것도 함께 지워주세요.

**2단계 — 설정 폴더 삭제**

1. 키보드에서 `Win` + `R`
2. 아래를 붙여넣고 `확인`
   ```
   %LOCALAPPDATA%
   ```
3. 열린 창에서 **`ViewMine`** 폴더를 찾아 삭제

이 폴더에 들어 있는 것:

| 파일 | 내용 |
|---|---|
| `beta_state.json` | 참가 코드, 사용 시작일 |
| `update.log` | 업데이트 기록 |
| `ytdlp` 폴더 | 자동으로 받아둔 최신 다운로드 엔진 |

**3단계 (선택) — 캐시 삭제**

`Win` + `R` 에 아래를 넣고 `yt-dlp` 폴더를 삭제합니다. 수백 KB라 남겨두어도 됩니다.

```
%APPDATA%
```

없으면 `%LOCALAPPDATA%` 안에도 확인해 보세요.

---

#### 🍎 macOS

**1단계 — 앱 삭제**

`응용 프로그램` 폴더(또는 압축을 푼 위치)에서
**`ViewMine.app`** 을 휴지통으로 옮깁니다.

**2단계 — 설정 폴더 삭제**

1. Finder를 열고 `⌘` + `⇧` + `G`
2. 아래를 붙여넣고 `Enter`
   ```
   ~/Library/Application Support
   ```
3. 열린 창에서 **`ViewMine`** 폴더를 휴지통으로

이 폴더에 들어 있는 것:

| 파일 | 내용 |
|---|---|
| `beta_state.json` | 참가 코드, 사용 시작일 |
| `update.log` | 업데이트 기록 |
| `ytdlp` 폴더 | 자동으로 받아둔 최신 다운로드 엔진 |

**3단계 (선택) — 캐시 삭제**

`⌘` + `⇧` + `G` 에 아래를 넣고 폴더째 삭제합니다. 수백 KB라 남겨두어도 됩니다.

```
~/.cache/yt-dlp
```

**4단계 — 휴지통 비우기**

---

#### 지워지지 **않는** 것

다운로드한 결과물은 **여러분이 지정한 저장 폴더**에 그대로 남습니다.
앱을 지워도 사라지지 않으니, 필요 없으면 직접 정리하세요.

- 영상 파일 `[업로더_조회수_날짜_제목_ID].mp4`
- 목록 `youtube_list_....tsv`
- 자막 `자막_ko_....txt`
- 중복 방지 목록 `downloaded_shorts.txt` / `downloaded_longform.txt`

---

> ⚠️ **설정 폴더를 지우면 참가 코드 기록도 함께 사라집니다.**
> 다시 설치하실 때 코드를 한 번 더 입력하셔야 하니, 받으신 코드는 잘 보관해 주세요.

> 💡 **다른 프로그램에서도 yt-dlp를 쓰신다면** 3단계 캐시 폴더는 함께 쓰는 것일 수 있습니다.
> 그럴 때는 지우지 말고 남겨두세요.

### 문의

문의는 스레드로 부탁드립니다.
