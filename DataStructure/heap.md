# Heap

먼저, **Heap** 은 **우선순위 큐를 위해 만들어진 자료구조**이다.

### Priority Queue(우선순위 큐)란?

Queue 에 **우선순위의 개념**을 도입한 data structure

> 데이터들이 각각 우선순위를 가지고 있으며 우선순위가 높은 데이터들이 먼저 나간다.
> 

**What is it used for?**

- **작업 스케줄링**
- 시뮬레이션 시스템
- 수치해석 계산
- 네트워크 트래픽 제어

**우선순위 큐**는 **배열**, **연결 리스트**, **힙** 으로 구현이 가능하다.

| 우선순위 표현 방법 | 삽입 | 삭제 |
| --- | --- | --- |
| 순서 있는 배열 | O(n) | O(1) |
| 순서 있는 연결 리스트 | O(n) | O(1) |
| 순서 없는 배열 | O(1) | O(n) |
| 순서 없는 연결 리스트 | O(1) | O(n) |
| 힙 | O(logn) | O(logn) |

# Heap(힙)이란?

- 완전 이진 트리의 일종으로 우선순위 큐를 위해 만들어진 Data Structure 이다.
- 입출력이 많이 일어나는 상황에서 데이터에서 최대값, 최소값을 빠르게 찾아낼 수 있도록 만들어진 완전 이진 트리(Complete Binary Tree)
    - 완전 이진 트리(Complete Binary Tree): 노드를 삽입할 때 최하단 왼쪽 노드부터 차례대로 삽입하는 트리
- 힙은 일종의 반정렬 (느슨한 정렬) 상태를 유지한다.
    - 부모 노드의 키 값이 자식 노드의 키 값보다 항상 큰(작은) 완전 이진 트리

## Why?

- 배열 or 링크드 리스트에 데이터를 넣고 최대값, 최소값을 찾으려면 **O(n)** 이 걸린다.
- 이에 반해, 힙에 데이터를 넣고 최대값, 최소값을 찾으려면 **O(logn)** 이 걸린다.
- 우선순위 큐와 같이 최대값 또는 최소값을 빠르게 찾아야 하는 자료구조 및 알고리즘 구현 등에 활용

## Heap 의 구조

- Heap 은 **최대값을 구하기 위한 구조 (최대 힙, Max Heap)** 와, **최소값을 구하기 위한 구조 (최소 힙, Min Heap)** 로 분류할 수 있다.
    - **Max Heap (최대 힙)**
        - 부모 노드의 값이 자식 노드의 값보다 항상 크거나 같은 완전 이진 트리
    - **Min Heap (최소 힙)**
        - 부모 노드의 값이 자식 노드의 값보다 항상 작거나 같은 완전 이진 트리
- Heap 은 다음 2가지 조건을 가지고 있는 자료구조
    - 각 노드의 값은 해당 노드의 자식 노드가 가진 값보다 같거나 (작거나/크다).
    - 완전 이진 트리 형태를 갖는다 → 트리에 노드가 insert 될 때 왼쪽부터 채워진다.

### **힙과 이진 탐색 트리의 공통점과 차이점**

- 공통점: 힙과 이진 탐색 트리는 모두 이진 트리임
- 차이점:
    - 힙은 각 노드의 값이 자식 노드보다 크거나 같음(Max Heap의 경우)
    - 이진 탐색 트리는 왼쪽 자식 노드의 값이 가장 작고, 그 다음 부모 노드, 그 다음 오른쪽 자식 노드 값이 가장 큼
    - 힙은 이진 탐색 트리의 조건인 자식 노드에서 작은 값은 왼쪽, 큰 값은 오른쪽이라는 조건은 없음
        - 힙의 왼쪽 및 오른쪽 자식 노드의 값은 오른쪽이 클 수도 있고, 왼쪽이 클 수도 있음
- 이진 탐색 트리는 탐색을 위한 구조, 힙은 최대/최소값 검색을 위한 구조 중 하나

### **5. 힙 (Heap) 시간 복잡도**

- depth (트리의 높이) 를 h라고 표기한다면,
- n개의 노드를 가지는 heap 에 데이터 삽입 또는 삭제시, 최악의 경우 root 노드에서 leaf 노드까지 비교해야 하므로 h=log2n 에 가까우므로, 시간 복잡도는 𝑂(𝑙𝑜𝑔𝑛)
    - 한번 실행시마다, 50%의 실행할 수도 있는 명령을 제거한다는 의미. 즉 50%의 실행시간을 단축시킬 수 있다는 것을 의미

## ✏️  예제

- 만 명의 학생 중 상위 10명을 알고 싶다. 해당 문제를 어떻게 접근할 것인가? 단, 정렬을 사용하면 안된다.
  - Max Heap 에 만 명을 삽입 후 10 명을 max heap 에서 출력시켜주면 될 것이다.
  - 만 명을 max heap 에 삽입 후 10명을 max heap에서 빼주면 시간 복잡도는 O(10 x log(10000)) 이 된다.
