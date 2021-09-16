---
layout: post
title:  "[파이썬] 해시탐색법으로 데이터를 탐색하는 알고리즘 "
date:   2021-09-16
excerpt: "[파이썬] 해시탐색법으로 데이터를 탐색하는 알고리즘 "
study: true
tag:
- Algorithms 
comments: true
---


### 해시탐색법으로 데이터를 탐색하는 알고리즘 

42 12 0 25 36 0 0 0 30 20 8
12가 저장되었는 요소를 검색하자. 12 -> x
해시값(arrayH의 번호) k= 데이터값 / 11 (방의 갯수)


### 문제

알고리즘을 보고 파이썬 코드를 입력하시오.
<br>
<img src="https://bittestb0341.github.io/assets\img\01_20210916day05.png">

{% highlight python %}
arrayH = [42,12,0, 25,36,0,0,0,30,20,8]

x = 7
k = x % 11


while True:
  if arrayH[k] != 0:
    if arrayH[k] == x:
      print('저장위치는 ',k,'번째 요소입니다.')
      break
    else:
      k = (k+1) % 11
      continue
  else:
    print(x,'는 존재하지 않습니다.')
    break
{% endhighlight %}

출력 답: 7 는 존재하지 않습니다.
{: .notice}
___

### 정렬 알고리즘  sort

데이터를 오름차순 또는 내림차순으로 나열하는 알고리즘
다양한 분야에 상당히 많이 사용된다. 

1. 단순 선택법 ( selection sort )
2. 단순 교환법 ( bubble sort )
3. 단순 삽입법 ( insertion sort )
4. 퀵 정렬     ( Quick sort )

#### 단순 선택법

가장 작은 데이터를 선택하여 맨 앞으로 순서대로 정렬한다.

  12 13 11 14 10 가장 작은 10을 맨 앞과 선택 교환 10 13 11 14 12 그 다음 작은 11을 두번째 값과 선택 교환 10 11 13 14 12 그 다음 작은 12를 세번째 값과 선택 교환 10 11 12 14 13 마지막으로 13과 14를 선택 교환 10 11 12 13 14

#### 단순 선택법 알고리즘

1. 탐색 범위의 최소값을 찾는 처리
2. 탐색 범위의 최소값을 맨 앞 요소와 교환