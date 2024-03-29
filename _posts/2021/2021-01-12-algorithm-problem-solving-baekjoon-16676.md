---
layout: single
title: "[Problem Solving - Baekjoon] 16676 근우의 다이어리 꾸미기"
date: 2021-01-12 22:46:00.000000000 +09:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories:
- Problem Solving
tags:
- data structure
- algorithm
- baekjoon
- greedy
meta:
  _edit_last: '2'
author:
  login: DawoonJeong
  email: iamdawoonjeong@gmail.com
  display_name: Dawoon Jeong
  first_name: Dawoon
  last_name: Jeong
permalink: "/algorithm-problem-solving-baekjoon-16676/"
---
# [Baekjoon Online Judge] 16676 근우의 다이어리 꾸미기

## 문제
곧 2018년이 끝나고, 2019년이 온다.

근우는 2019년에는 꼭 다이어리를 쓰기로 했다. 하지만, 처음 써보는 다이어리에 쓸 내용이 없어 고민하던 중 자신의 목표 연봉을 다이어리 앞에 쓰기로 했다.

다이어리를 쓰는 사람은 알겠지만 예쁜 다이어리의 핵심은 스티커다. 그렇기 때문에 근우는 목표 연봉을 손으로 쓰지 않고, 스티커로 붙이려고 한다. 목표연봉이 100이라면 [1] [0] [0]과 같이 붙이는 것이다. [1]이란 1이 써져있는 스티커로, 다른 숫자에 대해서도 동일한 규칙이 적용된다.

근우는 자신의 연봉 최댓값이 N임을 안다. 그렇기에 근우는 0부터 N까지의 수를 하나씩 스티커를 통해 모두 표현하고자 한다. 최댓값 N이 10이면 만드는 과정은 다음과 같다.

스티커 더미에서 [0] 하나를 가져와 0을 표현한다 ([0]). 이후 사용한 스티커 [0]을 스티커 더미로 되돌린다.
스티커 더미에서 [1] 하나를 가져와 1을 표현한다 ([1]). 이후 사용한 스티커 [1]을 스티커 더미로 되돌린다.
9까지의 마찬가지 방법으로 표현할 수 있다.
스티커 더미에서 [0] 하나와 [1] 하나를 가져와 10을 표현한다 ([1] [0]). 이후 사용한 스티커 [0]과 [1]을 스티커 더미로 되돌린다.
그러므로 N = 10 이면 스티커가 [0]부터 [9]까지 1개씩만 있으면 모두 표현할 수 있다.

필요한 스티커를 사러 고려대 하나스퀘어 유니스토어에 도착한 근우는 고민이 생겼다. 스티커 팩에는 [0]부터 [9]까지 스티커가 한 장씩 밖에 없으면서 생각보다 너무 비싼 것이다!

그렇기에 근우는 0부터 N까지 모든 수를 하나씩 표현할 수 있게 최소한의 스티커 팩만 사려고 한다.

근우는 매우 똑똑하지만, 스티커 팩 가격에 충격을 받아 계산할 수 없는 상태가 돼버렸다.

여러분이 근우의 최대 목표액 N이 주어졌을 때, 근우가 필요한 최소 스티커 팩의 개수를 구해주자.

### 입력
첫 번째 줄에 근우의 연봉 최댓값을 의미하는 정수 N이 주어진다. (0 ≤ N ≤ 1,000,000,000)

### 출력
첫 번째 줄에 근우가 0부터 N까지 스티커로 표현하기 위해 구매해야 하는 스티커 팩의 최소 개수를 출력한다.

### 예제

- input

```java
88
```

- output

```java
1
```

### 분류
- greedy

## 풀이

### 문제 파악
- 0 1 2 3 4 5 6 7 8 9 : 1팩인경우 1~10까지 표현 가능 (<11)
- 0 1 2 3 4 5 6 7 8 9 : 2팩인경우 11~110 까지 표현 가능 (<111)
- 0 1 2 3 4 5 6 7 8 9 : 3팩인경우 111~1110 까지 표현 가능 (<1111)

### 구현

[전체소스보기](https://github.com/devvoon/java-datastructure-algorithm/blob/master/java-algorithm-problem-solving/src/baekjoon/problem16676/Main.java)


- 입력한 숫자의 length 구하기   
- 길이만큼 length*1 만들기 예) 88이면 2, 1111이면 4
- 예) 입력이 88 이라면 max 값으로 11이 만들어짐
- 예2) 입력이 1111이라면 max 값으로 1111이 만들어짐  
- 예3) 입력이 1110이라면 max 값으로 1111이 만들어짐

```java
String n = br.readLine();
int lenght = n.length();

String max = "" ;
for (int i = 0; i < lenght; i++) {
    max = max.concat("1");
}
```

- 입력한 숫자가 1자리 숫자이면 스티커 1팩이면 완성
- 입력한 숫자가(88) max 값 (11) 보다 크거나 같을경우 length = 2 그대로 출력
- 입력한 숫자가(1110) max 값 (1111) 보다 작기 때문에 length-1 = 3 출력

```java
if (lenght == 1) {
    System.out.println(1);
}else if ( Integer.parseInt(n) >= Integer.parseInt(max)) {
    System.out.println(lenght);
}else {
    System.out.println(lenght-1);
}
```

---

#### references
<https://www.acmicpc.net/problem/16676>
