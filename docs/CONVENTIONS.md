# 프로젝트 컨벤션

## Git

- 브랜치: main(배포), feat/_, fix/_, refactor/_, chore/_
- 커밋: Conventional Commits
  - 예) `feat(til): add 2025-09-21 map vs foreach`

## 폴더

root/
├── .gitignore
├── .prettierrc
├── eslint.config.js
├── package.json
├── tsconfig.json
├── public/
│ └── assets/ # 정적 파일 (images, fonts, icons)
├── src/
│ ├── app/ # Next.js App Router (page.tsx, layout.tsx)
│ ├── components/ # UI 컴포넌트 (atoms, molecules, organisms)
│ ├── hooks/ # 커스텀 훅
│ ├── store/ # Zustand 전역 상태
│ ├── styles/ # 글로벌 스타일, 모듈 CSS
│ ├── utils/ # 공통 함수, api, constants
│ └── tests/ # 유닛/통합 테스트
├── content/
│ ├── til/ # 매일 기록 (Today I Learned)
│ ├── study/ # 스터디/강의 정리
│ └── projects/ # 프로젝트 회고/문서
└── docs/
└── CONVENTIONS.md # 프로젝트 컨벤션 문서

## 네이밍

- 컴포넌트: PascalCase (`ProjectCard.tsx`)
- 훅: useXxx (`useTheme.ts`)
- 변수/함수: camelCase
- 상수: UPPER_SNAKE_CASE
- 파일/폴더: kebab-case

## 상태관리

- **클라이언트 상태**: Zustand
- **서버 상태**: TanStack Query (필요 시)

## 스타일 & 접근성

- TailwindCSS **우선 사용**
- 필요 시 CSS Module 혼용
- 접근성:
  - `focus-visible` 적용
  - `aria-*` 속성 활용
  - 색 대비 **WCAG AA 이상**

## 환경 변수

- `.env*` 파일 **커밋 금지**
- 대신 `.env.example`로 예시 제공
