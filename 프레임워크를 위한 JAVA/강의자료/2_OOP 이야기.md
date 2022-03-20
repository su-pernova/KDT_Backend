# OOP 이야기

## 1. 객체지향 프로그래밍

- JAVA : 객체지향 언어다!
- 객체지향 프로그래밍 : 프로그램을 객체로 구성하는 것.

- 등장 : 프로그램이 거대화 하면서 등장.
- 아이디어 : 어떻게 큰 프로그램을 만들것인가?
  - 해결책 : 작게 나눠서 만들고 합쳐

- 프로그램의 동작을 객체들에게 나눠서 수행.

- 개념적인 용어 : 객체 / 기술적인 용어 : class, instance

- 객체는 작은 기능을 수행.
- 객체와 객체는 서로 협력.
=> 일을 잘게 쪼개서 객체에게 위임하고, 서로 협력하게 만드는 것.

- 객체를 서로 구분할 필요가 있습니다.
  - type(형)으로 구분합니다.
  - `String str = "Hello World"`

- 타입 만들기 : class 만들기
 
```java

package com.programmers;

import java.lang.*;

class MyObject extends Object implements Runnable {
    //필드영역
    private int a = 0;
    //메소드영역
    public void run() {
        a += 1;
    }
}

MyObject obj = new MyObject();
```


## 2. 객체지향의 특성

### (1) 캡슐화

1. 완성도가 있다.
- 기능을 수행하는 단위로써 완전함을 갖는다.
2. 정보가 은닉되어 있다.
- 객체의 정보가 밖에서 접근하거나, 밖에서 객체 내의 정보에 접근하지 못하게 한다.

=> 객체는 스스로 동작할 수 있는 환경을 갖고 있어야 한다.
   외부에 의존하거나, 외부의 침략을 제한하여야 한다.

```java
public class Human {
    private Heart heart;
    private Blood blood;
    protected Gene gene;

    Blood donation() {
        return null;
    }
}
```

* 접근지정자
- private : 객체 소유.
- protected : 상속된 객체에서도 접근 가능.
- (friendly) : 같은 패키지 내에서 접근 가능. (패키지 가시성)
- public : 모두 다 접근 가능.

// com.programmers
// com.programmers.girl
//                   Jane
//                   Secret
// com.programmers.boy
//                   Tom
//                   Secret


### (2) 상속

- 상위, 부모, super, [추상]
- 하위, 자식, (this), [구체]

- **오해**: 공통된 기능을 여러 객체에게 전달하고 싶을 때.
- `원자 > 물질 > 생물 > 동물 > 포유류 > 사람 > 남자 > 짱구`

### (3) 추상화

- 추상화된 객체 : 추상체
- 구체적인 객체 : 구상체
- 객체간의 관계에서 상위에 있는 것이 항상 하위보다 추상적이야 합니다.


```java
// 의미적 추상체
class Login {
    void login() {}
}

class KakaoLogin extends Login {
    void login() {}
}
```

```java
// 추상기능을 가진 객체
abstract class Login {
    abstract void login();
}

class KakaoLogin extends Login {
    void kakao() {}
    @Override void login() {}
}
```

```java
// 객체 자체가 추상적
interface Login {
    void login();
}

class KakaoLogin implements Login {
    void kakao() {}
    @Override void login() {}
}
```

### (4) 다형성

- 형(type)을 여러가지로 표현할 수 있다.

```java
class KakaoLogin implements Login {
    void kakao() {}
    @Override void login() {}
}

interface Portal {
    void portal();
}

class NaverLogin implements Login, Portal {
    void naver() {}
    @Override void login() {}
    @Override void portal() {}
}

KakaoLogin k = new KakaoLogin();
Login k = new KakaoLogin();
```

```java
Login login = new Login();
Login login = new KakaoLogin();
Login login = new NaverLogin();
login.login();

Portal potal = new NaverLogin();
potal.portal();
```

## 3. 객체지향 설계

### (1) UML
- 객체지향 프로그래밍 : 기능을 객체에게 나눠서 수행시킨다.
 => 객체를 어떻게 구분했다.
 => 객체간의 연관관계가 어떠하다.

- 설명하기 위한 도구 : UML 
  - Usecase Diagram
  - Sequence Diagram
  - Package Diagram
  - **Class Diagram**

- Tool
  - https://draw.io
  - https://staruml.io/
  - PowerPoint / Visio
  - 그림판


### (2) 어떻게 하면 객체를 잘 나누고 연관지을 수 있느냐?

- 객체지향 설계를 하는 5가지 원칙
- (1) S : SRP : 수정이 필요할 경우 수정되는 이유는 하나 때문이어야 한다.
- (2) O : OCP : 수정에는 닫히고, 확장에는 열어라.
- (3) L : LSP : 추상객체로 사용되는 부분에 구상객체가 들어가도 아무 문제 없어야 한다.
- (4) I : ISP : 
- (5) D : DIP : 

- 원칙에 따라서 설계를 해본거죠 => 여러가지 경우에서 공통점이 보인거예요.
- 공통점들을 모아놨습니다. => 책 => 디자인패턴
- Design Patterns: Elements of Reusable Object-Oriented Software (1994)
- 23가지 패턴
- https://refactoring.guru/

**(숙제)23가지 패턴에 대해서 정리하시오**
