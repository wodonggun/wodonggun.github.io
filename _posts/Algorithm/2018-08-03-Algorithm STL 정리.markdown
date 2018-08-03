---
layout: post
title: "Algorithm STL 정리"
subtitle: <span class="evidence">Algorithm STL 헤더 - #include <algorithm> </span>
date: 2018-08-03
author: NoonGam
category: Algorithm
tags: C 백준알고리즘 SW_expert
comments: true
finished: true
---



## Sort 정렬 알고리즘

> 알고리즘 헤더파일에서 제공하는 STL로써 범위내에서 주어진 범위내에서 원소들을 정렬합니다. 이때 정렬하는 방식(오름차순, 내림차순 등등등)은 사용자가 정의할 수 있으며, 동일한 원소에 대해서는 그 순서가 보장되지 않습니다. 이때 std::sort는 숫자 뿐만 아니라 대소 비교가 가능한 모든 원소에 대해서 정렬을 할 수 있습니다. 즉 int 뿐만 아니라 char, string 역시 정렬이 가능합니다.


<br>
<fieldset id="gpg-fieldset">
 <span> 이걸 왜 난 지금까지....시험장에서 구현을 했었을까ㅠㅠ</span>
</fieldset>


<br><br><br>
## 내림차순 예제 (Default)

```c++
#include <stdio.h>
#include <algorithm>

using namespace std;

int main()
{
	int arr[11] = { 0,10,8,6,4,3,1,5,2,9,7 };

	for (int i = 0; i < 11; i++)
		printf("%d ", arr[i]);

	sort(arr,arr+11);

	printf("\n -- 정렬 후 -- \n");

	for (int i = 0; i < 11; i++)
		printf("%d ", arr[i]);
	return 0;
}
```

![img](/img/0-Algorithm/2018-08-03-Algorithm STL 정리/1.PNG)



<br><br><br>

## 오름차순 예제

- 따로 #include <functional> 를 추가하여 greater<int>()를 사용하여야 합니다.

```c++
#include <stdio.h>
#include <functional>
#include <algorithm>

using namespace std;

int main()
{
	int arr[11] = { 0,10,8,6,4,3,1,5,2,9,7 };

	for (int i = 0; i < 11; i++)
		printf("%d ", arr[i]);

	sort(arr,arr+11, greater<int>());

	printf("\n -- 내림차순 정렬 후 -- \n");

	for (int i = 0; i < 11; i++)
		printf("%d ", arr[i]);
	return 0;
}
```


![img](/img/0-Algorithm/2018-08-03-Algorithm STL 정리/2.PNG)


<br><br><br>

## pair 한쌍

> 이름이 'first', 'second'인 두 개의 변수를 저장할 수 있는 구조체 입니다. 사용 용도로는 이차원 배열의 인덱스로 사용할 수도 있으며, 이차원 좌표평면의 좌표를 저장, 또는 A에서 B까지의 어떤 정보를 저장하고자 할때 사용합니다. <br>
ps. 서로다른 자료형의 데이터를 같이 저장할때 편리합니다. (구조체처럼)







```c++
#include <stdio.h>
#include <algorithm>

using namespace std;

int main()
{


	//pair 생성
	pair<int, int> p = make_pair(1, 2);

	pair<int, int> p_tmp;  // 초기화를 시켜주지않으면 모두 0으로 자동으로 초기화(0,0)


	printf("%d ",p.first);
	printf("%d", p.second);
	printf("\n");

	printf("\n=== \n\n");

	pair<int, char> p2 = make_pair(1, 'A');
	printf("%d ", p2.first);
	printf("%c", p2.second);
	printf("\n");

	return 0;
}
```

![img](/img/0-Algorithm/2018-08-03-Algorithm STL 정리/3.png)


<br><br><br>

## 참고 자료
* https://www.acmicpc.net/blog/view/22 [백준 알고리즘]
* http://sarah950716.tistory.com/4 [알고리즘 정복기]
