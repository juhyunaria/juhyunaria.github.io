---
title: "Next.js GitHub Pages 배포 리뷰 & 브랜치 전략"
date: "2025-09-21"
tags: ["til", "nextjs", "github-pages", "git", "roadmap"]
summary: "Next.js GitHub Pages 배포를 복기하고 브랜치 전략 및 프론트→풀스택 로드맵 고민"
draft: false
---

### 오늘 한 것
- 어제 진행한 **Next.js GitHub Pages 배포 과정** 복기
- GitHub Actions 배포 파이프라인 점검
- Git Flow 전략(main vs develop) 리서치
- 포트폴리오 진행 방향(프론트엔드 중심 → 백엔드 확장) 정리

### 배운 점
- **Next.js GitHub Pages 배포 과정 리뷰**
  - `next.config.js`에 `basePath: "/juhyunaria.github.io"`와 `output: "export"` 설정 필요
  - `next export`로 정적 사이트 빌드 후 `out/` 폴더가 Pages에 올라감
  - `.github/workflows/deploy.yml`에서 `actions/checkout@v3` → `actions/setup-node@v3` → `npm run build && npm run export` → `actions/upload-pages-artifact` → `actions/deploy-pages` 단계로 배포 자동화
  - 어제 배포 성공 후 `https://juhyunaria.github.io/`에서 기본 앱 페이지 확인 완료

- **Git Flow 브랜치 전략 (리서치)**
  - 협업 프로젝트:  
    - `main`: 항상 배포 가능한 안정 버전  
    - `develop`: 개발용 브랜치, 여기서 `feat/*`, `fix/*` 분기  
    - PR을 통해 develop → main 병합  
  - 개인 프로젝트(포트폴리오):  
    - 단일 `main` 브랜치만으로도 충분  
    - 하지만 Git Flow 패턴을 학습 목적으로 적용하면 나중에 협업 적응이 빠름  
  - 결론: 지금은 `main` 단일로 진행, 백엔드 붙일 때 `develop` 도입 고려

- **프로젝트 방향 & 로드맵**
  - 초기: 프론트엔드 중심 블로그 → `content/til`, `content/study`, `content/projects` 폴더 구조 확립  
  - 확장: 간단한 백엔드 기능 추가 (댓글, 조회수, 좋아요 카운트)  
  - 장점: 빠른 결과물 확보 후 점진적 확장 → 유지보수 부담 ↓, 포트폴리오 단계별 완성도 ↑  

- **프로젝트 컨벤션 (재정리)**
  - 브랜치: `main`, 필요 시 `develop`, `feat/*`, `fix/*`, `refactor/*`, `chore/*`
  - 커밋: Conventional Commits (예: `feat(til): add 2025-09-21 branch strategy review`)
  - 네이밍: 파일/폴더 `kebab-case`, 컴포넌트 `PascalCase`
  - 배포: GitHub Pages (정적 사이트, Actions 자동화)
  - 스타일 & 접근성: Tailwind + Prettier, `focus-visible`, `aria-*`

### 내일 할 것
- [ ] `content/til` 라우트 생성 & 첫 TIL 렌더링 테스트  
- [ ] `gray-matter`, `remark` 설치 후 마크다운 파싱 실습  
- [ ] 브랜치 전략을 실제로 적용해보기 (`develop` 생성 & feature 브랜치에서 작업)
