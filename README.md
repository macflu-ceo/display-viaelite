# VIA ELITE · Display Admin

비아엘리떼 매장 테블릿 디스플레이의 슬라이드를 등록·관리하는 본사 전용 어드민 콘솔입니다.

## 기능

- 슬라이드 등록 (이미지·브랜드·상품명·가격)
- 등록된 슬라이드 목록 (카드 그리드)
- 활성/비활성 토글
- 삭제
- 테블릿 화면 미리보기 링크 (display.viaelite.kr)

## 현재 상태

**v0.1 — 프론트엔드 데모 모드**
- 로그인: 아무 ID/비밀번호 통과
- 슬라이드 데이터: 브라우저 메모리에만 저장 (새로고침 시 초기화)
- 백엔드 연결 대기 중 (Apps Script URL은 코드에 이미 박혀있음)

## 다음 단계 (백엔드 연결)

- Google Sheet에 슬라이드 저장 (`슬라이드` 탭 추가)
- Apps Script에 `add_slide`, `delete_slide`, `get_slides` 액션 추가
- Google Drive에 이미지 자동 업로드
- 어드민 로그인 별도 인증 (현재는 데모)

## 폴더 구조

```
viaelite-display-admin/
├── index.html        어드민 메인
├── manifest.json     PWA 설정
├── sw.js             Service Worker
├── vercel.json       Vercel 배포 설정
├── icons/            PWA 아이콘
└── README.md
```

## 배포

### 1. GitHub 업로드
1. 새 Private 저장소: `viaelite-display-admin`
2. 모든 파일 업로드

### 2. Vercel 연결
1. vercel.com → New Project → GitHub 저장소 import → Deploy

### 3. 도메인 연결 (admin.viaelite.kr)
1. Vercel → Settings → Domains → `admin.viaelite.kr` 추가
2. 가비아 DNS:
   - Type: CNAME
   - 호스트: `admin`
   - 값: `cname.vercel-dns.com.`
3. 5분~1시간 대기

## 보안 정책

- 본사 직원 외 접근 차단 필요
- Private repo로 유지
- 향후 백엔드 연결 시 어드민 계정 별도 관리

## 도메인 (예정)

`https://admin.viaelite.kr`

## 관련 프로젝트

- [viaelite-tablet-display](../viaelite-tablet-display) — 매장 테블릿 디스플레이 (display.viaelite.kr)
- 백엔드 — Google Sheets + Apps Script (공통)
