---
title: "모던 자바스크립트 Deep Dive – Chapter 03 자바스크립트 개발 환경과 실행 방법 (Mac 기준)"
date: "2025-09-22"
tags: ["javascript", "deep-dive", "execution-environment", "nodejs", "browser"]
summary: "브라우저와 Node.js에서 자바스크립트 실행 방법, 개발 도구와 실행 흐름 요약"
draft: false
---

# 모던 자바스크립트 Deep Dive – Chapter 03 자바스크립트 개발 환경과 실행 방법 (Mac 기준)

## 날짜
2025-09-22 (Mon)

## 주제
브라우저와 Node.js 실행 환경, 개발 도구, 실행 흐름 요약

---

## 학습 내용 (개념 정리)

- **실행 환경**
  - 브라우저: 화면 제어, 이벤트 처리, 네트워크 요청에 활용
  - Node.js: 브라우저 밖 실행, 서버/파일 관리/CLI 제작 가능

- **브라우저에서 실행하기 (Mac)**
  1. HTML 파일 작성  
  ```html 
    <!DOCTYPE html>
    <html>
        <body>
          <h1>Hello JavaScript</h1>
            <script>
              console.log("Hello from JS!");
            </script>
        </body>
    </html> 
  ```
  2. Finder에서 파일 더블클릭 → 브라우저 실행  
  3. 개발자 도구 열기 (Command + Option + I → Console 확인)  
  4. 외부 파일 불러오기:  
     ```html <script src="app.js"></script> ```

- **Node.js에서 실행하기 (Mac)**
  - 설치 (공식 사이트 LTS 버전 or Homebrew)  
    ```bash brew install node ```
  - 설치 확인  
    ```bash node -v ```  
    ```bash npm -v ```
  - JS 파일 실행  
    ```bash node app.js ```
  - app.js 내용  
    ```js console.log("Hello Node.js!"); ```

- **개발 도구 및 디버깅**
  - **브라우저 개발자 도구 (Mac 단축키: Command + Option + I)**
    - Console: `console.log()` 출력 확인, 에러 메시지 확인
    - Elements: HTML/CSS 구조 확인 및 실시간 수정
    - Network: 요청/응답 상태 분석
    - Sources: JS 코드 디버깅, **중단점(breakpoint)** 설정 후 실행 흐름 단계별 추적
  - **Node.js 디버깅**
    - `node inspect app.js` → CLI 디버깅
    - VS Code → 내장 Debugger 탭에서 중단점 설정 후 실행 가능
  - **디버깅 핵심**
    - 단순 로그(console.log) → 빠른 확인
    - 중단점(breakpoint) → 코드 흐름 제어 및 변수 값 추적
    - Network 탭 → API 요청/응답 문제 확인  

- **코드 에디터**
  - Visual Studio Code 권장
  - 터미널에서 `code .` 명령어로 프로젝트 열기 가능 (PATH 설정 필요)

- **실행 흐름 요약**
  1. 코드 작성 (app.js)
  2. 실행 환경 선택 (브라우저 vs Node.js)
  3. 브라우저 → Console & Sources 탭 디버깅
  4. Node.js → `node app.js` 실행 + VS Code Debugger 활용
  5. 결과는 브라우저 화면 또는 터미널 출력

---

## 주요 포인트 / 세부 내용
1. 자바스크립트 실행 환경은 브라우저와 Node.js 두 가지다.  
2. **디버깅은 Console.log 확인에서 시작 → Breakpoint 활용으로 확장해야 한다.**  
3. 브라우저 개발자 도구의 Console, Sources, Network 탭은 반드시 익혀야 한다.  
4. Node.js는 CLI 디버깅과 VS Code Debugger로 보완 가능하다.  

---

## 코드/실습 예시
```bash 
node -v 
```  
```bash 
npm -v 
```  
```bash 
node app.js 
```  
```js 
console.log("Hello Node.js!"); 
```

---

## 배운 점 & 인사이트
- 디버깅은 단순 로그 출력에서 멈추지 않고, 중단점 활용과 실행 흐름 분석으로 확장해야 한다.  
- 브라우저 개발자 도구는 프론트엔드 개발자의 필수 무기다.  
- Node.js 환경에서는 CLI + VS Code 디버깅을 익혀야 한다.  
- 실행 환경과 디버깅 도구를 자유롭게 오가며 사용하는 능력이 곧 개발 생산성이다.  

---

## 다음 학습 계획
- Chapter 04 변수 학습