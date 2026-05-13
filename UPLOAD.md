# 📦 깃허브 업로드 체크리스트

이 폴더 안의 **모든 파일**을 깃허브 저장소에 올리면 됩니다.

## 업로드해야 할 파일 (총 11개)

```
viaelite-display-admin/
├── 📄 index.html           ← 어드민 메인 (필수)
├── 📄 manifest.json        ← PWA 설정 (필수)
├── 📄 sw.js                ← Service Worker (필수)
├── 📄 vercel.json          ← Vercel 설정 (권장)
├── 📄 README.md            ← 저장소 설명 (권장)
├── 📄 UPLOAD.md            ← 이 파일 (선택)
├── 📄 .gitignore           ← 깃 무시 (필수)
└── 📁 icons/               ← PWA 아이콘 (필수)
    ├── 🖼 icon-192.png
    ├── 🖼 icon-512.png
    ├── 🖼 apple-touch-icon.png
    └── 🖼 favicon.png
```

## 업로드 절차 (5분)

### 1️⃣ 깃허브 저장소 만들기
- github.com → New repository
- 이름: `viaelite-display-admin`
- **Private** 선택
- Create repository

### 2️⃣ 파일 업로드
- "uploading an existing file" 클릭
- 이 폴더 안의 모든 파일·icons 폴더 통째로 드래그&드롭
- Commit changes

### 3️⃣ Vercel 배포
- vercel.com → Add New → Project
- 방금 만든 저장소 import
- 설정 변경 없이 Deploy

### 4️⃣ 도메인 연결 (admin.viaelite.kr)
- Vercel → Settings → Domains → `admin.viaelite.kr` 추가
- 가비아 DNS 설정:
  - 타입: **CNAME**
  - 호스트: **admin**
  - 값: **cname.vercel-dns.com.**
- 5분~1시간 후 ✓ Valid Configuration 확인

## 현재 상태

⚠ **데모 모드** — 백엔드 연결 전이라 슬라이드 등록해도 시트에 저장 안 됨. 브라우저 메모리에만 저장.

다음 단계로 시트에 `슬라이드` 탭 추가하고 Apps Script에 CRUD 액션 추가하면 진짜 작동.

## 도움이 필요할 때

각 단계에서 막히면 어느 단계에서 어떻게 막혔는지 알려주세요.
