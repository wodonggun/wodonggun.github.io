---
layout: post
title: "Algorithm library C++ STL 정리"
subtitle: <span class="evidence">알고리즘 라이브러리 정리
date: 2018-08-03
author: NoonGam
category: Algorithm
tags: C 백준알고리즘 SW_expert
comments: true
finished: true
---



## Vector 벡터 라이브러리

>

<fieldset id="gpg-fieldset">
vector 컨테이너는 대표적인 시퀀스 컨테이너로 배열과 비슷하여 사용이 쉬우며 자주 사용된다.
vector는 임의 접근 반복자(Random Access Iterator)를 지원하는 배열 기반 컨테이너이다.
vector의 가장 큰 특징 중 하나는 원소가 하나의 메모리 블록에 연속하게 저장된다는 것이다.
그렇다 보니 원소가 추가되거나 삽입될 때 메모리 재할당이 발생할 수 있고 상당한 비용을 지불하게 된다.
그래서 메모리 할당 크기를 알 수 있게 capacity() 함수를 제공하며 한번에 메모리를 할당할 수 있는 reserve() 함수도 제공된다.
원소가 연속하게 저장되므로 [] 연산자 또는 at 으로 읽기에는 빠르지만  insert(), erase(), push_back() 등은 비효율적으로 동작한다.

</fieldset>

<p><table class="txc-table" width="614" cellspacing="0" cellpadding="0" border="0" style="border:none;border-collapse:collapse;;font-family:돋움;font-size:12px"><tbody><tr><td style="width: 613px; height: 24px; border: 1px solid rgb(204, 204, 204); background-color: rgb(217, 229, 255);" colspan="2" rowspan="1"><p style="text-align: left;"><b>템플릿 형식</b></p></td>

</tr>
<tr><td style="width: 340px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; template&lt;typename T, typename Allocator = allocator&lt;T&gt;&gt;</p><p>class vector</p></td>
<td style="width: 273px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>T는 vector 컨테이너 원소의 형식&nbsp; </p></td>
</tr>
</tbody></table></p><p><br /></p><p><br /></p><p><table class="txc-table" width="614" cellspacing="0" cellpadding="0" border="0" style="border:none;border-collapse:collapse;;font-family:돋움;font-size:12px"><tbody><tr><td style="width: 613px; height: 24px; border: 1px solid rgb(204, 204, 204); background-color: rgb(217, 229, 255);" colspan="2" rowspan="1"><p><b>생성자&nbsp; </b></p></td>

</tr>
<tr><td style="width: 151px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; vector v</p></td>
<td style="width: 462px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v는 빈 컨테이너이다.&nbsp; </p></td>
</tr>
<tr><td style="width: 151px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; vector v(n)</p></td>
<td style="width: 462px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v는 기본값으로 초기화된 n개의 원소를 갖는다.&nbsp; </p></td>
</tr>
<tr><td style="width: 151px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; vector v(n,x)</p></td>
<td style="width: 462px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v는 x 값으로 초기화된 n개의 원소를 갖는다.&nbsp; </p></td>
</tr>
<tr><td style="width: 151px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; vector v(v2)</p></td>
<td style="width: 462px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v는 v2 컨테이너의 복사본이다.(복사 생성자 호출)&nbsp; </p></td>
</tr>
<tr><td style="width: 151px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; vector v(b,e)</p></td>
<td style="width: 462px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v는 반복자 구간 [b,e)로 초기화된 원소를 갖는다.&nbsp; </p></td>
</tr>
</tbody></table></p><p><br /></p><p><br /></p><p><table class="txc-table" width="614" cellspacing="0" cellpadding="0" border="0" style="border:none;border-collapse:collapse;;font-family:돋움;font-size:12px"><tbody><tr><td style="width: 613px; height: 24px; border: 1px solid rgb(204, 204, 204); background-color: rgb(217, 229, 255);" colspan="2" rowspan="1"><p><b>멤버함수&nbsp; </b></p></td>

