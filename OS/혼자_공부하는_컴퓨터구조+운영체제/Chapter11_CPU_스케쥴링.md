# DAY3
작성일 : 2024/04/02

> 범위
- 01 CPU 스케쥴링 개요
- 02 CPU 스케쥴링 알고리즘

---
> 작성자 : PCYSB

## Q. 선점형, 비선점형 CPU 스케줄링의 차이점에 대해서 애기하세요

### CPU를 뺏을수 있느냐 없느냐
   - 선점형의 경우 특정 프로세스 1개가 CPU를 사용하고 있을 때 다른 프로세스가 CPU를 빼앗을 수 있는 방법
   - 비선점형의 경우 특정 프로세스 1개가 CPU를 사용하고 있을때는 못 뺏음

### 장,단점
#### 선점형
- 비교적 응답이 빠르다는 장점, 처리 시간을 예측하기 힘들고 높은 우선순위 프로세스들이 계속 들어오는 경우 오버헤드를 초래할 수 있다.

#### 비선점형
- 모든 프로세스에 대한 요구를 공정하게 처리할 수 있지만, 짧은 작업을 수행하는 프로세스가 긴 작업 종료 시까지 대기해야할 수도 있다.
---
> 작성자 : KUN

## Q. 각자 사용하고 있는 OS의 CPU 스케줄링 알고리즘의 종류가 무엇인지 말해주세요! 예) 윈도우 10 , MAC OS 등등

### 윈도우 10 - 멀티레벨 피드백 큐 (Multilevel Feedback Queue)

- 다양한 우선 순위 레벨을 가진 여러 개의 큐를 사용

- 프로세스의 우선 순위는 실행 가능한 큐 사이에서 조정

- 각 큐에는 프로세스에 할당되는 시간 할당량이 있음


### MAC OS - 라운드 로빈 알고리즘과 Mach 스케줄러

- 그중 Mach 스케줄러는 MAC OS 에 사용된 커널이 Mach 커
널과 BSD(UNIX)커널이 결합된 하이브리드 형태이기에 사용되
었고 이 Mach 스케줄러는 다중 큐 스케줄링 알고리즘을 기반으
로 설계가 되었다고 함

### 리눅스 OS - 멀티레벨 피드백 큐 (Multilevel Feedback Queue)

- 리눅스도 버젼별로 다르지만 최신 버전에선 멀티레벨 피드백 큐를 사용한다고함 


---
