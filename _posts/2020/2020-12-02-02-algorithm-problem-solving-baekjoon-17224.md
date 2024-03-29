---
layout: single
title: "[Problem Solving - Baekjoon] 17224 APC는 왜 서브태스크 대회가 되었을까?"
date: 2020-12-02 22:20:00.000000000 +09:00
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
- implementation
meta:
  _edit_last: '2'
author:
  login: DawoonJeong
  email: iamdawoonjeong@gmail.com
  display_name: Dawoon Jeong
  first_name: Dawoon
  last_name: Jeong
permalink: "/algorithm-problem-solving-baekjoon-17224/"
---
# [Baekjoon Online Judge] 17224 APC는 왜 서브태스크 대회가 되었을까?

## 문제
2019년 올해도 어김없이 아주대학교 프로그래밍 경시대회(Ajou Programming Contest, APC)가 열렸다! 올해 새롭게 APC의 총감독을 맡게 된 준표는 대회 출제 과정 중 큰 고민에 빠졌다. APC에 참가하는 참가자들이 너무 다양해 대회 문제 난이도 설정이 너무 어렵기 때문이다.

APC는 프로그래밍 대회에 익숙하지 않은 학생들과 전공생이 아닌 학생들도 대거 참가하기 때문에 모두가 풀거나 도전할 수 있는 난이도 커브를 갖춰야 한다. 또한 '경인지역 6개대학 연합 프로그래밍 경시대회 shake!'에 참가할 학교 대표 10인을 선발하기 위한 대표 선발전으로서의 변별력도 갖추어야 하며, 외부인들이 따로 참가할 수 있는 Open Contest가 동시에 진행되기 때문에 소위 '고인물'들에게 한 시간도 안되어 대회가 정복당하는 일도 막고 싶다. 여기에 APC 출제진인 준표, 만영, 현정, 준서는 문제를 준비하는 데 무척 고생을 했기 때문에 참가자들이 모든 문제를 한번씩은 읽어주었으면 하는 소망도 가지고 있다.

욕심 그득한 준표는 고민끝에 이 수많은 니즈를 충족시키기 위한 한가지 해결책을 제안했다. 하나의 문제를 제한조건을 통해 쉬운 버전과 어려운 버전으로 나누어 쉬운 버전만 맞더라도 부분점수를 주는 서브태스크 문제로 대회를 구성하는 것이다. 또한 이렇게 만들어진 문제를 쉬운 버전의 난이도순으로 배치하려 한다.

위와 같이 문제를 준비하면 프로그래밍 대회에 익숙하지 않은 사람은 앞에서부터 따라가면서 도전해볼 수 있어 쉬운 문제를 찾는 데 시간을 쓰지 않을 수 있고, 어려운 버전으로 학교 대표 선발을 위한 변별력을 유지할 수 있으며, 모든 문제가 읽히길 바라는 출제진의 소망도 이룰 수 있을 것이다!


현정이는 APC에 한 번이라도 나가보고 싶다는 소망이 있다. 하지만 이 소망은 여태까지 단 한 번도, 그리고 앞으로도 이루어질 리 없기 때문에 현정이가 입버릇처럼 하게 된 말이 있는데...

현정 : 아~~ 나도 APC 참가만 했으면 상금 받는 건데~~~~~
준표 : ... 그건 아닌 것 같은데?
현정이의 근거 없는 자신감이 눈꼴신 준표는 출제 중에 평가한 문제 난이도를 통해 현정이의 예상 점수를 알려주고 현정이가 현실을 받아들일 수 있도록 도와주고자 한다.

현정이는 L 만큼의 역량을 가지고 있어 L보다 작거나 같은 난이도의 문제를 풀 수 있다. 또한 현정이는 코딩이 느리기 때문에 대회 시간이 부족해 K개보다 많은 문제는 해결할 수 없다. 어떤 문제에 대해 쉬운 버전을 해결한다면 100점을 얻고, 어려운 버전을 해결한다면 여기에 40점을 더 받아 140점을 얻게 된다. 어려운 버전을 해결하면 쉬운 버전도 같이 풀리게 되므로, 한 문제를 해결한 것으로 계산한다.

현정이가 APC에 참가했다면 최대 몇점을 얻을 수 있었을지 알려주자.


### 입력
첫 줄에 문제의 개수 N, 현정이의 역량 L, 현정이가 대회중에 풀 수 있는 문제의 최대 개수 K가 주어진다.

둘째 줄부터 N개의 줄에 걸쳐 1 ~ N번째 문제의 쉬운 버전의 난이도 sub1, 어려운 버전의 난이도 sub2 가 순서대로 주어진다.

### 출력
현정이가 APC에 참가했다면 얻었을 점수의 최대값을 출력한다.

### 제한
- 1 ≤ N ≤ 100
- 1 ≤ L ≤ 50
- 1 ≤ sub1 ≤ sub2 ≤ 50

### 서브태스크1
- K = N

### 서브태스크2
- K = N

### 예제
- input

```java
4 8 4
1 8
4 5
6 20
9 12
```

- output

```java
380
```

### 예제2
- input

```java
8 7 5
1 3
2 5
3 5
4 8
5 8
6 9
6 7
7 10
```

- output

```java
660
```

### 예제3
- input

```java
8 9 5
1 8
3 10
4 5
5 20
7 12
8 15
9 50
14 14
```

- output

```java
580
```
### 분류
- 구현

## 풀이

### 문제 파악
- 어려운 문제를 풀면 140 (쉬운문제푼걸로 함)
- 쉬운문제풀면 100
- 문제풀수있는 갯수는 k개까지 가능

### 구현

[전체소스보기](https://github.com/devvoon/java-datastructure-algorithm/blob/master/java-algorithm-problem-solving/src/baekjoon/problem17224/Main.java)

- 능력치를 기준으로 어려운 문제 풀수 있는 갯수 구하기 (hard)
- 쉬운문제만 풀수있는 경우 갯수 구하기 (easy)

```java
int score = 0;

int easy = 0;
int hard = 0;

//풀수있는 문제의 갯수 구하기
for (int i = 0; i < N; i++) {

    //어려운 버전의 난이도 sub2를 풀었을때는 140점 획득
    if (L >= sub2[i]) {
        hard++;
    }else if (L < sub2[i] && L >= sub1[i] ){
        //어려운 버전은 못풀고 쉬운버전 sub1 풀었을때에는 100점 획득
        easy++;
    }
}
```

- 어려운 문제, 쉬운 문제 각각 계산해주기

```java
//어려운 문제 점수계산
int solved = Math.min(K, hard);
score = solved*140;

//풀수있는 문제의 갯수가 남아있다면 쉬운문제 점수 계산
if ( hard < K) {
    solved = Math.min(K-hard, easy) ;
    score += solved*100;
}

System.out.println(score);
```

---

#### references
<https://www.acmicpc.net/problem/17224>
