# Java

자바 웹 개발 프레임워크인 Spring을 배우기 전에, 자바 언어와 객체 지향 개념의 기본을 탄탄히 다지기 위해 공부했습니다.

아래 내용은 **Do it! 자바 프로그래밍 입문** 도서를 참고하며, 이해한 내용을 바탕으로 기록했습니다.

더욱 자세한 설명을 원하시면 위 책을 직접 읽어보시는 것을 추천드립니다.

---

- 자바는 1991년 제임스 고슬링을 비롯한 선 마이크로시스템스 연구원들이 처음 개발했다.
- 가전제품이나 휴대용 장치 등에 사용하는 소프트웨어를 만들기 위해 **독립적으로 작동하는 더 안정된 프로그래밍 언어**가 필요하여 자바가 만들어졌다.

아래는 자바의 특징을 나열한 것이다.

### 플랫폼에 종속 X

참고) 플랫폼(Platform)이란 프로그램이 실행되는 환경을 뜻한다.

- 자바에서는 .exe의 실행 파일 대신 .class의 확장자를 가진 바이트 코드를 생성
- 생성된 바이트 코드를 **자바 가상 머신**에서 실행하여, 각 운영체제에 맞는 실행 파일 생성
- 이러한 특성은 초반에 프로그램의 실행 속도를 저하시킨 원인이 되었지만, 자바 컴파일러가 JIT 컴파일 방식으로 개선되며 실행 속도가 개선됨

참고) JIT(Just In Time) 컴파일러는 실행 시점에 기계어 코드 생성, 같은 코드 반복일 경우 이전에 만든 기계어 재사용의 특징이 있다.

### 객체 지향 언어

- 객체 지향 프로그래밍이란 일의 순서가 아닌 **여러 객체의 협력(상호 관계)을 통해 프로그램을 구현하는 것**
- 공통으로 사용하는 부분을 수정하지 않고도 새 기능 쉽게 추가 가능
- **유지보수**가 쉽고 **확장성**이 좋은 프로그램이 될 수 있음

### 안정적인 프로그램

- 자바는 포인터 문법을 제공하지 않아 메모리를 직접 제어하지 않음. 그에 따라 오류 위험성을 줄임
- Garbage Collector를 이용해 동적 메모리를 수거하므로 효율적인 메모리 관리가 가능함

### 오픈 소스

- JDK(Java Development Kit)를 가지고 있어 프로그램을 빠르게 개발할 수 있음
- 자바를 활용한 오픈 소스가 많이 개발되어 있기 때문에 그 소스들을 연동하여 더 풍부한 기능을 빠르게 구현할 수 있음 

참고) JDK는 클래스, 자료 구조, 네트워크, 입출력, 예외 처리 등에 최적화된 알고리즘 라이브러리를 제공

---

## 자바 기초

### 변수명 정하기

- 변수명은 사용 목적에 맞게 의미를 부여하여 만들어야 한다.
- 영문자(대소문자)와 숫자를 사용할 수 있고, 특수문자는 $, _ 등만 사용할 수 있다.
- 숫자로 시작할 수 없다.
- 자바에서 이미 사용 중인 예약어는 사용할 수 없다.
- **Camel Notation**이란 중간에 다른 뜻의 단어가 등장하면 첫 글자를 대문자로 사용하는 것이다. (numberOfStudent, isGood)

### 자바 자료형

- 자바에서 제공하는 자료형에는 기본 자료형과 참조 자료형이 있음
- 참조 자료형은 클래스형임

아래는 기본 자료형이다.
- 정수형 : byte(1byte), short(2byte), **int(4byte)**, long(8byte)
- 실수형 : float(4byte), double(8byte)
- 문자형 : char(2byte)
- 논리형 : boolean(1byte)

아래는 자료형의 특징이다.
- long 형은 숫자 뒤에 `L`, `l`의 식별자를 붙여야 한다. 또한 float형은 `F`, `f`를 붙여야 함
- 컴퓨터 내부에서 문자를 표현할 때 특정 정수 값으로 정한다. 코드 값을 모아둔 것을 '문자 세트', 문자를 코드 값으로 변환하는 것을 '문자 인코딩', 그 반대를 '문자 디코딩'이라고 함
- 자바는 유니코드(unicode)에 기반하여 문자를 표현하기 때문에, char형은 2byte를 사용

