# 📦 깃허브 업로드 체크리스트

이 폴더 안의 **모든 파일**을 깃허브 저장소에 올리면 됩니다.

## 업로드해야 할 파일 (총 10개)

```
viaelite-tablet-display/
├── 📄 index.html           ← 메인 디스플레이 (필수)
├── 📄 manifest.json        ← PWA 설정 (필수)
├── 📄 sw.js                ← 오프라인 캐시 (필수)
├── 📄 vercel.json          ← Vercel 배포 헤더 설정 (권장)
├── 📄 README.md            ← 저장소 설명 (권장)
├── 📄 UPLOAD.md            ← 이 파일 (선택)
├── 📄 .gitignore           ← 깃 무시 파일 (필수)
└── 📁 icons/               ← PWA 아이콘 4개 (필수)
    ├── 🖼 icon-192.png
    ├── 🖼 icon-512.png
    ├── 🖼 apple-touch-icon.png
    └── 🖼 favicon.png
```

## 업로드 절차 (3단계, 약 5분)

### 1️⃣ 깃허브 저장소 만들기

1. [github.com](https://github.com) 로그인
2. 우상단 ➕ → **New repository**
3. 설정:
   - Repository name: `viaelite-tablet-display`
   - **Private** 선택 (중요)
   - Add a README file: **체크 해제** (이미 있음)
   - Add .gitignore: **None** (이미 있음)
4. **Create repository**

### 2️⃣ 파일 업로드

1. 새로 만들어진 저장소 화면에서 **"uploading an existing file"** 링크 클릭
2. 파일 탐색기에서 이 폴더(`viaelite-tablet-display/`)를 열고
3. **모든 파일과 `icons/` 폴더**를 한꺼번에 드래그&드롭으로 업로드
4. 아래 "Commit changes" 클릭

### 3️⃣ Vercel 배포

1. [vercel.com](https://vercel.com) 로그인
2. **Add New → Project**
3. GitHub에서 방금 만든 `viaelite-tablet-display` 선택 → **Import**
4. 설정 변경 없이 **Deploy** 클릭
5. 30초 후 임시 URL이 표시됨 (예: viaelite-tablet-display.vercel.app)
6. 그 URL로 접속해서 작동 확인

### 4️⃣ 도메인 연결 (display.viaelite.kr)

1. Vercel 프로젝트 → **Settings → Domains**
2. `display.viaelite.kr` 입력 → **Add**
3. 가비아 DNS 설정:
   - **viaelite.kr 관리 → DNS 정보 → DNS 설정 → 레코드 추가**
   - 타입: **CNAME**
   - 호스트: **display**
   - 값/위치: **cname.vercel-dns.com.** (끝에 점 포함)
   - 저장
4. 5분~1시간 대기 → Vercel에서 ✓ Valid 표시되면 완료
5. `https://display.viaelite.kr` 접속해서 작동 확인

## 현재 상태

⚠ **데모 모드** — 아무 ID/비밀번호 입력하면 통과. 백엔드(Apps Script)는 아직 미연결.

다음 단계로 백엔드를 연결하면 진짜 매장 계정으로 로그인됩니다.

## 도움이 필요할 때

각 단계에서 막히면:
1. 어느 단계에서 막혔는지 (1, 2, 3, 4 중)
2. 어떤 화면이 보이는지 (스크린샷)

알려주시면 바로 도와드립니다.
