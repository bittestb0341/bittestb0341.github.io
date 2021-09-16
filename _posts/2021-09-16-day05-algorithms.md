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

___
___

#### 단순 선택법

가장 작은 데이터를 선택하여 맨 앞으로 순서대로 정렬한다.

  12 13 11 14 10 가장 작은 10을 맨 앞과 선택 교환 10 13 11 14 12 그 다음 작은 11을 두번째 값과 선택 교환 10 11 13 14 12 그 다음 작은 12를 세번째 값과 선택 교환 10 11 12 14 13 마지막으로 13과 14를 선택 교환 10 11 12 13 14

#### 단순 선택법 알고리즘

1. 탐색 범위의 최소값을 찾는 처리
2. 탐색 범위의 최소값을 맨 앞 요소와 교환

<img src="https://bittestb0341.github.io/assets\img\02_20210916day05.png">

{% highlight python %}
arr = [12,13,11,14,10]

i = 0

while True:
  if i < 4:
    [최소값 찾기]
    [교환]
    i = i + 1
  else:

    
{% endhighlight %}

출력 답:  
{: .notice}

<img src="https://bittestb0341.github.io/assets\img\03_20210916day05.png">

찾은 작은 값과 교환

<img src="https://bittestb0341.github.io/assets\img\04_20210916day05.png">

최종 알고리즘

{% highlight python %}
arr = [12,13,11,14,10]

i = 0

while True:
  if i < 4:
    #[최소값 찾기]
    min = i
    k = i + 1
    while k < 5:
      if arr[k] < arr[min]:
        min = k
      k += 1
    t = arr[i]
    arr[i] = arr[min]
    arr[min] = t
    i = i + 1

  else:
    print(arr)
    break

    
{% endhighlight %}

출력 답:  [10, 11, 12, 13, 14]
{: .notice}

{% highlight python %}
i = 0
arr = [12,13,11,14,10]
while True:
    if i>4:
        print(arr)
        break
    else:
        min = i
        k = i+1

        while True:

            if k < 5:
                if arr[k] < arr[min]:
                    min = k
                    
                else :
                    k = k + 1
                    
            else:
                t = arr[i]
                arr[i] = arr[min]
                arr[min] = t
                i = i+1
                break

{% endhighlight %}

{% highlight python %}
ar=[10,40,5,26,50]
i=0
while i<4:
    min=i
    k= i+1
    while k<5:
        if ar[k]<ar[min]:
            min=k
        k +=1
    t=ar[i]
    ar[i] =ar[min]
    ar[min]=t
    i+=1

print(ar)

{% endhighlight %}
___

#### 단순 교환법 ( bubble sort )

- 단순 교환법은 인접한 데이터를 교환하는 처리를 반복하여 전체를 정렬한다.
- 단순한 알고리즘이지만 실행 속도가 느리다.
- 단순 교환법은 버블 정렬(bubble sort)라고도 한다. 정렬되는 모습이 마치 거품이 수면위에서 움직이는 것처럼 보인다고 해서 붙여진 이름이다.

#### 단순 교환 정렬 알고리즘

1. [5 3 4 1 2] 가장 뒤쪽 두개를 비교한다. 1 2
이미 정렬이 된 상태이므로 그대로 둔다.

2. [5 3 4 1 2] 2를 제외한 4 1 비교한다. 이번엔 정렬하기 위해 교환한다.

3. [5 3 1 4 2] 1과 3을 비교한다. 정렬의 위해 교환한다.

4. [5 1 3 4 2] 1과 5를 비교한다. 정렬의 위해 교환한다. 1 5 3 4 2 최종 1 위치가 확정됐다.

{% highlight python %}

1 5 3 2 4

1 5 2 3 4

1 2 5 3 4     # 2가 확정

1 2 3 5 4     # 3이 확정

1 2 3 4 5     # 4가 확정

1 2 3 4 5     # 5가 확정 -> 전체 확정

{% endhighlight %}

#### 단순 교환법 버블소트 알고리즘

