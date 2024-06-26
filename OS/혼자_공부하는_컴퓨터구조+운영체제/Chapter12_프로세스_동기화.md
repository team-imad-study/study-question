# DAY3
작성일 : 2024/04/02

> 범위
- 01 동기화란
- 02 동기화 기법

---

> 작성자 : NCookie

## 레이스 컨디션(race condition)이 발생하는 이유와 그로 인해 발생하는 문제 (Ch12-1)

`레이스 컨디션 (Race Condition)`은 병렬 프로그래밍에서 발생하는 문제로, 여러 프로세스 또는 스레드가 동시에 같은 자원을 수정하려고 할 때 예상치 못한 결과가 발생하는 상황이다. 이로 인해 다음과 같은 문제가 발생할 수 있다.

### 데이터 불일치 (Data Inconsistency)

여러 스레드가 동시에 같은 변수를 수정하는 경우, 변수의 값이 일관성 없이 변경될 수 있다. 예를 들어 은행 계좌 잔액을 동시에 감소시키는 경우, 잔액이 정확하지 않게 갱신될 수 있다.

### 쓰기-읽기 충돌 (Write-Read Conflict)

하나의 스레드가 데이터를 수정하는 동안 다른 스레드가 같은 데이터를 읽으려고 할 때 충돌이 발생합니다. 이로 인해 잘못된 데이터를 읽을 수 있다.

### 쓰기-쓰기 충돌 (Write-Write Conflict)

두 개 이상의 스레드가 동시에 같은 데이터를 수정하려고 할 때 충돌이 발생한다. 이로 인해 데이터가 무효화될 수 있다.

### 교착 상태 (Deadlock)

두 개 이상의 스레드가 서로의 작업이 끝나기를 기다리며 멈춰있는 상태다. 데드락이 발생하면 프로그램이 더 이상 진행되지 않는다. 교착 상태가 발생할 수 있는 조건은 다음과 같다.

1. 상호 배제

레이스 컨디션의 문제를 해결하고자 상호 배제 조건을 두어 동시에 공유 자원에 접근할 수 없도록 하여 한 자원에 한 스레드만 접근 할 수 있게 하는 것을 의미한다.

스레드가 자원을 독점적으로 사용하고 있어 다른 스레드가 자원에 접근하려고 락을 획득하기 위해 무한 대기할 수 있는 상황이 발생할 수 있다.

2. 점유 상태로 대기

공유 자원에 락을 획득하여 점유하고 있는 상태인데 다른 자원의 락을 획득하기 위해 대기하고 있는 상황을 의미한다.

조금 더 이해하기 쉽게 풀어서 말해본다면, 발생할 수 있는 상황이 여러 개의 자원을 동시에 써야하는 경우 락을 획득한 자원에 대한 처리는 끝났는데 남은 자원의 락을 다른 스레드가 가지고 해제를 하지 않아 무한정 대기하는 상태다.

또한 자신이 점유하고 있는 락도 해제를 해주어야 그 락을 획득하기 위해 대기하고 있는 다른 스레드들도 자원에 접근하여 처리를 할 수 있는데 락을 획득할 수 없어 다른 스레드 마저 무한정 대기할 수 밖에 없는 상황이 발생한다.

![Alt text](image-26.png)

3. 선점 불가

다른 스레드가 자원을 선점하고 있어서 자원을 뺏어올 방법이 없는 것을 의미한다. 만일 어느 스레드가 공유 자원의 락을 획득하여 선점하고 있다면 그 공유 자원에 접근해야 하는 다른 스레드들은 아무리 잠깐 처리하면 끝나는 상황이라도 락을 빼앗을 방법이 없기 때문에 무한 대기할 상황이 발생할 수 있다.

4. 순환성 대기

프로세스가 어느 자원을 점유하고 있고 다른 자원을 요청하여 대기하고 있는데 순환적인 구조를 가지는 경우를 순환성 대기라고 한다.

즉, `점유 상태로 대기`가 순환적으로 발생한 상황으로 볼 수 있다. 락을 해제하고 락을 획득하는게 순차적으로 잘 돌아가면 좋겠지만, 어느 순간 모든 프로세스가 락을 획득하려고 대기하여 모든 프로세스가 무한 대기에 놓인 상황이 발생할 수 있다.

![Alt text](image-27.png)

### 레이스 컨디션 공격

리눅스 환경에서 레이스 컨디션 상태를 이용해 root 권한을 얻어내는 공격 방식이다. 

사용자가 프로그램을 실행했을 때 SETUID를 통한 권한 상승으로 관리자 권한의 임시 파일이 생성된다. 공격자는 이 *임시 파일의 이름을 파악해놓고*, 임시 파일이 생성되면 이 파일의 심볼릭 링크를 생성한다. 

다음 프로그램 실행 시 기존의 임시 파일이 삭제되고 재생성되면 공격자는 심볼릭 링크를 이용해 파일의 내용을 변경한다. 이후 시스템은 변경된 파일을 자신이 생성한 임시 파일이라 인식해 프로세스를 진행시키고, 공격자는 관리자 권한으로 실행되는 프로그램에서 자신이 원하는 동작을 실행할 수 있게 된다.

이를 위한 필요조건은 다음과 같다.
1. 공격자는 생성되는 임시 파일의 이름을 사전에 알고 있어야 한다.
2. 파일의 소유자가 root이며 SETUID 비트를 가져야 한다.

## 참고

- [[OS] 스레드 동기화 문제](https://cheetile.tistory.com/entry/OS-%EC%8A%A4%EB%A0%88%EB%93%9C-%EB%8F%99%EA%B8%B0%ED%99%94-%EB%AC%B8%EC%A0%9C-Race-Condition-Deadlock-Starvation-Livelock)
- [레이스 컨디션 그게 뭐야?](https://velog.io/@maketheworldwise/%EB%A0%88%EC%9D%B4%EC%8A%A4-%EC%BB%A8%EB%94%94%EC%85%98-%EA%B7%B8%EA%B2%8C-%EB%AD%90%EC%95%BC#%EC%9E%84%EA%B3%84-%EC%98%81%EC%97%AD)
- [[시스템해킹] 레이스 컨디션 공격 기법 (Race Condition)](https://m.blog.naver.com/kky564/80188027120)
- [레이스 컨디션(Race Condition) 공격](https://angangmoddi.tistory.com/130)

---
> 작성자 : Quarang

## Q. Semaphore란 무엇이고, 주된 기능이 뭔지 설명하시오.

#### 정의 
- 정수 변수로서, 멀티 프로그래밍 환경에서 `공유자원에 대한 접근을 제한하는 방법`으로 사용됨
- 스레드가 `공유 자원의 배타적인 사용을 보장받기 위해` 임계구역에 출입할때 세마포어 같은 동기화 매커니즘이 사용됨


## Q. - 01 아래 링크의 코드를 해석해보시오
[[예제]](/예제%20코드/semaphore01.playground/Contents.swift)

- 해답은 문제와 함께

---
