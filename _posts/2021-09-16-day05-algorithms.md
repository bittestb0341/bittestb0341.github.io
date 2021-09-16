---
layout: post
title:  "[파이썬] 이진 탐색 알고리즘, 해시 탐색 알고리즘"
date:   2021-09-16
excerpt: "[파이썬] 이진 탐색 알고리즘, 해시 탐색 알고리즘"
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

### # 정렬 알고리즘  sort

데이터를 오름차순 또는 내림차순으로 나열하는 알고리즘
다양한 분야에 상당히 많이 사용된다. 

1. 단순 선택법
2. 단순 교환법 ( bubble sort )
3. 단순 삽입법
4. 퀵 정렬