1. 오른쪽 끝 요소부터 순서대로 인접한 데이터를 오름차순으로 교환하여 정렬한다.
2. 왼쪽 끝 요소부터 순서대로 하나씩 데이터를 오름차순으로 정렬된 요소를 확정해나간다.

<img src="https://bittestb0341.github.io/assets\img\05_20210916day05.png">


{% highlight python %}
arr = [5, 3, 4, 1, 2]

i = 4

while True:
  if i > 0:
    if arr[i-1] > arr[i]:
      t = arr[i-1]
      arr[i-1] = arr[i]
      arr[i] = t   

    i = i - 1
    
{% endhighlight %}

출력 답:   
{: .notice}

<img src="https://bittestb0341.github.io/assets\img\06_20210916day05.png">

{% highlight python %}
arr = [5, 3, 4, 1, 2]

k = 0

while True:

  if  k < 4:
    i = 4
    while True:
      if i > k:
        if arr[i-1] > arr[i]:
          t = arr[i-1]
          arr[i-1] = arr[i]
          arr[i] = t   

        i = i - 1
      else:
        k = k + 1
        break

  else:
    print(arr)
    break
    
{% endhighlight %}

출력 답:   [1, 2, 3, 4, 5]
{: .notice}
___

#### 단순 삽입법 ( insertion sort )

1. 올바른 순서가 되도록 데이터를 삽입한다. 다른 이름으로 삽입정렬, 기본삽입법, 삽입법이라고 한다.
2. 요소를 하나씩 차례대로 올바른 위치에 삽입하여 최종적으로 전체를 정렬한다.
3. [5 3 4 1 2] 먼저 제일 왼쪽에 있는 숫자를 정렬이 된상태라고 가정한다. 나머지 4개는 정렬이 안된 상태로 가정한다.
4. [5   3 4 1 2] 아직 아무것도 하지 않은 단계에사 정렬된 공이라고 가정하는 이유는 정렬된 공이 하나도 없으면 대소를 비교할 대상이 없기 때문이다. 따라서 정렬되지 않은 공을 정확한 위치에 삽입할 수 없기 때문에 우선 0번의 데이터를 '정렬되었다'라고 가정한다. 
5.  정렬되지 않은 데이터 중에서 가장 왼쪽의 데이터 부터 정렬된 데이터의 올바른 위치에 삽입하는 방법을 사용한다. 현재 정렬되지 않은 데이터들의 가장 왼쪽에 있는 3 데이터를 정렬된 데이터 즉 5 의 올바른 위치에 삽입한다. 정확한 위치는 5의 앞이 된다. 3을 5의 앞에 삽입한다. 

{% highlight python %}
[3 5 4 1 2]

원래 0번 위치에 있던 데이터 5를 1의 위치로 옮기고 3 데이터를 0번째로 넣는다. 이제 0, 1 번째가 '정렬된 상태'가 되었다.

다음으로 index 2번째에 있는 4 데이터를 '정렬된 데이터' 중에 올바른 위치로 삽입한다.

[3 4 5 1 2]

현재 3 4 5 가 정렬된 상태가 되었다. 1을 올바른 위치에 삽입한다.

[1 3 4 5 2]

[1 2 3 4 5] 최종 정렬이 완성되었다.
{% endhighlight %}

#### 단순 삽입법의 알고리즘
삽입하고 싶은 데이터는 변수를 별도로 준비한다.

변수의 데이터를 정렬된 데이터와 순서대로 비교한다. 변수의 데이터보다 작은 데이터가 발견되면 그 뒤의 요소에 변수의 데이터를 삽입한다.

### 문제

알고리즘을 보고 파이썬 코드를 입력하시오.
<br>
<img src="https://bittestb0341.github.io/assets\img\07_20210916day05.png">

{% highlight python %}
arr = [5, 3, 4, 1, 2]
i = 1

while True:
  if i < 5:
    x = arr[1] 
    k = 1
    if arr[k-1] > x:
      arr[k] = arr[k-1] 
      k = k-1
      arr[k] = x
  else:
    print(arr)
    break
{% endhighlight %}

