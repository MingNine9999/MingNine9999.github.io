---
layout: post
title: "Algorithm 스터디 준비\n C++ STL Container 편 3. stack, queue, deque, priority_queue"
date: 2019-08-29 09:45:00 +0900
category: algorithm-C++_STL
---

# stack, queue, deque, priority_queue

### 설명

stack, queue, deque, priority_queue(heap)는 자료구조에서 배운 그대로의 기능을 갖추고있다.

따라서, 각각 자료구조의 개념과 함수만 알고 있다면 충분히 활용도가 높다.

<br>

각각 #include <stack> <queue> <deque> 해야 사용 가능하며 이 들 역시도 namesapce std안에 있다.

stack<T> s 는 s.push(), s.pop(), s.top(), s.size(), s.empty() 가 있고

queue<T> q 는 q.push(), q.pop(), q.front(), q.size(), q.emtpy() 로 스택과 top(), front()의 차이만 있다.

deque은 double ended - queue의 줄임말로 큐의 양 쪽 끝이 모두 push, pop이 가능한 자료구조이다.

따라서, push(), pop()도 두 가지씩 존재한다. deque<T> dq 는 dq.push_back(), dq.push_front(),

dq.pop_back(), dq.pop_front(), dq,front(), dq.back(), dq.size(), dq.empty() 가 있다.

또한 덱만 예외로 인덱스에 의한 임의 접근이 가능하기 때문에 []연산자를 사용하여 dq[3]처럼 접근이 가능하다.

priority_queue는 queue의 헤더파일안에 있으며 힙을 구현한다.

기본적으로 최대힙이 구현되어 있으며 비교함수에 따라 최소힙 또는 다른 비교에 따른 힙을 구현 할 수 있다.

priorty_queue에는 인자가 3개가 들어가는데 priority_queue<int, vector<int>, less<int> > pq 형식이다.

(위 선언문에서 >>를 붙여쓴다면 컴파일러에서 쉬프트 연산자와 헷갈려 연산이 달라 질 수 있으므로 띄어쓰도록 하자)

만약 선언할떄 뒤 두개 인자를 생략한다면 defalut로 vector와 less가 들어가며 최소힙을 구현한다면

priority_queue<int, vector<int>, greater<int> > pq 로 선언해주도록 하자

(greater는 functional헤더파일에 있다)

pq.push(), pq.pop(), pq.top(), pq.empty(), pq.size() 가 있다.

<br>

### 예제

![stack_queue_deque_pq](https://github.com/MingNine9999/MingNine9999.github.io/blob/main/_posts/img/stack_queue_deque_pq.png?raw=true)

<br>

### 용도

자료구조들을 따로 구현할 필요 없이 가져다 쓰기만 하면 되므로 매우 편안!