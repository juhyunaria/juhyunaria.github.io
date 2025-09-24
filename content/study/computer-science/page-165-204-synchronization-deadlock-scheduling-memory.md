---
title: "2025-09-23 동기화·교착상태·스케줄링·메모리 관리/이것이 취업을 위한 컴퓨터 과학이다"
date: "2025-09-23 22:00"
tags: ["cs", "synchronization", "deadlock", "scheduling", "memory", "study"]
summary: "운영체제에서의 동기화, 교착 상태, CPU 스케줄링 기법, 메모리 관리"
draft: false
---

# 동기화 (Synchronization)

### 개념
멀티스레드 환경에서 공유 자원을 동시에 접근하면 **경쟁 조건(Race Condition)**이 발생.  
이를 방지하기 위해 임계 구역(Critical Section)을 보호해야 함.  

### 예시
은행 계좌 `balance`를 두 스레드가 동시에 출금 → 최종 잔액 오류 발생 가능.  

### 코드
```java
synchronized void withdraw(int amount) {
    if(balance >= amount) {
        balance -= amount;
    }
```
![critical-section](./images/critical-section.png)

## 교착 상태 (Deadlock)
### 개념
두 프로세스가 서로 자원을 점유한 채 상대방의 자원을 기다리면서 무한 대기하는 상태.

### 예시
프로세스 A: 프린터 점유, 스캐너 요청

프로세스 B: 스캐너 점유, 프린터 요청
→ 두 프로세스 모두 진행 불가.

### 조건
상호 배제, 점유 대기, 비선점, 환형 대기.

![deadlock](./images/deadlock.png)

## CPU 스케줄링
### 개념
Ready Queue에 있는 프로세스 중 어떤 순서로 CPU를 할당할지 결정하는 알고리즘.

### 예시
FCFS: A(5s), B(2s) → B가 길게 대기.

RR(Time Quantum=2): A와 B가 번갈아 실행 → 응답성 ↑.

![scheduling](./images/scheduling.png)

## 메모리 관리 (가상 메모리 전까지)
### 개념
프로그램 실행을 위해 메모리를 어떻게 나누어 할당할지 결정.

### 예시
Fixed Partition: 25KB 공간에 10KB 프로그램 실행 → 내부 단편화 15KB 발생.

Paging: 논리 페이지 10개 ↔ 물리 프레임 매핑 → 외부 단편화 해결.

![paging](./images/paging.png)


## 세그멘테이션 (Segmentation)

### 개념
메모리를 **의미 단위(세그먼트)**로 나누는 방식.  
- 세그먼트: 코드(Code), 데이터(Data), 스택(Stack) 등 논리적 단위.  
- 프로세스는 세그먼트 번호 + 오프셋(offset)으로 접근.  
- 사용자 관점에 적합 (논리 구조 그대로 반영).  

### 예시
프로그램 실행 시  
- Code: 20KB  
- Data: 15KB  
- Stack: 10KB  
→ 각 세그먼트를 필요 크기만큼 따로 배치.  

단점: 세그먼트 크기가 달라서 **외부 단편화** 발생 가능.  

### 그림
![segmentation](./images/segmentation.png)