### 상수

- 상수(constant)는 항상 변하지 않는 값임
- 값 초기화 후에 다시 값 변경 불가
- 상수를 선언할 때 자료형 앞에 `final`을 붙임
- 이름은 주로 대문자를 사용하고, _ 기호를 사용해 여러 단어를 연결함

### 리터럴

- 프로그램에서 사용하는 모든 숫자, 문자, 논리값을 일컫는 말
- 프로그램이 시작할 때 시스템에 같이 로딩되어 constant pool에 놓임
- 이 리터럴은 변수나 상수 값으로 대입할 수 있음

(일반 연산자에 대한 기록은 생략하겠습니다.)

### 비트 연산자

비트 논리 연산자
- `&` : 두 개의 비트 값이 모두 1인 경우에만 1이 됨
- `|` : 하나의 비트만 1이어도 1이 됨
- `^` : 같은 값이면 0, 다른 값이면 1
- `~` : 비트 값이 0이면 1, 1이면 0으로 바꿈

비트 이동 연산자
- `<<` : 왼쪽으로 비트 이동. 왼쪽으로 n비트 이동하면 기존 값에 2의 n제곱만큼 곱함
- `>>` : 오른쪽으로 비트 이동. 오른쪽으로 n비트 이동하면 기존 값을 2의 n제곱만큼 나눔
- `>>>` : 오른쪽으로 비트 이동, 왼쪽에 채워지는 비트 값이 부호 비트와 상관없이 무조건 0이 됨

(제어문과 반복문에 대한 기록은 생략하겠습니다.)

---

## 객체 지향 프로그래밍

- 객체 지향 프로그래밍(Object-Oriented Programming; OOP)은 객체를 기반으로 프로그래밍 하는 것
- 한 마디로, 객체를 만들고 **객체 사이에 일어나는 일을 구현**하는 것
- 우리는 객체를 먼저 정의하고 각 객체가 어떤 기능을 제공할지, 객체 간 협력을 어떻게 구현할 것인지 고민해야 함

### 클래스

- 클래스는 **객체의 속성과 기능**을 코드로 구현한 것
- 클래스는 속성(멤버 변수)과 메서드를 가짐
- 클래스 이름은 대문자로 시작함 (coding convention)

아래는 클래스를 정의하는 문법이다.
```
(접근 제어자) class 클래스 이름 {
  멤버 변수;
  메서드;
}
```

### 멤버 변수 (member variable)

- **객체가 가지는 속성**을 클래스 내부에 변수로 선언한 것
- 멤버 변수(member variable)는 다른 말로 속성(property) 또는 특성(attribute) 등으로 표현함
- 멤버 변수의 자료형은 기본 자료형(int, double ..), 참조 자료형(String, Date, 직접 만든 클래스 ..) 둘 다 가능하다.

참고) 패키지는 클래스 파일의 묶음이다. 패키지는 계층 구조를 가지고, 이 계층 구조를 잘 구성해야 유지 보수가 편리하다.

### 메서드 (method)

- 메서드는 함수에 객체 지향 개념이 포함된 용어
- 멤버 변수를 사용하여 **클래스의 기능**을 구현한 것

아래는 클래스와 내부의 멤버 변수, 메서드를 구현한 코드이다.
```java
public class Student {
    int studentID;
    String studentName;
    int grade;
    String address;

    public String getStudentName() {
        return studentName;
    }

    public void setStudentName(String name) {
        studentName = name;
    }
}
```

### main() 함수

- 클래스를 사용하려면 main() 함수가 있어야 함. 이 main() 함수는 클래스 내부에 만들지만, 클래스의 메서드는 아님
- 자바 가상 머신(JVM)은 프로그램을 시작할 때 main() 함수를 가장 먼저 호출함
- main() 함수는 클래스 내부에 만들어도 되고, 외부에 테스트용 클래스를 만들어 사용해도 됨
- 테스트 클래스와 실제 클래스 파일이 각각 다른 패키지에 있을 경우 import문을 사용해 클래스를 불러와야 함.

### 인스턴스 (instance)
 
