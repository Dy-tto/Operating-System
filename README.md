# Operating-System

## Operating System 정리

### Chap1. 
1. 통용되는 정의: 컴퓨터에서 항상 실행 중인 프로그램
Kernel 이라고도 불림

2. Bootstrap: 컴퓨터가 켜질 때 가장 처음 실행되는 프로그램
그 다음 OS가 실행

3. Interrupt: a signal to the CPU

4. 저장 시스템 계층: registers > cache > main memory > solid-state disk > hard disk > optical disk > magnetic tapes
앞에 있을 수록 속도 빠르다

5. 컴퓨터 시스템 구성:
CPU : 명령을 실행하는 하드웨어
Processor : 하나 이상의 CPU를 포함하는 물리적 칩
Core
Multicore
Multiprocessor

6. Symmetric Multiprocessing (SMP)
가장 흔한 멀티프로세서 시스템
각각의 CPU가 register와 cache를 가지고 병렬로 구성.

7. Multi-core design
한 프로세서에 several cores 구성

8. Multiprogramming
여러개의 프로그램을 메모리에 동시에 올리는 것
CPU의 효율이 올라간다.

9. Multitasking = Multiprocessing
CPU가 jobs들을 엄청 빠르게 switch하면서 실행
users는 각각의 job들을 같이 사용할 수 있다.
CPU scheduling: 몇 개의 프로세서들이 동시에 실행 준비, 시스템이 다음에 실행될 프로세스를 선택

10. Operations mode
User mode, kernel mode : 프로그램이 잘못 실행되지 않게한다.

11. Virtualization (가상화)
Virtual Machine Manager : 운영체제를 여러 개 돌릴 수 있다.
Ex) VMware, Xen, virtual box

12. 다양한 환경의 OS
Mobile, Client-Server(1:1), Peer-to-Peer(P2P, N:N), Cloud, Real-Time Embedded Systems.

### Chap2
.
1. OS가 제공하는 환경
UI, Program execution, I/O operation, File-System, Communications, Error detection, Resource allocation, Logging, Protection and security

2. Interface
CLI : Commend Line Interface (shells)
GUI : Graphical User Interface (Windows, Aqua for MacOS
Touch-Screen Interface : Android UI, IOS UI

3. System Calls
Services made avilable by the OS
API : Application Programming Interface
Ex)
Process Control: fork(), exit(), wait()
File Manipulation : open(), read(), write(), close()

### Chap3. Processes

1. Process : 실행 중인 프로그램

2. Process의 sections
Text section : 실행 가능한 코드(명령어)
Data section : global variables
Heap section : 동적할당 메모리
Stack section : 함수 호출

3. Process의 state
New : 프로세스 생성
Running : 실행
Waiting : I/O를 기다리는 등 대기상태
Ready : 실행 준비 완료
Terminated : 실행 종료

4. Process Control Block (PCB)
Process state
Program Counter(PC)
CPU registers
CPU-scheduling information
Memory-management information
Accounting information
I/O status information

5. Thread
A lightweight process
Multiprocess 보다 Multithread가 장점이 더 많다

6. Process scheduling
Multiprogramming : 동시에 여러 프로세스를 실행, CPU 효율을 최대화
Time sharing : process들을 아주 빠르게 switch, user가 실행 중인 각 프로그램들을 같이 사용

7. Scheduling Queues
Ready queue -> running -> waiting/ready queue
PCB 연결리스트로 구현되어 있다.

8. Context Switch
Interrupt 발생 시 PC가 어디까지 실행됬는지 저장, 나중에 복원할 수 있다.
상태 저장, 상태 복원 기능

9. Operations on Processes
The creating process : a parent process
A newly created process : a child process
주로 fork() 사용
Parent 와 child가 동시에 실행되거나 / child가 끝날 때까지 기다리거나

child는 parent를 복제 하거나 새로운 프로그램을 로드하거나


10. Process terminates
Return 값을 반환해서 끝나는 경우
exit() system call로 강제 종료

OS는 resources를 회수한다. (Allocated memories, open files, I/O buffers, etc)

11. Zombie and Orphan
Zombie process : child가 종료되었지만 parent가 child의 종료 상태를 회수하지 않았을 경우( wait() 호출을 하지 않음)
Orphan process : parent가 wait()을 하지 않고 child보다 먼저 종료




