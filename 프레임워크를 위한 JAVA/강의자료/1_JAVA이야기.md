# 프레임워크를 위한 JAVA

## JAVA 이야기

1. JAVA 개발환경
- JDK
  JVM 필요 => 실행환경 : JRE  : java 
  JRE+개발툴 => 개발환경 : JDK  : java + javac

  최소 8버전 이상을 설치

  https://www.oracle.com/java/technologies/javase-downloads.html#JDK16

  https://jdk.java.net/16/

  path 설정

**(숙제) 직접 JAVA 개발환경 꾸미기**



2. Build Tool

- 자동으로빌드해주고 실행해주는 그런 툴을 만들면 좋겠다.
- Build Tool : Ant, Maven, Gradle
- https://gradle.org

- gradle init 으로 프로젝트를 생성
- gradle tasks 로 태스크 목록 확인
- gradle build 로 빌드
- gradle run 으로 실행

**(숙제) 직접 Gradle 설치하기**



3. IDE : 통합 개발 환경
- 자바개발자들이 주로 사용하는 IDE : Eclipse, IntelliJ
- https://www.jetbrains.com/ko-kr/idea/

- 유용한 단축키
- Alt+Enter | Option+Enter     : 빠른 수정
- Ctrl+1    | Command+1        : 폴더창으로 커서 이동
- Ctrl+N    | Command+N        : 새파일 생성
- Shift+Shit                   : 파일이름 검색
- Alt+Up/Down | Option+Up/Down : 단계별 블럭 지정
- Ctrl+/      | Command+/      : 주석 토글
- Ctrl+Alt+L  | Command+Option+L : 코드 리포맷팅
- Shift+Ctrl+Alt+T | Ctrl+T      : 리팩토링 메뉴
- Shift+Ctrl+A  | Shift+Command+A : 명령어 검색
- IntelliJ Cheat Sheet

**(숙제) IntelliJ 설치하기**



4. 초보개발자가 알면 좋을 정보

(1) Coding Convention
- 팀이나 회사나 개발 그룹에서 정해서 사용합니다.
- 안 정하는 경우 => 일반적인 자바 코딩 룰을 따릅니다.
  
- 클래스명은 대문자로 시작한다.

class myClass {}   // (X)
class MyClass {}   // (O)

class My_Class {}  // (X)

- 메소드나 변수명은 소문자로 시작한다.

int my_variable = 0;   // (X)
int myVariable = 0;    // (O)

void GoHome() {}     // (X)
void goHome() {}     // (O)

- Indent : 들여쓰기 
  - Tab, Space
  - 섞어서 쓰면 안됩니다.


(2) Reference
- java에서는 alloc/free 를 개발자가 일일이 신경쓰지 않아도 된다. (O)
- Java를 하면 포인터를 몰라도 된다. (X)
- Java에서는 포인터 대신 레퍼런스라는 개념이 있습니다.
- Java 에서는 모든것이 레퍼런스 값 입니다.
  - 몇 개 빼구요.
  - 8개 primitive
  - boolean, byte, int, short, long, float, double, char
  - array 는 reference로 취급합니다.

- Call by value / Call by reference


(3) Constant Pool
- String 을 특별하게 취급합니다. / Constant Pool을 이용하죠.
- String 에 대해서는 += 연산을 사용하지 말자
- StringBuffer를 사용하자.
- cf) StringBuilder 가 있는데
  
**(숙제) StringBuilder와 StringBuffer는 무슨 차이가 있는가?**


(4) Object
- 모든 객체의 최상위 객체 입니다.
- 모든 객체에는 Object의 메소드를 호출할 수가 있다는 말.
- Object에 어떤 메소드가 있는지, 어떤 기능을 수행하는지.
- toString()
- equals()
- hashCode()

**스스로 학습하시길 바랍니다.**


(5) Git
- git을 사용하는 것이 기본기.
- 명령어로 익히실 필요는 없습니다. 
  - 어떻게 사용하는지.
  - Tool 을 사용해서 활용하면 됩니다.
  - https://desktop.github.com
  - https://www.sourcetreeapp.com

- .gitignore 잘 활용해 줬으면 좋겠다.
  - 포함되지 않아야 할 파일들이 잔뜩 있다면, 감점요소.
  - 빌드결과. 바이너리. 제너레이트 가능한 파일들. 로컬설정. 키/보안관련 파일들
  - *.class, *.jar, build/

- 안올려도 되는 파일들을 .gitignore 파일에 기록해서 관리하는 것이 좋습니다.
- http://gitignore.io/