- main() 함수에서 클래스를 사용할 때 new 예약어와 생성자를 사용해 클래스를 생성
- 클래스가 생성된다는 것은 클래스를 실제 사용할 수 있도록 힙 메모리를 할당 받는 것임
- 생성된 클래스를 **인스턴스**(혹은 객체)라고 하고, 인스턴스를 가리키는 클래스형 변수를 **참조 변수**라고 함
- 즉, 인스턴스는 클래스가 메모리 공간에 생성된 상태

아래는 new 예약어를 사용하는 방법이다.
```
클래스형 변수명 = new 생성자;
```

- 참조 변수에 도트 연산자(.)를 사용하여 멤버 변수와 메서드를 참조하여 사용 가능
- ```new Student()```와 같이 선언하면 이 인스턴스와 멤버 변수들은 힙 메모리(heap memory)에 저장

아래는 인스턴스를 생성하는 코드이다.
```java
Student studentAhn = new Student();
```
지역 변수 Ahn에 생성된 인스턴스를 대입한다는 것은, studentAhn에 인스턴스가 생성된 힙 메모리의 주소를 대입한다는 것과 같은 의미이다.

참고) 힙(heap)은 프로그램에서 사용하는 동적 메모리(dynamic memory)공간이다. 보통 객체가 생성될 때 사용하는 공간이다.

### 생성자 (constructor)

- 생성자는 클래스를 처음 만들 때 멤버 변수나 상수를 초기화해줌
- 생성자가 없는 클래스는 자바 컴파일러에서 디폴트 생성자(default constructor)를 자동으로 만듦
- 프로그래머가 디폴트 생성자를 직접 만드는 경우 필요에 따라 코드 구현 가능
- 인스턴스가 생성될 때 인스턴스 초기화를 위해 생성자를 직접 구현하기도 함

아래는 클래스 안의 디폴트 생성자를 코드로 구현한 것이다.
```java
public class Person {
  String name;
  float height;
  float weight;
  
  public Person() {}
}
```

### 생성자 오버로드 (constructor overload)

- 생성자 오버로드는 클래스에 생성자가 두 개 이상 제공되는 것
- 필요에 따라 매개변수가 다른 생성자를 여러 개 만들 수 있음
- 경우에 따라 클래스에서 일부러 디폴트 생성자를 제공하지 않기도 함

참고) 객체 지향 프로그램에서 메서드 이름은 같고 매개변수만 다른 경우를 **오버로드**라고 한다.

아래는 생성자 오버로드를 구현한 코드이다.
```java
public class Person {
    String name;
    float height;
    float weight;

    public Person() {}

    public Person(String pname) {
        name = pname;
    }

    public Person(String pname, float pheight, float pweight) {
        name = pname;
        height = pheight;
        weight = pweight;
    }
}
```

### 정보 은닉 (information hiding)

- 객체 지향 프로그램에서는 접근 제어자(access modifier)를 사용해 (클래스 내부 변수, 메서드, 생성자에 대한) **접근 권한**을 지정할 수 있음
- private으로 선언한 멤버 변수는 getter, setter 메서드(public으로 설정)로 접근 가능
- 정보 은닉은 클래스 내부에서 사용할 변수나 메서드를 private으로 선언하여 외부에서 직접 접근하지 못하도록 하는 것
- 정보 은닉은 객체 지향 프로그래밍의 특징

|접근 제어자|설명|
|-----|-----|
|public|외부 클래스 어디서나 접근 가능|
|protected|같은 패키지 내부와 상속 관계의 클래스에서만 접근 가능|
|아무것도 없는 경우|default이며 같은 패키지 내부에서만 접근 가능|
|private|같은 클래스 내부에서만 접근 가능|

### this 예약어

- this는 생성된 인스턴스 스스로를 가리키는 예약어
- this는 동적 메모리에 생성된 인스턴스의 위치를 직접 가리킴
- 또한 this는 생성자에서 다른 생성자를 호출할 수 있음 (이때 호출 코드 이전에 다른 코드를 넣으면 오류 발생)
- this를 활용해 생성된 클래스 자신의 주소값을 반환할 수 있음

### static 변수

