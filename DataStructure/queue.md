# Queue

### Queue(큐) 란

- **데이터의 입력과 출력이 각각 한 곳(방향)으로 제한**이 되어있다.
    - **입력**은 큐의 **마지막**에서 이루어진다.
    - 출력은 큐의 **앞단**에서 이루어진다.
- **데이터의 입출력 방향은 First-in-First-out (FIFO) 으로 처음에 들어온 데이터가 가장 먼저 나오는 데이터 구조**이다.

### What is it used for?

- **컴퓨터 운영체제의 테스크 스케줄링**
- etc…

### Implementation

Queue 에는 기본적으로 5**가지의 추상화된 함수**가 존재

- **enQueue()**: 큐에 데이터를 넣는다.
- **deQueue()**: 큐에서 데이터를 빼낸다.
- **isEmpty()**: 큐가 비어있는지 확인한다.
- **isFull()**: 큐가 꽉 차 있는지 확인한다.
- **peek()**: 앞에있는 원소를 삭제하지 않고 반환한다.

**Abstract Data Type 인 Queue 를 구현하는 방법**에는 여러가지가 존재

- Array
    - Queue의 처음과 마지막 위치(인덱스)의 tracking **변수 필요**
        - Front, Back index 를 tracking
- LinkedList
    - Queue의 처음과 마지막 위치를 tracking **포인터 변수 필요**
- Stack
    - Stack **2개로 Queue 구현 가능**

### Problem

데이터를 빼내는 deQueue() 연산을 사용하면 맨 앞(front)에 있는 데이터가 빠져나간다. 그럼 **맨 앞 이후에 있는 데이터들을 앞으로 한 칸씩 이동**해야한다. 그렇지 않으면 **Queue의 가동 범위가 줄어들고, 재사용이 불가**해진다.

이러한 문제점 보완하기 위해 **원형 큐(Circle Queue)** 를 사용 혹은 **재할당 과정**을 거친다.