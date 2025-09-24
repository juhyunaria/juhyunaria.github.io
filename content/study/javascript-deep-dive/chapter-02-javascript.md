---
title: "모던 자바스크립트 Deep Dive – Chapter 02 자바스크립트"
date: "2025-09-22"
tags: ["javascript", "deep-dive", "ajax", "nodejs", "es6"]
summary: "자바스크립트의 발전, 엔진, Node.js, SPA, ECMAScript와 Web API, ES6 지원 현황 정리"
draft: false
---

# 모던 자바스크립트 Deep Dive – Chapter 02 자바스크립트

## 날짜
2025-09-22 (Mon)

## 주제
자바스크립트의 발전, 엔진, Node.js, SPA, ECMAScript와 Web API, ES6 지원 현황

---

## 학습 내용 (개념 정리)
- Ajax: 새로고침 없는 데이터 교환, fetch API로 대체
- jQuery: DOM 제어 단순화, 크로스 브라우징 문제 해결
- JS 엔진: V8, SpiderMonkey, JIT 최적화
- Node.js: 브라우저 밖 JS 런타임, 서버·CLI·데스크톱 앱 활용
- SPA: 단일 페이지에서 동적 전환, SEO 과제 존재
- ECMAScript vs JavaScript: 표준 사양 vs 실행 환경 + Web API
- 자바스크립트 특징: 멀티 패러다임, 빠른 진화
- ES6 지원 현황: 모던 브라우저 대부분 지원, IE 제외

---

## 주요 포인트 / 세부 내용
1. Ajax는 웹 상호작용의 혁신을 이끈 출발점이다.
2. jQuery는 JS 대중화를 견인했지만 지금은 역사적 의미가 크다.
3. JS 엔진의 JIT 컴파일러는 언어의 성능과 위상을 끌어올렸다.
4. Node.js는 풀스택 자바스크립트 시대를 열었다.
5. SPA 프레임워크는 UX 혁신과 SEO 문제를 동시에 안고 있다.
6. ECMAScript와 Web API의 구분은 학습 핵심이다.

---

## 코드/실습 예시
```js
// fetch API 예시
fetch("/api/data")
  .then(res => res.json())
  .then(data => console.log(data));

// jQuery 예시
$("#title").css("color", "red");

// Node.js (Express 서버)
const express = require("express");
const app = express();
app.get("/", (req, res) => res.send("Hello Node.js"));
app.listen(3000);
```
---

## 배운 점 & 인사이트
- 자바스크립트는 브라우저 언어에서 범용 언어로 성장했다.
- Ajax/jQuery/엔진/Node.js는 시대별 진화 단계로 연결된다.
- SPA의 한계(SEO)는 SSR/CSR 하이브리드로 보완된다.
- 표준(ECMAScript)과 실행(Web API)의 분리를 이해하는 게 중요하다.

---

## 다음 학습 계획
- Chapter 03 자바스크립트 실행 환경과 개발 환경