</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; v.assign(n,x)</p></td>
<td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v에 x 값으로 n개의 원소를 할당한다.&nbsp; </p></td>
</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; v.assign(b,e)</p></td>
<td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>&nbsp; v를 반복자 구간 [b,e)로 할당한다.</p></td>
</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; v.at(i)</p></td>
<td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v의 i번째 원소를 참조한다.&nbsp; </p></td>
</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; v.back()</p></td>
<td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v의 마지막 원소를 참조한다.&nbsp; </p></td>
</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; p=v.begin()</p></td>
<td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>p는 v의 첫 원소를 가리키는 반복자&nbsp; </p></td>
</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; x=v.capacity()</p></td>
<td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>x는 v에 할당된 공간의 크기&nbsp; </p></td>
</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; v.clear()</p></td>
<td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v의 모든 원소를 제거한다.&nbsp; </p></td>
</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; v.empty()</p></td>
<td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>v가 비었는지 조사한다.&nbsp; </p></td>
</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);"><p>&nbsp; p=v.end()</p></td>
<td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);"><p>p는 v의 끝을 표식하는 반복자&nbsp; </p></td>
</tr>
<tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1">
  &nbsp; p=v.erase(p)</td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1"><p>p가 가리키는 원소를 제거한다. q는 다음 원소를 가리킨다.&nbsp; </p></td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1">&nbsp; q=v.erase(b,e)</td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1"><p>반복자 구간 [b,e)의 모든 원소를 제거한다. q는 다음 원소&nbsp; </p></td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1"><p>&nbsp; v.front()</p></td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1">v의 첫 번째 원소를 참조한다.&nbsp; </td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1">&nbsp;  q=v.insert(p,x)</td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1"><p>p가 가리키는 위치에 x 값을 삽입한다. q는 삽입한 원소를 가리키는 반복자다.&nbsp; </p></td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1"><p>&nbsp;  v.insert(p,n,x)</p></td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1">p가 가리키는 위치에 n개의 x 값을 삽입한다.&nbsp; </td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1">&nbsp;  v.insert(p,b,e)</td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1"><p>p가 가리키는 위치에 반복자 구간 [b,e)의 원소를 삽입한다.&nbsp; </p></td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1">&nbsp; x=v.max_size()</td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1"><p>x는 v가 담을 수 있는 최대 원소의 개수(메모리의 크기)&nbsp; </p></td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1"><p>&nbsp; v.pop_back()</p></td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1">v의 마지막 원소를 제거한다.&nbsp; </td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1">&nbsp; v.push_back()</td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1">v의 끝에 x를 추가한다.&nbsp; </td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1"><p>&nbsp; p=v.rbegin()</p></td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1">p는 v의 역 순차열의 첫 원소를 가리키는 반복자다.&nbsp; </td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1">&nbsp; p=v.rend()</td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1"><p>p는 v의 역 순차열의 끝을 표식하는 반복자&nbsp; </p></td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1">&nbsp; v.reserve(n)</td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1">n개의 원소를 저장할 공간을 예약한다.&nbsp; </td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1"><p>&nbsp; v.resize(n)</p></td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1"><p>v의 크기를 n으로 변경하고 확장되는 공간의 값을 기본값으로 초기화 한다.&nbsp; </p></td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1"><p>&nbsp; v.resize(n,x)</p></td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1">v의 크기를 n으로 변경하고 확장되는 공간의 값을 x 값으로 초기화한다.&nbsp; </td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1">
  v.size()</td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1">v의 원소 갯수</td></tr><tr><td style="width: 167px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204); border-left-width: 1px; border-left-style: solid; border-left-color: rgb(204, 204, 204);" rowspan="1"><p>&nbsp; v.swap(v2)</p></td><td style="width: 446px; height: 24px; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: rgb(204, 204, 204); border-right-width: 1px; border-right-style: solid; border-right-color: rgb(204, 204, 204);" rowspan="1">v와 v2를 swap한다.&nbsp; </td></tr></tbody></table></p><p><br /></p><p><br /></p><p><table class="txc-table" width="614" cellspacing="0" cellpadding="0" border="0" style="border:none;border-collapse:collapse;;font-family:돋움;font-size:12px"><tbody><tr><td style="width: 613px; height: 24px; border: 1px solid rgb(204, 204, 204); background-color: rgb(217, 229, 255);" colspan="2" rowspan="1"><p><b>연산자&nbsp; </b></p></td>

