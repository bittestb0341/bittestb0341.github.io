---
layout: post
title:  "알고리즘"
date:   2021-09-15
excerpt: "알고리즘"
study: true
tag:
- Algorithms 
comments: true
---




### 이진 탐색 알고리즘
   1. 가운데 요소를 선택한다.
   2. 가운데 요소와 찾는 데이터를 비교한다.
   3. 탐색 범위를 절반으로 좁힌다.
   4. 찾는 데이터가 존재하지 않을 수도 있다.

### 가운데 요소를 선택하는 방법

*  평균을 이용해서 가운데 요소를 찾는다.
* 0 ~ 10 0+10/2 = 5
* head tail (head+tail)/2
* 요소의 갯수가 짝수라면 0~5
* 0+5/2=2.5 보통 버리기를 사용한다.

<img src="https://bittestb0341.github.io/assets\img\1_20210915day04.png">


### 문제
아래 알고리즘을 보고, 파이썬 코드를 작성해보자!

<img src="https://bittestb0341.github.io/assets\img\2_20210915day04.png">

{% highlight python %}

array = [11,13,17,19,23,29,31]

head = 0
tail = 6

while True:
  if head <= tail:
    mid = (head+tail)//2  # 소수가 나오니까 몫만 취하자!
    if array[mid] == 17: 
      print(mid,'번째 요소가 일치')
      break
    else:
      if array[mid] < 17:
        head = mid + 1
      else:
        tail = mid - 1

  else:
    print("찾지 못했습니다.")
    break

{% endhighlight %}