- static 변수는 정적 변수 혹은 클래스 변수(class variable)라고도 함
- static 변수는 클래스에서 공통으로 사용하는 변수, 즉 프로그램이 실행되어 메모리에 올라갔을 때 한 번 메모리 공간이 할당되고, 그 후 모든 인스턴스가 공유하는 변수
- 자바에서는 다른 멤버 변수처럼 클래스 내부에, static 예약어를 사용하여 선언

아래는 static의 사용법이다.
```
static 자료형 변수명;
```

아래처럼 class 안에 static 예약어를 사용하여 선언한다.
```java
public class Student {
    public static int serialNum = 1000;
    public int studentID;
    public String studentName;
}
```

- static 변수는 인스턴스 생성과는 별개이므로 **인스턴스보다 먼저 생성**
- 따라서 static 변수는 클래스 이름으로도 참조하여 사용 가능 (보통 클래스 이름과 함께 사용)
- static 변수를 위한 메서드를 static 메서드 또는 클래스 메서드(class method)라고 함
- static 메서드 또한 static 변수처럼 클래스 이름으로 직접 호출 가능

아래는 static 메서드를 구현한 코드이다.

```java
public class Student2 {
    private static int serialNum = 1000;
    int studentID;
    String studentName;
    int grade;
    String address;

    public Student2() {
        serialNum++;
        studentID = serialNum;
    }

    public static int getSerialNum() {
        int i = 10;
        return serialNum;
    }

    public static void setSerialNum(int serialNum) {
        Student2.serialNum = serialNum;
    }
}
```

- static 메서드 내에서 지역 변수와 클래스 변수는 사용할 수 있지만, 인스턴스 변수를 사용하면 오류가 발생함

### 변수 유효 범위 (scope)

- 변수는 특성에 맞게 선언해서 사용하는 것이 중요함
- 지역 변수(local variable) : 함수/메서드 내부에서 선언하기 때문에 함수 밖에서는 사용 불가
- 멤버 변수(member variable) : 클래스의 어느 메서드에서나 사용 가능
- static 변수 : private이 아니라면 클래스 외부에서도 객체 생성과 무관하게 사용 가능

|변수 유형|선언 위치|사용 범위|메모리|생성과 소멸|
|--------|--------|---------|------|---------|
|지역 변수|함수 내부에 선언|함수 내부에서만 사용|스택|함수가 호출될 때 생성되고 함수가 끝나면 소멸|
|멤버 변수|클래스 멤버 변수로 선언|클래스 내부에서 사용, private이 아니면 다른 클래스에서 접근 가능|힙|인스턴스가 생성될 때 힙에 생성, 가비지 컬렉터가 메모리 수거 시 소멸|
|static 변수|static 예약어를 사용하여 클래스 내부에 선언|클래스 내부에서 사용, private이 아니면 클래스 이름으로 다른 클래스에서 사용 가능|데이터 영역|프로그램 시작 시 데이터 영역에 생성, 프로그램 종료와 메모리 해제 시 소멸|

- static 변수는 프로그램 시작부터 끝까지 메모리에 상주하므로, 크기가 너무 큰 변수를 static으로 선언하는 것은 좋지 않음
- 지역 변수 -> 함수에서 기능 구현을 위해 잠시 사용할 때
- 멤버 변수 -> 클래스의 속성을 나타내고, 각 인스턴스마다 다른 값을 가질 때
- static 변수 -> 여러 인스턴스에서 공유해서 사용, 한 번만 생성

### 싱글톤 패턴 (singleton pattern)

- 싱글톤 패턴은 객체 지향 프로그램에서 **인스턴스를 단 하나**만 생성하는 디자인 패턴
- 실무 혹은 여러 프레임워크에서 많이 사용하는 패턴

참고) 디자인 패턴(design pattern)이란 객체 지향 프로그램을 어떻게 구현해야 더 유연하고 재활용성이 높은 프로그램을 만들 수 있는지 정리한 내용이다. 다시 말해, 프로그램 특성에 따른 설계 유형을 이론화한 것이다.

#### 1단계 : 생성자를 private으로 만들기
- private으로 디폴트 생성자를 명시하여, 외부 클래스에서 마음대로 인스턴스를 여러 개 생성하는 것을 막기 위해 
- 클래스 내부에서만 해당 클래스의 생성을 제어할 수 있음
```java
public class Company {
    private Company() {}
}
```