설명: arr0 과 arr[1] 의 교환은 잘 이루어졌다.
arr[1] arr[2]을 비교한다. arr[i](i == 2) arr[2]의 데이터를 변수 x에 대입한다. i -> k 즉 k 에 2를 대입하여 arr[2] 빈요소가 되었다.
그 다음은 x 에 대입한 4 arr[1]의 5를 비교한다. 이 둘을 비교하면 5 크기 때문에 5를 하나 뒤로 이동해야 한다.
5을 이동하고나면 arr[k-1] (현재 k==2)를 빈요소로 지정하기 위해서 k-1 -> k로 처리한다. k가 2에서 1로 되어 빈요소가 arr[2] arr[1]로 바뀌었다. 그러나 여기서 문제가 발생한다.
k-1 -> k == 1의 다음의 처리가 아직 x -> array[k]로 되어있다. 이런 상태라면 아직 x 와 arr[0]의 비교처리가 끝나지 않았음에도 arr[1]에 x의 데이터 4가 대입된다.
k - 1 -> k k가 1이 된 후에는 다시 arr[k-1] > x 의 비교처리로 되돌아가 arr[0] 과 x를 비교할 수 있도록 반복 구조를 만들어야 한다. 반복 구조는 종료 조건을 필요로 한다. 여기서는 k 값을 확인하자.
k 가 빈요소의 첨자를 나타낸다. k가 2,1, 0의 순서로 하나씩 줄어든다. k가 0이 된다는 것은 빈요소 arr[k]가 맨앞의 요소 arr[0]이라는것을 의미한다. 더이상의 요소가 존재할수 없다.
이와는 반대로 k가 0보다 큰 공안에는 앞의 요소의 비교처리를 계속 반복해야 한다. 따라서 조건식은 k > 0로 정하여 Yes의 경우는 k를 1개씩 앞으로 이동하면서 (k-1->k)비교 처리를 반복 실행하자. No 인경우는 x의 데이터를 arr[k]에 대입한다.
{: .notice}

<img src="https://bittestb0341.github.io/assets\img\08_20210916day05.png">
<img src="https://bittestb0341.github.io/assets\img\09_20210916day05.png">

{% highlight python %}
arr = [5, 3, 4, 1, 2]
i = 1

while True:
  if i < 5:
    x = arr[i] 
    k = i
    while True:
      if arr[k-1] > x and k > 0:
        arr[k] = arr[k-1] 
        k = k - 1
      else:
        arr[k] = x
        i += 1
        break
  else:
    print(arr)
    break
{% endhighlight %}

출력 답:   [1, 2, 3, 4, 5]
{: .notice}

#### 단순 삽입법 ( insertion sort )

단순 삽입볍은 요소를 하나씩 차례대로 올바른 위치에 삽입함으로 전체를 정렬하는 알고리즘이다. 정렬의 실행 속도는 그다지 빠르지 않기 때문에 데이터가 많은 경우에는 적합하지 않지만 정렬을 하기 전에 데이터가 어느정도 정렬이 되어 있는 상태라면 고속 처리를 기대할 수 있다.

퀵정렬 데이터를 대소 그룹의 둘로 나누어 분해한 후 전체를 정렬하는 알고리즘이다. 실행속도 무지 엄청 빠른 것이 특징이다. 퀵정렬은 대량의 데이터를 정렬할 때 자주 사용된다. 유명한 알고리즘 중에서도 실제로 사용되는 빈도가 가장 높은 중요한 알고리즘이다.

5 3 7 6 8 4 1 2 9
우선 정렬의 기준 데이터를 선택하자. 제일 왼쪽의 '5'를 기준 데이터로 사용한다.

그 기준 데이이터인 5보다 작은 데이터들은 왼쪽으로 5보다 큰 데이터들은 오른쪽으로 배치한다.

3 4 1 2 5 7 6 8 9

5보다 작은 데이터는 모두 5 왼쪽에 위치하고 5보다 큰 데이터는 모두 5 오른쪽에 위치하게 된다. 5는 4의 정착했다. 앞으로 5는 더이상 위치를 변경시키지 않아도 된다. 위치가 정해졌다.

