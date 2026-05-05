A Little Wag - PWA (Progressive Web App)
=========================================

파일 구조:
  index.html      - 앱 메인 파일 (PWA 메타태그 + Service Worker 등록 포함)
  manifest.json   - PWA 매니페스트 (앱 이름, 아이콘, 테마 색상 등)
  sw.js           - Service Worker (오프라인 캐싱 지원)
  icon.svg        - SVG 아이콘 (모든 크기에 대응)
  icon-192.png    - 192x192 앱 아이콘
  icon-512.png    - 512x512 앱 아이콘 (스플래시 화면용)

─────────────────────────────────────────────
배포 방법 1: GitHub Pages (무료, 권장)
─────────────────────────────────────────────
1. GitHub 계정이 없으면 https://github.com 에서 가입
2. 새 Repository 생성 (예: little-wag-diary)
   - Public으로 설정 (Pages 무료 사용을 위해)
3. 이 폴더 안의 파일들을 모두 업로드:
   - Repository 페이지 > "uploading an existing file" 클릭
   - index.html, manifest.json, sw.js, icon.svg, icon-192.png, icon-512.png 모두 선택 후 업로드
4. Settings > Pages > Source: "Deploy from a branch" > Branch: main / (root) 선택 > Save
5. 잠시 후 https://[사용자명].github.io/[repository명]/ 주소로 접속 가능
6. 모바일에서 해당 URL 접속 후 "홈 화면에 추가" 로 설치!

─────────────────────────────────────────────
배포 방법 2: Netlify (무료, 드래그앤드롭 지원)
─────────────────────────────────────────────
1. https://netlify.com 접속 후 무료 계정 가입
2. 로그인 후 Sites 탭에서 이 폴더 전체를 드래그앤드롭
3. 자동으로 배포되며 랜덤 URL 생성됨 (예: https://little-wag-abc123.netlify.app)
4. Site Settings > Domain management에서 커스텀 도메인 설정 가능
5. 배포된 URL을 모바일에서 열고 "홈 화면에 추가"로 설치!

─────────────────────────────────────────────
로컬 테스트 방법 (PWA 기능 포함)
─────────────────────────────────────────────
Service Worker는 반드시 HTTPS 또는 localhost에서만 작동합니다.
로컬 테스트는 아래 방법 중 하나를 사용하세요:

방법 A - VS Code Live Server 확장 설치 후 index.html 열기
방법 B - Node.js 설치 후 폴더에서:
  npx serve .
  → http://localhost:3000 에서 확인

─────────────────────────────────────────────
PWA 설치 방법 (모바일)
─────────────────────────────────────────────
Android (Chrome):
  배포 URL 접속 → 주소창 우측 "설치" 버튼 또는
  메뉴(점 세개) > "앱 설치" 또는 "홈 화면에 추가"

iOS (Safari):
  배포 URL 접속 → 하단 공유 버튼(사각형+화살표) > "홈 화면에 추가"
  ※ iOS는 반드시 Safari를 사용해야 합니다

─────────────────────────────────────────────
주의사항
─────────────────────────────────────────────
- 일기 데이터는 브라우저 localStorage에만 저장됩니다
- 다른 기기와 동기화되지 않으며, 브라우저 데이터 초기화 시 삭제됩니다
- 날씨 정보는 온라인 상태에서만 불러옵니다 (오프라인 시 "Unavailable")
