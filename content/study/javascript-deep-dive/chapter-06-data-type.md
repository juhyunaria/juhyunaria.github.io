---
title: "모던 자바스크립트 Deep Dive – Chapter 06 데이터 타입"
date: "2025-09-22"
tags: ["javascript", "deep-dive", "data-type", "string", "symbol", "typeof"]
summary: "문자열, 템플릿 리터럴, undefined, 원시 타입과 심벌, 객체, typeof, 동적 타이핑 정리"
draft: false
---

# 모던 자바스크립트 Deep Dive – Chapter 06 데이터 타입

## 날짜
2025-09-22 (Mon)

## 주제
문자열, 템플릿 리터럴, undefined, 원시 타입과 심벌, 객체, typeof, 동적 타이핑

---

## 학습 내용 (개념 정리)

### 6.2 문자열 타입 (String)
- 문자열은 반드시 작은따옴표('), 큰따옴표("), 또는 백틱(`)으로 감싸야 한다  
- 그렇지 않으면 자바스크립트 엔진이 키워드나 식별자로 오해할 수 있다  

```js let str = hello;  // Error (hello라는 변수를 찾으려 함) ```  
```js let str = "hello"; // 정상 ```

- 일반적으로 자바스크립트 커뮤니티에서는 작은따옴표(')를 많이 사용한다  

---

### 6.3 템플릿 리터럴 (Template Literal)

#### 6.3.1 멀티라인 문자열
- 일반 문자열에서 줄바꿈 시 `\n` 같은 이스케이프 시퀀스를 사용해야 한다  
```js let str = "hello\nworld"; ```

- 템플릿 리터럴(`)에서는 줄바꿈을 직접 작성 가능, 공백도 그대로 유지된다  
```js let str = `hello
world`; ```  
```js console.log(str); // hello \n world ```

#### 6.3.2 표현식 삽입 (Expression Interpolation)
- `${ }` 안에 표현식을 넣어 문자열 안에 값을 삽입 가능  

```js let name = "주현"; let msg = `Hello, ${name}!`; // "Hello, 주현!" ```  
```js let calc = `1 + 2 = ${1 + 2}`; // "1 + 2 = 3" ```

- 문자열 연결 연산자(+)를 쓰지 않아도 된다  

---

### 6.5 undefined 타입
- undefined는 값이 “없음”을 표현하는 게 아니라, **엔진이 변수를 초기화할 때 자동 할당하는 값**  
- 개발자가 의도적으로 쓰는 값이 아님  

```js let x; console.log(x); // undefined ```

- **선언(declaration)**: 변수 이름을 엔진에 알리고 메모리 공간 확보  
```js let a; // 선언 ```
- **정의(definition)**: 선언 + 초기값 할당을 함께 하는 것  
```js let b = 10; // 선언과 정의 동시에 ```

---

### 6.7 원시 타입과 심벌
- 원시 타입: 숫자, 문자열, 불리언, null, undefined, 심벌, BigInt  
- 특징  
  - 불변(immutable)  
  - 값 자체가 메모리에 저장됨  
  - 복사 시 값이 그대로 복사 (copy by value)  

#### 심벌(Symbol)
- ES6에서 추가된 원시 타입  
- 동일한 설명 문자열을 넣어도 항상 유일한 값 생성  

```js 
let s1 = Symbol("id"); 
let s2 = Symbol("id"); 
console.log(s1 === s2); // false 
```

- 주로 객체 프로퍼티 키로 사용 → 다른 코드와 충돌 방지  

```js 
let obj = {}; 
let sym = Symbol("key"); 
obj[sym] = "secret"; 
console.log(obj[sym]); // "secret" 
```

- for...in 루프, Object.keys() 등에서는 심벌 키가 나오지 않음 (은닉성 확보)  

---

### 6.8 객체 타입 (Object)
- 원시 타입을 제외한 나머지 모두 객체  
- 배열, 함수, 정규표현식, Date, Error 등도 객체  
- 즉, 자바스크립트의 대부분은 객체  

---

### 6.10 typeof 연산자
- typeof는 피연산자의 데이터 타입을 문자열로 반환  

```js
typeof 123;        // "number"  
typeof "hello";    // "string"   
typeof true;       // "boolean"   
typeof undefined;  // "undefined"   
typeof null;       // "object" (초기 설계 버그) 
typeof Symbol();   // "symbol"   
typeof 10n;        // "bigint"   
typeof {};         // "object"   
typeof [];         // "object" (배열도 객체)   
typeof function() {}; // "function" (실제로는 객체지만 특별 취급) 
```

- **null 문제**: typeof null → "object"  
  - 실제 null은 객체가 아님, “값이 없음”을 의미하는 원시 타입  

---

### 6.10.2 동적 타이핑
- 자바스크립트는 변수 타입을 미리 고정하지 않음  
- 값이 바뀌면 타입도 런타임에 따라 변함  

```js 
let x = 10;     // numbe  
  x = "hello";   // string   
  x = true;      // boolean 
```

- 장점: 유연함  
- 단점: 타입 추적이 어려워 버그 발생 가능  

---

## 주요 포인트 / 세부 내용
1. 문자열은 반드시 따옴표로 감싸야 한다  
2. 템플릿 리터럴은 멀티라인, 표현식 삽입 기능을 제공한다  
3. undefined는 엔진의 기본 초기화 값, null은 의도적으로 “없음”을 표현하는 값이다  
4. 원시 타입은 불변이고 값이 그대로 복사된다  
5. 심벌은 유일한 값을 보장하며, 주로 객체 프로퍼티 키로 사용된다  
6. 객체는 원시 타입을 제외한 모든 값이다  
7. typeof로 타입을 확인할 수 있지만, null은 "object"라는 예외가 있다  
8. 동적 타이핑은 편리하지만 유지보수 시 버그를 유발할 수 있다  
