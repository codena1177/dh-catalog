# 디지털헬스 카탈로그 — GitHub Pages 배포 가이드

## 📁 폴더 구조

```
dh-catalog/
├── index.html          ← 메인 앱 (이게 전부)
├── data/
│   └── products.json   ← 제품 기본 데이터
└── assets/
    ├── images/         ← 제품 사진 (선택, 앱 내 업로드로 대체 가능)
    └── reports/        ← PDF 샘플 (선택, 앱 내 업로드로 대체 가능)
```

---

## 🚀 배포 방법 (처음 한 번만)

### 1단계 — GitHub 계정 만들기
- https://github.com 접속 → Sign up
- 계정명 예: `daewoong-dh`

### 2단계 — 새 저장소(Repository) 만들기
1. GitHub 로그인 후 우상단 `+` → `New repository`
2. Repository name: `dh-catalog`
3. **Public** 선택 (Pages 무료 사용 조건)
4. `Create repository` 클릭

### 3단계 — 파일 올리기
1. 새 저장소 페이지에서 `uploading an existing file` 클릭
2. `index.html`, `data/` 폴더, `assets/` 폴더를 드래그하여 업로드
3. `Commit changes` 클릭

### 4단계 — GitHub Pages 활성화
1. 저장소 → `Settings` → 좌측 메뉴 `Pages`
2. Source: `Deploy from a branch`
3. Branch: `main` / `/ (root)` 선택 → `Save`
4. 1~2분 후 URL 생성: `https://daewoong-dh.github.io/dh-catalog`

---

## 📱 팀원 공유 방법

생성된 URL을 팀 카톡/슬랙에 공유하면 끝.
- 별도 설치 없이 브라우저에서 바로 사용
- 모바일에서도 동작

---

## 💾 데이터 저장 방식

| 항목 | 저장 위치 | 특징 |
|------|-----------|------|
| 제품명/설명/병원 등 텍스트 | 각 PC 로컬스토리지 | 편집 후 즉시 저장 |
| 제품 사진 (업로드) | 각 PC 로컬스토리지 | base64 변환 저장 |
| 레포트 PDF (업로드) | 각 PC 로컬스토리지 | base64 변환 저장 (10MB 이하) |

> **주의**: 로컬스토리지는 브라우저/PC별 독립 저장입니다.
> 팀원 전체 동기화가 필요하면 → `data/products.json` 수정 후 GitHub에 재업로드
> (팀원들이 새로 접속하면 자동 반영)

---

## ✏️ 제품 정보 업데이트 방법

### 방법 A — 앱에서 직접 편집 (개인 PC용)
앱 접속 → `편집` 탭 → 수정 → 저장 버튼

### 방법 B — JSON 파일 수정 (전체 동기화용)
1. `data/products.json` 파일을 텍스트 에디터로 열기
2. 내용 수정 (제품명, 병원 등)
3. GitHub에 파일 재업로드 (기존 파일 덮어쓰기)
4. 팀원들이 새로고침하면 자동 반영

---

## 🔗 제품 선택 후 링크 공유

1. 앱에서 원하는 제품 선택
2. 우상단 `링크 공유` 버튼 클릭
3. 자동으로 `?sel=1,3,5` 형태 URL 복사됨
4. 해당 링크 열면 선택된 제품만 바로 보임

---

## 📄 PDF 출력

1. 원하는 제품 선택
2. `선택 미리보기` 탭
3. `PDF 저장` 버튼 → 브라우저 인쇄 다이얼로그 → `PDF로 저장`
