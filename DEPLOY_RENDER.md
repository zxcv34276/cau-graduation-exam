# CAU 졸업시험 문제은행 PWA

322문항이 포함된 정적 웹앱입니다. 서버/DB 없이 실행되며 학습 기록은 각 기기의 브라우저 저장공간(localStorage)에 자동 저장됩니다.

## 폰에서 설치하기

배포된 HTTPS 주소로 접속한 뒤:

- **Android/Chrome**: 화면의 `앱 설치` 버튼 또는 Chrome 메뉴의 `앱 설치`/`홈 화면에 추가`를 사용합니다.
- **iPhone/iPad**: 반드시 Safari에서 열고 `공유(□↑)` → `홈 화면에 추가` → `추가`를 누릅니다.
- 한 번 정상적으로 접속하면 앱 셸이 캐시되어 오프라인에서도 문제를 열 수 있습니다.

## 기록 저장 방식

- 정답/오답, 즐겨찾기, 복습일정은 **현재 기기 + 현재 브라우저/PWA 저장공간**에 저장됩니다.
- 친구에게 같은 주소를 공유해도 기록은 서로 섞이지 않습니다.
- 기기 간 자동 동기화는 아직 없습니다. PC↔폰 이동 시 앱의 `학습기록 내보내기/불러오기`를 사용하세요.
- 브라우저 데이터 삭제/앱 데이터 초기화 시 기록이 지워질 수 있으므로 중요한 기록은 가끔 내보내기로 백업하세요.

## Render 배포 (추천)

### 방법 A — Render Static Site
1. 이 폴더의 파일 전체를 GitHub 저장소에 올립니다.
2. Render Dashboard에서 **New → Static Site**를 선택합니다.
3. GitHub 저장소를 연결합니다.
4. Build Command: `echo "No build required"`
5. Publish Directory: `.`
6. Deploy를 누릅니다.
7. 발급된 `https://...onrender.com` 주소를 휴대폰/친구에게 공유합니다.

### 방법 B — Blueprint
저장소 루트에 `render.yaml`이 들어 있으므로 Render에서 Blueprint로 저장소를 연결해도 됩니다.

## 파일 구조

- `index.html` — 322문항 데이터와 앱 UI
- `manifest.webmanifest` — PWA 설치 정보
- `service-worker.js` — 오프라인 캐시
- `icons/` — 홈 화면 아이콘
- `render.yaml` — Render Static Site 설정

## 업데이트

문제/디자인을 수정한 뒤 GitHub에 push하면 Render의 자동 배포를 켠 경우 새 버전이 배포됩니다. 앱은 페이지 이동 시 네트워크를 우선 확인하도록 구성되어 있어 새 `index.html`을 받을 수 있습니다.
