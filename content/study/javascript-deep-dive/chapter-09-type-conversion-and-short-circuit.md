---
title: "모던 자바스크립트 Deep Dive – Chapter 09 타입 변환과 단축 평가"
date: "2025-09-22"
tags: ["javascript", "deep-dive", "type-conversion", "coercion", "short-circuit"]
summary: "명시적/암묵적 타입 변환, Truthy/Falsy, 단축 평가와 옵셔널 체이닝/Null 병합 연산자 정리"
draft: false
---

# 모던 자바스크립트 Deep Dive – Chapter 09 타입 변환과 단축 평가

## 날짜
2025-09-23 (Tue)

## 주제
명시적/암묵적 타입 변환, Truthy/Falsy, 단축 평가, 옵셔널 체이닝, Null 병합 연산자

---

## 학습 내용 (개념 정리)

### 9.1 타입 변환 개요
- 타입 변환(Type Conversion): 기존 값을 다른 타입으로 바꾸는 것  
- 명시적 변환: 개발자가 의도적으로 변환  
- 암묵적 변환(타입 강제 변환, Coercion): 엔진이 자동으로 변환  

---

### 9.2 명시적 타입 변환 (Explicit Conversion)
- 문자열 변환  
```js 
  String(1); // "1"  (1).toString(); // "1" 
```  
- 숫자 변환  
```js 
  Number("10"); // 10 parseInt("10"); // 10 
```  
- 불리언 변환  
```js 
  Boolean("x"); // true Boolean(""); // false 
```

---

### 9.3 암묵적 타입 변환 (Implicit Conversion)
- 자바스크립트 엔진이 상황에 따라 자동 변환  
```js 
  1 + "2"; // "12" (숫자 → 문자열)  
  "5" * 2; // 10 (문자열 → 숫자)  
  !0; // true (숫자 → 불리언) 
```

---

### 9.4 Truthy와 Falsy
- 조건문에서 암묵적 불리언 변환 발생  
- Falsy 값: `false`, `0`, `-0`, `NaN`, `""`, `null`, `undefined`  
- Truthy 값: Falsy 이외 모든 값  

```js 
  if ("hello") { console.log("Truthy"); } 
```

---

### 9.5 단축 평가 (Short-circuit Evaluation)
- 논리 연산자의 평가 결과를 이용해 불필요한 연산 생략  

```js 
  true || "값"; // true  
  false || "값"; // "값"   
  true && "값"; // "값"   
  false && "값"; // false 
```

- 활용 예  
  - 기본값 설정: `let n = input || 0;`  
  - 조건부 실행: `isLoggedIn && doSomething();`  

---

### 9.6 옵셔널 체이닝 연산자 (?.)
- 좌항이 `null` 또는 `undefined`일 때 에러 대신 `undefined` 반환  

```js 
  let user = null; console.log(user?.name); // undefined 
```

---

### 9.7 Null 병합 연산자 (??)
- 좌항이 `null` 또는 `undefined`일 때만 우항 반환  

```js 
  let foo = null ?? "기본값"; // "기본값"  
  let bar = 0 ?? 42; // 0 (0은 falsy지만 null/undefined 아님) 
```

---

## 주요 포인트 / 세부 내용
1. 타입 변환은 명시적과 암묵적으로 나뉜다  
2. 암묵적 변환은 편리하지만 예측 불가 상황을 만들 수 있어 주의 필요  
3. Truthy/Falsy 개념은 조건문 평가의 핵심이다  
4. 단축 평가는 조건부 실행과 기본값 설정에서 많이 활용된다  
5. 옵셔널 체이닝(`?.`)과 Null 병합(`??`)은 안전한 프로퍼티 접근과 기본값 지정에 유용하다  
