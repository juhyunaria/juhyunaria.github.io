---
title: "모던 자바스크립트 Deep Dive – Chapter 08 제어문"
date: "2025-09-22"
tags: ["javascript", "deep-dive", "control-flow", "if", "for", "while", "switch"]
summary: "조건문과 반복문, break/continue, 제어문 사용법과 특징 정리"
draft: false
---

# 모던 자바스크립트 Deep Dive – Chapter 08 제어문

## 날짜
2025-09-23 (Tue)

## 주제
조건문과 반복문, break/continue, 제어문 특징과 주의사항

---

## 학습 내용 (개념 정리)

### 8.1 제어문 개요
- 제어문(control statement): 코드 실행 흐름을 제어하는 문  
- 조건에 따라 분기하거나 반복을 수행하는 구조  

---

### 8.2 블록문 (Block Statement)
- 블록문: 0개 이상의 문을 `{}`로 묶은 것  
- 단독으로도 사용 가능, 일반적으로 제어문이나 함수 정의에 사용  

```js 
  { let x = 10; console.log(x); } 
```

---

### 8.3 조건문 (Conditional Statement)

#### if문
- 조건식이 true일 때 코드 블록 실행  

```js 
  let x = 10; 
  if (x > 5) { 
    console.log("x는 5보다 큽니다"); 
  } 
```

#### if...else문
- 조건식이 false일 경우 실행할 블록 지정  

```js 
  let age = 20; 
  if (age >= 18) { 
    console.log("성인"); 
  } else { 
    console.log("미성년자");
  } 
```

#### else if문
- 여러 조건 분기 가능  

```js 
let score = 85; 
if (score >= 90) { 
  console.log("A"); 
  } else if (score >= 80) { 
    console.log("B"); 
  } else { 
      console.log("C 이하"); 
  } 
```

#### switch문
- 표현식을 평가해 case 절과 일치하는 값 실행  

```js 
let fruit = "apple"; switch (fruit) { 
  case "apple": console.log("사과"); 
  break; 
  case "banana": console.log("바나나"); 
  break; 
  default: console.log("기타 과일"); 
}; 
```

- 일치 비교(`===`)로 동작  
- break 없으면 다음 case까지 실행됨 (fall-through 현상)  

---

### 8.4 반복문 (Loop Statement)

#### for문
- 반복 횟수가 명확할 때 사용  

```js 
  for (let i = 0; i < 3; i++) { console.log(i); } 
```

#### while문
- 조건이 true인 동안 반복  

```js 
  let n = 0; while (n < 3) { console.log(n); n++; } 
```

#### do...while문
- 조건을 나중에 평가 → 최소 한 번은 실행  

```js 
  let i = 0; do { console.log(i); i++; } while (i < 3); 
```

---

### 8.5 break문
- 가장 가까운 반복문이나 switch문을 즉시 종료  

```js 
  for (let i = 0; i < 5; i++) { if (i === 3) break; console.log(i); } // 0,1,2 
```

---

### 8.6 continue문
- 반복문의 현재 실행만 건너뛰고, 다음 반복으로 진행  

```js 
for (let i = 0; i < 5; i++) { if (i === 2) continue; console.log(i); } // 0,1,3,4 
```

---

## 주요 포인트 / 세부 내용
1. 제어문은 실행 흐름을 조건과 반복으로 제어한다  
2. if, switch는 조건 분기에서 상황에 맞게 선택한다  
3. 반복문은 for(명확한 반복), while/do...while(조건 기반 반복)로 구분해 사용한다  
4. break는 반복이나 switch를 강제 종료하고, continue는 특정 반복만 건너뛴다  
5. switch문에서 break를 빠뜨리면 fall-through 발생하므로 주의해야 한다  
