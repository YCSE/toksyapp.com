# Toksy Landing Page

워드프레스 기반 웹사이트를 GitHub Pages로 마이그레이션한 정적 사이트입니다.

## 프로젝트 구조

```
/
├── index.html              # 언어 감지 및 리다이렉트
├── CNAME                   # 커스텀 도메인 설정
├── ko/
│   └── index.html         # 한국어 페이지
├── en/
│   └── index.html         # 영어 페이지
├── jp/
│   └── index.html         # 일본어 페이지
└── assets/
    ├── css/
    │   └── style.css      # 공통 스타일시트
    └── images/
        ├── ko/            # 한국어 이미지
        ├── en/            # 영어 이미지
        └── jp/            # 일본어 이미지
```

## 언어 감지 로직

루트 페이지(`index.html`)는 브라우저의 언어 설정을 자동으로 감지하여 적절한 언어 페이지로 리다이렉트합니다:

- **한국어** (`ko`): `/ko/`로 리다이렉트
- **일본어** (`ja`): `/jp/`로 리다이렉트
- **기타 언어**: `/en/`로 리다이렉트 (기본값)

## 배포 방법

### GitHub Pages 설정

1. GitHub에 새 리포지토리 생성
2. 로컬 파일을 GitHub에 푸시:

```bash
git init
git add .
git commit -m "Initial commit: WordPress to GitHub Pages migration"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

3. GitHub 리포지토리 설정에서 Pages 활성화:
   - Settings → Pages
   - Source: Deploy from a branch
   - Branch: `main` / `root`
   - Save

### 커스텀 도메인 설정

1. GitHub Pages 설정에서 Custom domain에 `toksyapp.com` 입력
2. DNS 설정에서 A 레코드 추가:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
3. CNAME 레코드 추가 (www 서브도메인):
   ```
   www.toksyapp.com → YOUR_USERNAME.github.io
   ```

## 로컬 테스트

로컬에서 테스트하려면 간단한 HTTP 서버를 실행하세요:

```bash
# Python 3
python3 -m http.server 8000

# 브라우저에서 http://localhost:8000 접속
```

## 기능

- ✅ 브라우저 언어 자동 감지
- ✅ 3개 언어 지원 (한국어, 영어, 일본어)
- ✅ 반응형 디자인 (모바일/태블릿/데스크톱)
- ✅ SEO 최적화 (메타 태그, 시맨틱 HTML)
- ✅ Google Analytics 통합
- ✅ App Store 링크 연동

## 유지보수

### 콘텐츠 수정

각 언어별 페이지를 직접 수정:
- 한국어: `ko/index.html`
- 영어: `en/index.html`
- 일본어: `jp/index.html`

### 스타일 수정

공통 스타일시트 수정: `assets/css/style.css`

### 이미지 추가/교체

각 언어별 이미지 디렉토리에서 관리:
- `assets/images/ko/`
- `assets/images/en/`
- `assets/images/jp/`

## 라이선스

© 2024 TOKSY. ALL RIGHTS RESERVED.
