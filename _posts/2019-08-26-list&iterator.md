---
layout: post
title: "Algorithm 스터디 준비\n C++ STL Container 편 2.list & iterator"
date: 2019-08-26 16:50:00 +0900
category: algorithm/C++_STL
---

# list와 iterator

list는 다들 알고있는 링크드리스트이다

#include <list>를 포함해야하며, 역시 std가 필요하다

list<T>의 형태로 선언하며 list는 []연산에의한 임의접근을 할 수 없기 때문에, iterator라는 친구를 잘 알아야 한다.

list는 기본적으로 더블링크드리스트이며 원형링크드리스트는 따로 지원하지 않기 떄문에 직접 구현해줘야 한다.



list를 쓰기위한 iterator를 알아보자!

일단 iterator(반복자)는 리스트에만 쓰이는 것이 아니라 모든 STL Container에 사용되며 포인터와 매우 유사한 기능과 형태를 갖고있다.

iterator변수는 list<T>::iterator iter 형식으로 선언하며 데이터는 list의 함수에서 받아 사용

할 수 있다.

list<int> L이라는 리스트가 있다고 하면 L.begin()은 리스트의 헤드노드의 iterator를 반환하고 L.end()는 리스트의 테일의 다음노드의

iterator를 반환한다. rbegin()과 rend()라는 함수도 있는데 이 함수들은 리버스 함수들로 rbegin()은 뒤에서 맨 앞 노드 즉, 테일 노드를

반환하고 rend()는 뒤에서 맨뒤노드의 다음노드 즉, 헤드의 앞 노드를 반환한다.

즉, list<int>::iterator iter = L.begin(); 이면 iter는 헤드를 가르키고 있고 iter++하면 다음 노드, --하면 이전 노드를 가르키게된다.

리스트의 헤드노드부터 테일노드까지 탐색하는 반복문을 for (list<int>::iterator iter = L.begin(); iter != L.end(); iter++) 로 쓸 수 있다.

iter변수의 자료형이 길어서 쓰기힘들다면,  auto iter = L.begin()으로 사용 할 수 도 있다.



iterator를 사용 할 수 있게 되었다면, 리스트에 노드를 추가 삭제 하는 방법을 알아보자.

기본적인 추가 삭제는 insert()와 erase()로 할 수 있다.

insert()는 맨 앞에는 항상 iterator변수가 들어간다. 그리고 값이 들어가는데 그 값은 iterator변수가 가리키고 있는 노드 앞으로 삽입된다.

L.insert(iter, val)이런식으로 사용하고 L.insert(iter, n, val)처럼 여러개를 한번에 넣는 것도 가능하다.

또 L.insert(iter, first, last)처럼 first와 last에 아예 새로운 iterator변수를 삽입해서 범위를 한번에 삽입하는 것도 가능하다.

(first부터 last의 앞까지 삽입)

erase()도 역시 맨 앞에는 항상 iterator변수가 들어간다. L.erase(iter)로 한다면 iter가 가르키고있는 값이 삭제된다.

마찬가지로, L.erase(first, last)처럼 범위를 지정해서 한번에 삭제하는것이 가능하다. (first부터 last의 앞까지 삭제)

추가로 맨 앞, 맨 뒤의 삽입, 삭제는 push_back(), push_front(), pop_back(), pop_front()로 편하게 구현 할 수 있다.

그 외 쓸만한 함수로는, size(), clear(), sort(), unique(), merge()정도가 있다.



### 예제

![list_iter](https://github.com/MingNine9999/MingNine9999.github.io/blob/main/_posts/img/list_iter.png?raw=true)


### 용도

링크드리스트 문제 풀 때 하나하나 구현 할 필요가 없!다! ㄱㅇㄷ