#### 2단계 : 클래스 내부에 static으로 유일한 인스턴스 생성
- 이 인스턴스가 프로그램 전체에서 사용할 유일한 인스턴스
- 유일한 인스턴스를 private으로 선언하여 인스턴스 오류 방지
```java
public class Company {
    private static Company instance = new Company();
    private Company() {}
}
```

#### 3단계 : 외부에서 참조 가능한 public 메서드 만들기
- 외부 사용이 가능하도록, 유일하게 생성한 인스턴스를 반환하는 public 메서드 생성
- 이때 인스턴스 생성과 상관없이 호출할 수 있어야 하기 때문에, 인스턴스 반환하는 메서드는 반드시 static으로 선언
```java
public class Company {
    private static Company instance = new Company();
    private Company() {}
    
    public static Company getInstance() {
        if(instance == null) {
            instance = new Company();
        }
        return instance;
    }
}
```

#### 4단계 : 클래스를 실제 사용하는 코드 만들기
- 외부 클래스에서는 객체를 생성할 수 없으므로, static으로 제공되는 getInstance() 메서드를 호출
```java
public class CompanyTest {
    public static void main(String[] args) {
        Company myCompany1 = Company.getInstance();
        Company myCompany2 = Company.getInstance();
        System.out.println(myCompany1 == myCompany2);
    }
}
```

### 배열

- 배열을 사용하면 자료형이 같은 자료 여러 개를 한 번에 관리 가능
- 배열 요소들은 자료형이 모두 같다.

아래는 배열의 선언 방법이다.
```
자료형[] 배열이름 = new 자료형[개수];
자료형 배열이름[] = new 자료형[개수];
```

- 기본적으로 배열의 자료형에 따라 정수는 0, 실수는 0.0, 객체 배열은 null로 초기화됨
- 배열을 특정한 값으로 초기화할 수도 있음
- 특정한 값으로 초기화하는 경우 `[]`안의 개수는 생략해야 함
- 선언과 동시에 초기화할 때 `new 자료형[]`부분 생략 가능 (선언 후 초기화할 때는 생략할 수 없음)

아래는 배열을 선언하고 특정한 값으로 초기화한 코드이다.
```java
int[] studentIDs = new int[] {101, 102, 103};
int[] studentIDs = {101, 102, 103}; 
```

- 배열은 배열 총 길이를 나타내는 length 속성을 가짐

아래는 배열을 사용하고 출력한 코드이다.
```java
public class ArrayTest {
    public static void main(String[] args) {
        int[] num = new int[] {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        
        for(int i = 0; i < num.length; i++) {
            System.out.println(num[i]);
        }
    }
}
```

- 객체 배열을 선언하게 되면, 각각의 인스턴스 주소 값을 담을 공간이 생성됨
- 즉, Book이라는 클래스가 있다고 가정할 때 `Book[] library = new Book[5];`의 5개 공간에는 각각 Book 객체의 주소값을 담을 수 있음
- 아래 코드처럼 객체 배열 선언 후에 new 키워드를 사용하여 생성된 객체를 직접 저장해야 함

```java
public class BookArray {
    public static void main(String[] args) {
        Book[] library = new Book[5];

        library[0] = new Book("태백산맥", "조정래");
        library[1] = new Book("데미안", "헤르만 헤세");
        library[2] = new Book("어떻게 살 것인가", "유시민");
        library[3] = new Book("토지", "박경리");
        library[4] = new Book("어린 왕자", "생텍쥐페리");

        for(int i = 0; i < library.length; i++) {
            library[i].showBookInfo();
        }

        for(int i = 0; i < library.length; i++) {
            System.out.println(library[i]);
        }
    }
}
```

- 배열 복사는 기존 배열과 자료형, 배열 크기가 같은 배열을 새로 만들거나 더 큰 배열을 만들어 기존 배열 자료를 불러올 때 사용
- 배열 복사의 가장 단순한 방법은 for문을 활용한 복사임
- 다른 방법은 `System.arraycopy()`메서드를 사용하는 방법
- `System.arraycopy(src, srcPos, dest, destPos, length)`메서드의 각 매개변수 설명은 아래와 같음

|매개변수|설명|
|-------|----|
|src|복사할 배열 이름|
|srcPos|복사할 배열의 첫 번째 위치|







