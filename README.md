# juhyunaria.github.io
포트폴리오 & TIL 사이트 (Next.js + Tailwind).  
그래픽 디자이너 & 마케터 백그라운드를 바탕으로 **디자인 완성도 + 개발 학습 기록**을 함께 보여줍니다.

## Live
- (추후) https://juhyunaria.github.io 또는 Vercel 커스텀 도메인

## Tech Stack
- **Framework**: Next.js (App Router)
- **Lang/Types**: JavaScript (→ TypeScript 도입 예정)
- **UI**: Tailwind CSS
- **State**: Zustand
- **Deploy**: Vercel
- **Content**: Markdown(.md) in `content/`

## Project Structure
```plaintext
root/
├── public/ # 정적 파일 (images, fonts, icons)
├── src/
│ ├── app/ # Next.js App Router (page.tsx, layout.tsx)
│ ├── components/ # UI 컴포넌트 (atoms, molecules, organisms)
│ ├── hooks/ # 커스텀 훅
│ ├── store/ # Zustand 전역 상태
│ ├── styles/ # 글로벌 & 모듈 CSS
│ ├── utils/ # 공통 함수, api, constants
│ └── tests/ # 유닛/통합 테스트
├── content/
│ ├── til/ # 매일 기록 (Today I Learned)
│ ├── study/ # 스터디/강의 정리
│ └── projects/ # 프로젝트 회고/문서
└── docs/
└── CONVENTIONS.md # 프로젝트 컨벤션 문서
```

## Content 규칙
- 파일명: `YYYY-MM-DD-keyword.md` (소문자-하이픈)
- Frontmatter: `title, date, tags, summary, draft, cover`

예시
```markdown
---
title: 'map vs forEach'
date: '2025-09-21'
tags: ['til', 'javascript']
summary: 'map은 배열을 리턴, forEach는 undefined'
draft: false
cover: '📝'
---

핵심 메모 ...
```

## Conventions
- 브랜치: main, feat/_, fix/_, refactor/_, chore/_
- 커밋: Conventional Commits
- 자세한 규칙: docs/CONVENTIONS.md

## Getting Started
```bash
npm install
npm run dev
# http://localhost:3000
```

## Deploy
- GitHub → Vercel 연결 후 main 푸시 시 자동 배포

## Roadmap
- [ ] /til 목록/상세 페이지 연결 (gray-matter, remark)
- [ ] Study/Projects 섹션 연결
- [ ] 다크모드 & 접근성 개선
- [ ] 컨텐츠 검색/태그 페이지
