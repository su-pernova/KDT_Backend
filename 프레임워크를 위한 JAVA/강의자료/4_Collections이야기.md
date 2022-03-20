# Collection 이야기

## Collection

- 여러 데이터의 묶음을 컬렉션이라고 합니다.
- 컬렉션은 추상체 입니다.
- Collection
  - List
    - LinkedList
    - ArrayList
    - Vector
    - Stack
  - Set
    - HashSet

## Iterator

- 여러 데이터의 묶음을 풀어서 하나씩 처리할 수 있는 수단을 제공합니다.
- next()를 통해서 다음 데이터를 조회할 수 있습니다.
- 역으로 움직일 수 없습니다. (이전데이터를 조회할 수는 없습니다.)

## Stream

- Java 8 이상에서 부터 사용 가능합니다.
- 
- 데이터의 연속입니다.
- (System.in / System.out 이것도 스트림 입니다. 이미 우리가 쓰고 있던 겁니다.)
- Collections.stream() 을 제공해줍니다. (Java8)
- filter, map, forEach 같은 고차함수(함수를 인자로 받는 함수)가 제공이 됩니다.

- Stream을 만들때는 Stream.generate 과 Stream.iterate 으로 만들 수 있습니다.
- 스트림을 사용하면 연속된 데이터에 대해서 풍부한 고차함수들을 사용하여
  강력한 기능을 간결하게 표현할 수 있습니다.

- 익숙해지면 굉장히 편리해 집니다.
- 자주 사용해보다보면 익숙해 집니다.


## Optional

- NPE : Null Pointer Exception - 가장 많이 발생하는 에러중의 하나
- 자바에서는 (거의) 모든것이 레퍼런스 ==> (거의) 모든것이 null이 될 수 있다.
- 항상 null을 확인할 필요가 있습니다.

- 이제부터 null을 쓰지마!! ==> 서로 약속! : 계약한다 : 계약을 하고 프로그래밍 한다.

- (1) EMPTY 객체를 사용하는 방법
- (2) Optional을 사용한다.

- Optional
  - null 데이터 : Optional.empty()
  - 데이터 : Optional.of( {DATA} )
  - 확인하는 방법은 : .isEmpty(), .isPresent()

```java
if (optionalUser.isPresent()) {
    /// do 1
} else {
    //// do 2
}

if (optionalUser.isEmpty()) {
    // do 2
} else {
    // do 1
}

optionalUser.ifPresentOrElse(user -> {
    // do 1
}, () -> {
    // do 2
});

optionalUser.ifPresent(user -> {
    // do 1
});
```