</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; v1==v2</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>v1과 v2의 모든 원소가 같은가? (bool)&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; v1!=v2</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>v1과 v2의 모든 원소 중 하나라도 다른 원소가 있는가?&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; v1&lt;v2</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>문자열 비교처럼 v2가 v1보다 큰가?&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; v1&gt;v2</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>문자열 비교처럼 v1이 v2보다 큰가?&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; v[i]</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>v의 i번째 원소를 참조한다.&nbsp; </p></td>
</tr>


</tbody></table></p><p><br /></p><p><br /></p><p><table class="txc-table" width="614" cellspacing="0" cellpadding="0" border="0" style="border:none;border-collapse:collapse;;font-family:돋움;font-size:12px"><tbody><tr><td style="width: 613px; height: 24px; border: 1px solid rgb(204, 204, 204); background-color: rgb(217, 229, 255);" colspan="2" rowspan="1"><p><b>멤버 형식</b>&nbsp; </p></td>

</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; allocator_type</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>&nbsp; 메모리 관리자 형식&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; const_iterator</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>&nbsp; const 반복자 형식&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; const_pointer</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>&nbsp; const value_type* 형식&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; const_reference</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>&nbsp; const value_type&amp; 형식&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; const_reverse_iterator</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>&nbsp; const 역 반복자 형식&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; difference_type</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>&nbsp; 두 반복자 차이의 형식&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; iterator</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>&nbsp; 반복자 형식&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; pointer</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>&nbsp; value_type* 형식&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;"><p>&nbsp; reference</p></td>
<td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;"><p>&nbsp; value_type&amp; 형식&nbsp; </p></td>
</tr>
<tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;" rowspan="1">&nbsp; reverse_iterator</td><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;" rowspan="1"><p>&nbsp; 역 반복자 형식&nbsp; </p></td></tr><tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;" rowspan="1">&nbsp; size_type</td><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;" rowspan="1">&nbsp; 첨자(index)나 원소의 개수 등의 형식&nbsp; </td></tr><tr><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;border-left:1px solid #ccc;;" rowspan="1"><p>&nbsp; value_type</p></td><td style="width:307;height:24;border-bottom:1px solid #ccc;border-right:1px solid #ccc;;" rowspan="1">&nbsp; 원소의 형식&nbsp; </td></tr></tbody></table></p><p><br /></p>


<br><br><br>

## Vector 정리 및 요약

> 벡터는 앞쪽이 막혀있는 구조로, FILO스택구조와 비슷하다고 생각하면 된다. 즉, 원소 제거는 맨 마지막에 넣은 것과 빼는 것만 가능하다.
(ex: vec.push_back();   vec.pop_back();)


- Vector와 Stack 함수 차이

![img](/img/0-Algorithm/2018-08-03-Algorithm library C++ STL 정리/vector_stack.gif)





- ```push_back(element)``` : end에 요소를 추가

insert(v.begin()+3, element) : 3번째 인덱스에 요소를 추가, 그 뒤의 요소는 뒤로 밀림

### 삭제

- ```pop_back()``` : end에 있는 요소를 삭제
q = erase(v.begin()+3) : 3번째 인덱스의 요소 삭제, q는 다음번 요소를 가리킴
clear() : 벡터의 모든 요소 삭제


### 조회
- ```at(index)``` : index에 있는 요소를 반환
- ```begin(), end()``` : 각각 첫 번째와 마지막 포인터 반환


### 기타
- ```empty()``` : 벡터가 비어있으면 true 아니면 false를 반환
- ```size()``` : 벡터 사이즈를 반환

<br><br><br>
## stack

추가 및 삭제

- ```push(element)``` : top에 요소를 추가
- ```pop()``` : top에 있는 요소를 삭제

조회

- ```top()``` : top(스택의 처음이 아닌 가장 끝)에 있는 요소를 반환

기타

- ```empty()``` : 스택이 비어있으면 true 아니면 false를 반환
- ```size()``` : 스택 사이즈를 반환





<br><br><br>

## 참고 자료
* [wnsgml972님의 깃허브]( https://github.com/wnsgml972/algorithm-study/blob/master/contents/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0_algorithm-%ED%97%A4%EB%8D%94-%EC%A0%95%EB%A6%AC.md)
* [개발이 하고싶어요 블로그] ( http://hyeonstorage.tistory.com/324#recentComments)
