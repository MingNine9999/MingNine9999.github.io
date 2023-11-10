---
layout: post
title: "Algorithm 스터디 준비\n C++ STL Container 편 4.pair & tuple"
date: 2020-05-22 23:59:00 +0900
category: algorithm/C++_STL
---

# pair와 tuple

### 설명

pair는 utility헤더에 정의되어 있지만, 굳이 헤더파일을 선언하지 않아도 사용할 수 있다. (왜지?)

pair도 역시 namespace std에 정의되어 있고, 있다가 볼 pair를 만드는 함수 make_pair도 std안에 있다.

pair는 이름 그대로 두 가지 변수를 하나로 생각할 수 있는 구조체라고 생각하면 쉽다. 두 개의 변수 모두

템플릿으로 정의 되어있기 때문에, 사용하고 싶은 자료형을 마음대로 사용해도 상관이 없다.

내부 변수는 first와 second 두 가지가 있으며 순서대로 앞, 뒤 변수를 가르킨다.

사실 단순 구조체이기 때문에 구현하기 귀찮을 때, 유용하게 쓸 수 있는 container이지 특별한 기능은

없다고 할 수 있다.

<br>

선언 : pair<T, T> p

인자 참조 : p.first, p.second

선언할 때에는 pair<int, int> p = { 1,2 };가 가능하지만 그 외에 값을 대입할 때에는 p.first = 1; p.second = 2;

또는 p = make_pair( 1,2 ); 로 해야한다. make_pair는 앞, 뒤의 인자로 pair를 만들어 반환한다.

또한 구조체인 만큼 두 페어사이의 대입 p1 = p2도 가능하고 operator<가 정의되어 있어 p1 < p2의 비교도 가능하다.

p1 < p2 는 먼저 first인자로 비교되고 first인자가 서로 같다면 second인자로 비교되어진다.

따라서 sort를 사용할 때에도 first인자로 먼저 정렬되고 first인자가 같은 값에 대해서 second인자로 정렬된다.

### 예제

![pair](https://github.com/MingNine9999/MingNine9999.github.io/blob/main/_posts/img/pair.png?raw=true)

![pair_out](https://github.com/MingNine9999/MingNine9999.github.io/blob/main/_posts/img/pair_out.png?raw=true) 이 처럼 b의 first가 더 크기 때문에 if문에서 b가 출력되는 것을 알 수 있다.

<br>

### tuple!

추가로 tuple은 pair보다 많은 인자들을 하나로 묶는데 사용한다.

#include <tuple>헤더를 추가해야 사용할 수 있고, 마찬가지로 namespace std안에 있다.

두 개보다 많은 인자를 하나로 묶을 수 있고, 몇 개가 나올지 모르기 때문에 인자로 접근하는 것이 아닌, get<n>을

사용하여 접근한다. (get<n>은 pair에서도 쓸 수 있다. 0, 1만이지만)

그런데 개인적으로는 두 개보다 많은 인자를 하나로 묶을 때에는 그냥 구조체를 새로 선언하는 것이 직접 operator도

정해 줄 수 있고 더 편해서 tuple은 거의 쓰지않는다. (많이 안써봐서 설명을 못하는것도 사실이다ㅎㅎ)