# VIA ELITE · Store Display

비아엘리떼 매장 디스플레이 시스템. 매장 테블릿에서 풀스크린 PWA로 실행되며, 본사 어드민에서 등록한 상품 슬라이드를 자동 롤링합니다.

## 핵심 기능

- 매장 계정 로그인 (어느 매장의 리드인지 파악)
- 등록 슬라이드 자동 롤링 (5초마다)
- 손가락 좌우 스와이프로 수동 전환
- "구매하기" 버튼 → 이름·연락처 입력 → 본사 시트 자동 저장
- 30초마다 어드민의 최신 슬라이드 자동 동기화
- PWA — 풀스크린 모드, 오프라인 캐시

## 폴더 구조

```
viaelite-tablet-display/
├── index.html        메인 디스플레이
├── manifest.json     PWA 설정
├── sw.js             Service Worker (오프라인 캐시)
├── vercel.json       Vercel 배포 설정
├── icons/            PWA 아이콘
│   ├── icon-192.png
│   ├── icon-512.png
│   ├── apple-touch-icon.png
│   └── favicon.png
└── README.md
```

## 배포

### 1. GitHub 업로드
1. 새 Private 저장소 생성: `viaelite-tablet-display`
2. 이 폴더의 모든 파일 업로드

### 2. Vercel 연결
1. [vercel.com](https://vercel.com) → New Project → GitHub 저장소 import
2. 빌드 설정 변경 없이 그대로 Deploy

### 3. 도메인 연결 (display.viaelite.kr)
1. Vercel 프로젝트 → Settings → Domains
2. `display.viaelite.kr` 추가
3. 가비아 DNS 설정:
   - Type: CNAME
   - 호스트: display
   - 값: cname.vercel-dns.com
4. 5분~1시간 후 ✓ Valid Configuration 확인

### 4. 백엔드 연결 (다음 단계)
현재는 데모 모드입니다. Apps Script 백엔드 셋업 후:
- `index.html` 의 `APPS_SCRIPT_URL` 자리에 발급받은 URL 붙여넣기
- 다시 배포 (Vercel은 GitHub 푸시 시 자동 배포)

## 테블릿 셋업

### 단순 PWA 사용 (간단)
1. 테블릿 Chrome/Samsung Internet에서 `display.viaelite.kr` 접속
2. 매장 ID/비밀번호로 로그인
3. 메뉴 → "홈 화면에 추가"
4. 홈 화면 아이콘 클릭 → 풀스크린 자동 실행

### 키오스크 모드 (매장 무인 운영 권장)
**Android (갤럭시 탭 등):**
1. Play Store에서 **Fully Kiosk Browser** 설치
2. 앱 실행 → Settings → Web Content Settings
3. Start URL: `https://display.viaelite.kr`
4. Kiosk Mode → On
5. Boot 시 자동 시작 설정
6. 결과: 테블릿 켜면 자동으로 디스플레이가 풀스크린 실행, 다른 앱으로 빠져나갈 수 없음

**iPad:**
1. 설정 → 손쉬운 사용 → 안내 모드 → On
2. Safari로 `https://display.viaelite.kr` 열기
3. 홈 버튼 3번 클릭 → 안내 모드 시작
4. 결과: 다른 앱 접근 차단

## 도메인 / URL

- **운영**: `https://display.viaelite.kr` (예정)
- **개발**: Vercel 자동 부여 URL

## 다음 개발 단계

- [ ] Apps Script 백엔드 (매장 인증 + 슬라이드 CRUD + 리드 저장)
- [ ] Google Drive 자동 이미지 업로드 (어드민에서 등록 시)
- [ ] Zapier 연동 (리드 들어오면 컨시어지에게 알림)
- [ ] 매장별 큐레이션 (선택)
- [ ] 통계 대시보드 (어떤 슬라이드 클릭률 높은지)

## 보안

- 매장 ID/비밀번호로 1차 인증
- 리드 정보는 본사 Google Sheet에만 저장
- 외부 노출 없음 (테블릿 키오스크 모드)

## 기술 스택

- HTML / CSS / Vanilla JavaScript (단일 페이지)
- PWA (manifest + service worker)
- 배포: Vercel
- 백엔드: Google Sheets + Apps Script (예정)
- 호스팅: 무료 (Vercel hobby tier)
