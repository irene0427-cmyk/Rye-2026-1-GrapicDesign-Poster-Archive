# GDES 2026-1 — Poster Archive

Graphic Design 2026년 1학기 포스터 아카이빙 사이트.  
GitHub Pages로 무료 호스팅, `posters.json` 파일만 수정해서 포스터를 추가할 수 있어요.

**Live Site:** `https://[irene0427-cmyk].github.io/gdes-archive`

---

## 파일 구조

```
gdes-archive/
├── index.html       ← 사이트 본체 (건드릴 필요 없음)
├── posters.json     ← 포스터 데이터 (여기만 편집하면 됨)
└── README.md
```

---

## 포스터 추가하는 방법

### 1단계 — 이미지 공개 링크 만들기

**Google Drive 사용 시:**
1. Drive에 이미지 업로드
2. 파일 우클릭 → "공유" → "링크가 있는 모든 사용자"로 변경
3. 공유 링크에서 파일 ID 복사  
   예: `https://drive.google.com/file/d/`**`1AbCdEfGhIjK`**`/view`
4. 아래 형식으로 직접 이미지 URL 변환:  
   `https://drive.google.com/uc?export=view&id=1AbCdEfGhIjK`

**Notion 사용 시:**
1. Notion 페이지에 이미지 삽입
2. 이미지 우클릭 → "이미지 복사"로 URL 획득  
   (단, Notion 이미지 URL은 만료될 수 있어 Drive 권장)

---

### 2단계 — posters.json 편집

`posters.json` 파일을 열어 항목 추가:

```json
[
  {
    "id": 3,
    "title": "포스터 제목",
    "category": "타이포그래피",
    "assignment": "Week 7 Assignment",
    "description": "이 포스터에 대한 설명을 여기에 적어요.",
    "imageUrl": "https://drive.google.com/uc?export=view&id=YOUR_FILE_ID",
    "date": "2026-05-20"
  }
]
```

**category 선택지:** `타이포그래피` / `포스터` / `실험` / `브랜딩` / `기타`

> `id`는 기존 번호와 겹치지 않게 순서대로 올려주세요.

---

### 3단계 — GitHub에 저장

파일 저장 후 GitHub에 커밋하면 약 1분 내로 사이트에 반영됩니다.

---

## 처음 배포하는 방법 (최초 1회)

```bash
# 1. 레포 초기화
git init
git add .
git commit -m "init: GDES 2026-1 poster archive"

# 2. GitHub에 레포 생성 후 연결
git remote add origin https://github.com/[username]/gdes-archive.git
git branch -M main
git push -u origin main
```

그 다음 GitHub 레포 → Settings → Pages → Branch: `main` / `/ (root)` 선택 → Save

약 1분 후 `https://[username].github.io/gdes-archive` 에서 사이트 확인 가능.

---

## 포스터 업데이트 (이후)

```bash
git add posters.json
git commit -m "add: [포스터 제목]"
git push
```
