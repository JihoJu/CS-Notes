# Stack

### Stack(스택)이란

- **데이터의 입출력이 한 곳(방향)으로 제한**이 되어있다.
- 또한, **데이터의 입출력 방향은 Last-in-First-out (LIFO) 로 마지막에 들어온 데이터가 가장 먼저 나오는 데이터 구조**이다.

### **What is it used for?**

- **Call stack of function(recursion)**
- **Operator postfix notation**
- **스트링을 파라미터로 받아서, 그것을 역순으로 리턴하는 함수**
- etc…

### Implementation

Stack 에는 기본적으로 **4가지의 추상화된 함수**가 존재

- **push**: 데이터를 넣는다.
- **pop**: 스택에 있는 최상위 값을 뺀다.
- **isFull**: stack 꽉차있는 지 확인
- **isEmpty**: 스택이 비어있있는 지 확인

> **왜 isEmpty 같은 함수가 필요한거지??**
> 
- **for (i in 0 until stack.size)** 로도 구현이 괜찮지 않나?
    - 아니다. loop 를 돌리기 위해서 새로운 변수 i 를 생성하고 stack 의 size도 확인을 해야한다.
- 이를 효율적으로 수정하면 다음과 같다.
- **while(!stack.isEmpty)**
    - isEmpty 함수를 사용하면 마지막 데이터의 위치를 가리키는 ‘stack pointer’ 만 확인하면 결과가 리턴이 되어 **for (i in 0 until stack.size)** 보다 효율적이다.

**Abstract Data Type 인 Stack 을 구현하는 방법**에는 여러가지가 존재

- Array
    - **마지막에 들어온 데이터의 위치를 표시하는 ‘Stack Pointer(sp)’ 가 필요**
        - Last index 를 tracking
    - 데이터 크기를 미리 지정해야하는 단점
- LinkedList
    - 마지막에 들어온 노드(데이터)의 위치를 tracking 할 수 있는 **‘Stack Pointer(sp)’ 이 또한 필요**
- Queue
    - **Queue Data Structure 2개로도 Stack 을 구현 가능**
    - Stack Pointer 가 필요가 없다.