자 이제 5보다 작은 데이터 그룹과 5보다 큰 데이터 그룹에 대해 각각 지금 실행한 정렬과 똑같은 작업을 수행한다.

7 6 8 9

6 7 8 9

1 2 3 4

1 2 3 4 5 6 7 8 9

퀵정렬 알고리즘

기준값을 경계로 데이터를 대소로 나누기
나눈 데이터에 반복적으로 또같은 작업 실행하기
먼저 배열을 준비하자 배열명은 arr 요소수는 9개

0 1 2 3 4 5 6 7 8 [index] 5 4 7 6 8 3 1 2 9 [data]

변수 5개를 준비하자.

left : 제일 왼쪽 요소의 첨자 right: 제일 오른쪽 요소의 첨자 i ; 기준값 보다 큰 요소 k : 기준값 보다 작은 요소 w : 데이터 교환용 변수

우선 left right 에 각각 정렬 범위 맨 앞 요소의 첨자와 마지막 요소의 첨자를 대입한다. 0-> left 8-> right 기준값은 맨 앞 요소로 하기 때문에 left를 사용해서 arr[left]라고 표현한다. i에는 left의 하나 오른쪽에 해당하는 첨자 (left+1)를 대입하고 k에 right을 대입하자.

{% highlight python %}
기준  i                  k
5     4 7 6 8 3 1 2      9  [data]
left                     right
{% endhighlight %}

변수 i를 사용해서 기준값보다 큰 요소를 찾자

i는 기준값5 보다 큰 요소를 찾는 변수다. 현재 위치에서 하나씩 오른쪽으로 이동하면서 기준값보다 큰 요소가 있는지 확인하고 거기서 멈춘다.찾을때는 조건식을 사용한다.

arr[i] > arr[left]

i 가 오른쪽 끝에 도달 하는 시점에서 반복을 종료한다.

5 4 7 6 8 3 1 2 9 - - 기준인 5보다 큰 7을 찾았고 5보다 작은 2를 찾았다. 이 두데이터를 교환한다.

5 4 2 6 8 3 1 7 9

5 4 2 6 8 3 1 7 9 - - 5 4 2 1 8 3 6 7 9 - - 5 4 2 1 3 8 6 7 9

4 2 1 3 5 8 6 7 9

나누어진 데이터에 다시 한번 같은 처리를 실행한다.

퀵 정렬은 똑같은 처리를 반복함으로 데이터를 정렬하는 알고리즘이다.

4 2 1 3 5 8 6 7 9

2 1 3 4 7 6 8 9

1 2 6 7

1 2 3 4 5 6 7 8 9

{% highlight python %}
def Quick_sort(a):
  n = len(a)
  if n <= 1:
    return a
  
  pivot = a[-1]  

  a_left = []
  a_right = []

  for i in range(0, n-1):
    if a[i] <= pivot:
      a_left.append(a[i])
    else:
      a_right.append(a[i])
  return Quick_sort(a_left) + [pivot] + Quick_sort(a_right)


a = [5, 4, 7, 6, 8, 3, 1, 2, 9]
Quick_sort(a)
{% endhighlight %}

출력 답:   
[5]
[5, 4]
[5, 4, 7]
[5, 4, 7, 6]
[5, 4, 7, 6, 8]
[5, 4, 7, 6, 8, 3]
[5, 4, 7, 6, 8, 3, 1]
[5, 4, 7, 6, 8, 3, 1, 2]
[5]
[5, 4]
[5, 4, 7]
[5, 4, 7, 6]
[5, 4, 7, 6, 8]
[5, 4, 7, 6, 8, 3]
[1]
[5]
[5, 4]
[5, 4, 7]
[5, 4, 7, 6]
[5, 4, 7, 6, 8]
[5]
[5, 4]
[5, 4, 7]
[5, 4, 7, 6]
[5]
[5, 4]
[7]
[5]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
{: .notice}
___