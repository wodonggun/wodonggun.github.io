---
layout: post
title: " -------- "
subtitle: <span class="evidence"> -------- </span>
date: 2018-01-01
author: NoonGam
category: Study
tags: Network Linux
comments: true
finished: true
---



##  ?

1 using namespace std::가 뜻하는 의미를 아는가?
C++ 언어에서는 단일 글로벌 네임스페이스를 제공합니다. 이것은 전역 이름 충돌 문제를 일으킬 수 있습니다. 예를 들어, 이러한 두 C++ 헤더 파일을 참조하십시오.
char func(char);
class String { ... };

// somelib.h
class String { ... };
이러한 정의로, 단일 프로그램 내에서 두개의 헤더 파일 사용이 불가능합니다; String 클래스가 충돌하게 됩니다.
네임스페이스는 추가 식별자를 자신 안에 선언된 임의의 이름에 연결하는 선언 영역입니다. 추가 식별자는
이름이 프로그램의 다른 곳에서 선언된 이름과 충돌할 가능성을 줄여 줍니다. 이름이 동일한 번역 단위에
나타나더라도 충돌 없이 별도의 네임스페이스에 같은 이름을 사용하는 것이 가능합니다. 별도의 네임스페이스에
나타나는 경우 네임스페이스 식별자가 추가되므로 각 이름은 고유합니다. 예를 들면 다음과 같습니다.
namespace one {
   char func(char);
   class String { ... };
}

// somelib.h
namespace SomeLib {
   class String { ... };
}
이제 클래스 이름이 각각 one::String와 SomeLib::String가 되기 때문에 충돌하지 않습니다.
C++에서는 네임스페이스에 복합 이름을 허용하지 않습니다.
// pluslang_namespace.cpp
// compile with: /c
// OK
namespace a {
   namespace b {
      int i;
   }
}

// not allowed
namespace c::d {   // C2653
   int i;
}
모든 네임스페이스 밖에 있는 변환 단위의 파일 범위의 선언은 여전히 전역 네임스페이스의 멤버입니다.
Using = 네임스페이스를 따로 범위를 지정하지않아도 자동으로 사용가능
Std::cin  cin

Namespace = 클래스







<br><br><br>

## data sniffing





<br><br><br>

## 예시







<br><br><br>

## 참고 자료
*
*
*
<fieldset id="gpg-fieldset">
 샘플 파일
</fieldset>
