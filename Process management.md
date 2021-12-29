# 프로세스 관리
- 프로세스 관리는 각 프로세스 자원을 다른 프로세스로부터 보호하고 프로세스마다 작업 시간을 할당해주고 작업에 우선 순위를 매기는등의 행위로 여러 작업이 동시에 이뤄질 때 효율적으로 처리하기 위해서 프로세스를 관리하는 행위이다. 

## 목차
- 프로세스 정의
- PCB
- 프로세스 상태 전이
- 스케줄링


- ## 프로세스 정의
  - 프로세스는 일반적으로 프로세서(처리기,CPU)에 의해 처리되는 사용자 프로그램 혹은 시스템 프로그램이라고 한다. 
  - 쉽게 말해 실행중인 프로그램을 의미한다.
  - 그리고 PCB를 가진 프로그램이라고도 불린다.

- ## PCB(Process Control Block, 프로세스 제어 블록)
  - PCB는 운영체제가 프로세스에 대한 중요한 정보를 저장해 놓는 곳이다.
  - 각 프로세스가 생성될 때마다 고유의 PCB가 생성되고 프로세스가 완료되면 PCB는 제거된다.
  
  - PCB에 저장되어 있는 정보
    - 프로세스의 현재 상태
    - 포인터
    - 프로세스 고유 식별자
    - 스케줄링 및 프로세스의 우선순위
    - CPU 레지스터 정보
    - 주기억장치 과닐 정보
    - 입출력 상태 정보
    - 계정 정보
  
- ## 프로세스 상태 전이
  - 프로세스 상태 전이는 프로세스가 시스템 내에 존재하는 동안 프로세스의 상태가 변하는 것을 의미한다. 
![프로세스_상태전이도](https://user-images.githubusercontent.com/79912056/147618435-446865a8-10c1-4e97-bd0f-f527cd14a5fb.png)
  - 생성, 준비, 실행, 대기, 종료로 이루어져 있다.
    - 생성(New) : 제출(Submit)과 접수(Hold)의 작업을 수행한다.
    - 준비(Ready) : 프로세스가 프로세서를 할당받기 위해 기다리고 있는 상태이다.
    - 실행(Run) : 준비상태 큐에 있는 프로세스가 프로세서를 할당받아 실행되는 상태이다.
    - 대기(Wait) : 프로세스에 I/O 처리가 필요하면 현재 실행중인 프로세스가 중단되고 I/O 처리가 완료될 때까지 대기하고 있는 상태이다.
    - 종료(Exit) : 프로세스의 실행이 끝나고 프로세스 할당이 해제된 상태이다.

- ## 스케줄링(Scheduling)
  - 스케줄링은 프로세스가 생성되어 실행될 때 필요한 시스템의 여러 자원을 해당 프로세스에게 할당하는 작업이다.
  - 스케줄링의 종류에는 장기 스케줄링, 중기 스케줄링, 단기 스케줄링이 있다.
    - 장기 스케줄링 : 어떤 프로세스가 시스템의 자원을차지할 수 있도록 할 것인가를 결정하여 준비상태 큐로 보내는 작업을 의미한다.
    - 중기 스케줄링 : 어떤 프로세스들이 CPU를 할당 받을 것인지를 결정하는 자업을 의미한다.
    - 단기 스케줄링 : 프로세스가 실행되기 위해 CPU를 할당 받는 시기와 특정 프로세스를 지정하는 작업을 의미한다.
  
  
  - 프로세스 스케줄링의 기법
    - 비선점(Non-Preempive) 스케줄링 : 이미 할당된 CPU를 다른 프로세스가 강제로 빼앗아 사용할 수 없는 스케줄링 기법이다
    - 선점(Preemptive) 스케줄링 : 하나의 프로세스가 CPU를 할당받아 실행하고 있을 때 우선순위가 높은 다른 프로세스가 CPU를 강제로 빼앗아 사용할 수 있는 스케줄링 기법이다.