- 10마리의 말 중 가장 빠른 말 3마리만 추출해 세계 경주 대회에 내보내고 싶다면 어떻게 추출할 것인가?
  - max heap 사용!!

## Heap(힙)의 구현

- 힙을 저장하는 표준적인 자료구조는 **배열**
- 구현을 쉽게 하기 위해 인덱스 0은 사용하지 않는다.

> 왼쪽 자식 index = (부모 index) * 2
> 

> 오른쪽 자식 index = (부모 index) * 2 + 1
> 

> 부모 index = (왼쪽/오른쪽) 자식 index / 2
> 

### Insertion (삽입)

1. 새로운 노드를 Heap 의 마지막 index 에 삽입
2. 오로지 부모 노드의 key 값과 비교하여 heap 의 알맞은 위치(index) 를 찾아간다.
- **Insertion 구현 코드**
    
```python
class Heap:
    def __init__(self, data):
        self.heap_array = list()
        self.heap_array.append(None)
        self.heap_array.append(data)
            
    def move_up(self, inserted_idx):
        if inserted_idx <= 1:
            return False
        
        parent_idx = inserted_idx // 2
        if self.heap_array[inserted_idx] > self.heap_array[parent_idx]:
            return True
        else:
            return False
            
    def insert(self, data):
        if len(self.heap_array) == 0:
            self.heap_array.append(None)
            self.heap_array.append(data)
            return True
        
        self.heap_array.append(data)
        
        inserted_idx = len(self.heap_array) - 1
        
        while self.move_up(inserted_idx):
            parent_idx = inserted_idx // 2
            self.heap_array[inserted_idx], self.heap_array[parent_idx] = self.heap_array[parent_idx], self.heap_array[inserted_idx]
            inserted_idx = parent_idx
        
        return True
```
    

### Deletion (삭제)

1. Heap 의 Root 노드(Index = 1)를 내보낸다(삭제).
2. Heap 의 가장 마지막 노드의 key 값을 Root 노드 자리(index = 1)에 삽입(혹은 가정)
3. 자식 노드의 key 값과 비교해가며 heap 의 알맞은 위치(index) 를 찾아간다.
- **Deletion 구현 코드**
    
```python
class Heap:
    def __init__(self, data):
        self.heap_array = list()
        self.heap_array.append(None)
        self.heap_array.append(data)
        
    def move_down(self, popped_idx):
        left_child_popped_idx = popped_idx * 2
        right_child_popped_idx = popped_idx * 2 + 1
        
        # case1: 왼쪽 자식 노드도 없을 때
        if left_child_popped_idx >= len(self.heap_array):
            return False
        # case2: 오른쪽 자식 노드만 없을 때
        elif right_child_popped_idx >= len(self.heap_array):
            if self.heap_array[popped_idx] < self.heap_array[left_child_popped_idx]:
                return True
            else:
                return False
        # case3: 왼쪽, 오른쪽 자식 노드 모두 있을 때
        else:
            if self.heap_array[left_child_popped_idx] > self.heap_array[right_child_popped_idx]:
                if self.heap_array[popped_idx] < self.heap_array[left_child_popped_idx]:
                    return True
                else:
                    return False
            else:
                if self.heap_array[popped_idx] < self.heap_array[right_child_popped_idx]:
                    return True
                else:
                    return False
        
    def pop(self):
        if len(self.heap_array) <= 1:
            return None
        
        returned_data = self.heap_array[1]
        self.heap_array[1] = self.heap_array[-1]
        del self.heap_array[-1]
        popped_idx = 1
        
        while self.move_down(popped_idx):
            left_child_popped_idx = popped_idx * 2
            right_child_popped_idx = popped_idx * 2 + 1
    
            # case2: 오른쪽 자식 노드만 없을 때
            if right_child_popped_idx >= len(self.heap_array):
                if self.heap_array[popped_idx] < self.heap_array[left_child_popped_idx]:
                    self.heap_array[popped_idx], self.heap_array[left_child_popped_idx] = self.heap_array[left_child_popped_idx], self.heap_array[popped_idx]
                    popped_idx = left_child_popped_idx
            # case3: 왼쪽, 오른쪽 자식 노드 모두 있을 때
            else:
                if self.heap_array[left_child_popped_idx] > self.heap_array[right_child_popped_idx]:
                    if self.heap_array[popped_idx] < self.heap_array[left_child_popped_idx]:
                        self.heap_array[popped_idx], self.heap_array[left_child_popped_idx] = self.heap_array[left_child_popped_idx], self.heap_array[popped_idx]
                        popped_idx = left_child_popped_idx
                else:
                    if self.heap_array[popped_idx] < self.heap_array[right_child_popped_idx]:
                        self.heap_array[popped_idx], self.heap_array[right_child_popped_idx] = self.heap_array[right_child_popped_idx], self.heap_array[popped_idx]
                        popped_idx = right_child_popped_idx
        
        return returned_data
```
