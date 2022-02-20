---
layout: post
title: Go 언어로 읽는 클린 코드 2장 - 의미 있는 이름
categories:
  - books
tags:
  - 노개북
  - 클린 코드
sharing:
  twitter: Go 언어로 읽는 클린 코드 2장 - 의미 있는 이름 #코딩 #개발자 #노마드북클럽 #노개북
---

클린 코드, 애자일 소프트웨어 장인 정신: Day 02 - 의미 있는 이름

> Java 언어를 기반으로 쓰여진 이 책의 내용들을 어떻게 Go 언어에 적용할 수 있을까를 고민하며 읽었습니다.

## 😀 책에서 기억하고 싶은 내용을 써보세요.

"의미 있게 구분하라" (p.25)

"한 개념에 한 단어를 사용하라" (p.33)

"집중적인 탐구가 필요한 코드가 아니라 대충 훑어봐도 이해할 코드 작성이 목표다. 의미를 해독할 책임이 독자에게 있는 논문 모델이 아니라 의도를 밝힐 책임이 저자에게 있는 잡지 모델이 바람직하다." (p.34)

"해법 영역에서 가져온 이름을 사용하라 (중략) VISITOR 패턴에 친숙한 프로그래머는 AccountVisitor라는 이름을 금방 이해 한다. JobQueue를 모르는 프로그래머가 있을까? 프로그래머에게 익숙한 기술 개념은 아주 많다. 기술 개념에는 기술 이름이 가장 적합한 선택이다." (p.34)

"의미 있는 맥락을 추가하라. 클래스, 함수, 이름 공간(namespace)에 넣어 맥락을 부여한다. 모든 방법이 실패하면 마지막 수단으로 접두어를 붙인다." (p.35)

"맥락을 개선하면 함수를 쪼개기가 쉬워지므로 알고리즘도 좀 더 명확해진다." (p.36)

## 🤔 오늘 읽은 소감은? 떠오르는 생각을 가볍게 적어보세요.

코드에 의미와 맥락을 제공하는 것이 얼마나 중요한지 볼 수 있었다. 그리고 그 의미와 맥락을 제대로 제공하고 나누기 위해서는 코드를 작성하기 전에 구현하고자 하는 것이 무엇인지 정확하게 파악하는게 더 중요하다는 생각이 들었다. 최근 들었던 조언 중에 구현을 늦출 수 있으면 정말 필요하다고 생각이 될 때까지 최대한 늦춰라라는 것이었다. 너무 많은 것을 한 번에 구현하려다 보면 여러 기능을 실행하려고 하는 키메라 함수를 만들 수 있기 때문이다. 필요한 기능들을 최대한 작은 단위로 쪼개고 각 의미에 맞게 추상화하여 클래스와 함수로 구현해야 할 것 같다.

## 👀 소감 3줄 요약

- 리팩토링할 것은 코드가 아니라 코드에 담긴 의미일 수도 있다. 코드가 하고자 하는 것이 명확해지면 각 함수와 변수는 각각의 의미를 가지게 되고 더 깔끔한 코드가 나올 것이다.
- 해법 영역에서 가져온 이름을 사용하라는 부분에서 많은 개발자들이 시행착오를 거쳐 만들어낸 디자인 패턴을 잘 익혀둬야 다른 개발자의 코드를 읽을 때도 그리고 다른 개발자에게 공유할 때도 편할 것 같다.
- 습관적으로 코드를 짜지 말고 코드가 하고자 하는 기능의 의미를 잘 나타내는지 생각하면서 코드를 짜야겠다.

## Go 언어만의 이름 짓기 규칙

다른 언어들과 달리 Go 언어는 첫 글자가 대문자이냐 소문자이냐에 따라 외부로 내보낼 수 있냐 없냐가 결정된다. 그렇기 때문에 모든 이름은 `mixedCap`이어야 한다 (상수도 예외가 아니다). 그리고 Go 언어는 예외가 없는 대신 에러 처리를 직접 할 수 있다. 그렇기 때문에 에러 처리를 하지 않고 `panic`을 해야 한다면 그 함수 이름을 `Must`로 시작하게 지은 것을 Go 언어 Standard Library에서 볼 수 있다. 이것은 `Effective Go`나 공식 문서에 있지는 않지만 따라서 나쁘지는 않을 것 같은 규칙이다.