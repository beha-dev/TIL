# 기본 클래스
- java.lang 패키지
    - 프로그래밍 시 import 하지 않아도 자동으로 import 됨
    - import java.lang.*; 문장이 추가 됨
    - 많이 사용하는 기본 클래스들이 속한 패키지
    - String, Integer, System 등
    - Object 클래스
        - 모든 클래스의 최상위 클래스
        - java.lang.Object 클래스
        - 모든 클래스는 Object 클래스에서 상속 받음
        - 모든 클래스는 Object 클래스의 메서드를 사용할 수 있음
        - 모든 클래스는 Object 클래스의 메서드 중 일부는 재정의 할 수 있음(final로 선언된 메서드는 재정의 할 수 없음)
        - 컴파일러가 extends Object 를 추가함
        - toString() 메서드
            - Object 클래스의 메서드
            - 객체의 정보를 String으로 바꾸어서 사용할 때 많이 쓰임
            - String이나 Integer 클래스에는 이미 재정의 되어 있음
            - String은 문자열 반환
            - Integer는 정수 값 반환
        - equals() 메서드
            - 두 인스턴스의 주소 값을 비교하여 true/false를 반환
            - 재정의 하여 두 인스턴스가 논리적으로 동일함의 여부를 반환
            - 같은 학번의 학생인 경우 여러 인스턴스의 주소 값은 다르지만, 같은 학생으로 처리해야 학점이나 정보 산출에 문제가 생기지 않으므로 이런 경우 equals() 메서드를 재정의
        - hashCode() 메서드
            - hash : 정보를 저장, 검색하기 위해 사용 하는 자료구조
            - 자료의 특정 값(키 값)에 대해 저장 위치를 반환해주는 해시 함수를 사용함
            - 해시 함수는 어떤 정보인가에 따라 다르게 구현 됨
            - hashCode() 메서드는 인스턴스의 저장 주소를 반환함
            - 힙 메모리에 인스턴스가 저장되는 방식이 hash
            - hashCode()의 반환 값 : 자바 가상 머신이 저장한 인스턴스의 주소값을 10진수로 나타냄
            - 서로 다른 메모리의 두 인스턴스가 같다면?
                - 재정의 된 equals() 메서드의 값이 true
                - 동일한 hashCode() 반환 값을 가져야 함
                - 논리적으로 동일함을 위해 equals() 메서드를 재정의 하였다면 hashCode()메서드로 재정의 하여 동일한 값이 반환 되도록 함
            - String 클래스 : 동일한 문자열 인스턴스에 대해 동일한 정수가 반환 됨
            - Integer 클래스 : 동일한 정수값의 인스턴스에 대해 같은 정수값이 반환 됨
        - clone() 메서드
            - 객체의 원본 복제하는데 사용하는 메서드
            - 원본을 유지해 놓고 복사본을 사용할 때
            - 기본 틀(prototpe)을 두고 복잡한 생성과정을 반복하지 않고 복제
            - clone() 메서드를 사용하면 객체의 정보(멤버변수 값)가 같은 인스턴스가 또 생성되는 것이므로 객체 지향 프로그램의 정보은닉, 객체 보호의 관점에서 위배될 수 있음
            - 객체의 clone() 메서드 사용을 허용한다는 의미로 clonable 인터페이스를 명시해 줌
    - String 클래스
        - String을 선언하는 두 가지 방법
            - String str1 = new String("abc") => 생성자의 매개변수로 문자열 생성
            - String str2 = "test" => 문자열 상수를 가리키는 방식
        - 힙 메모리에 인스턴스로 생성되는 경우와 상수 풀(constant pool)에 있는 주소를 참조하는 방법 두 가지
        - 문자열 연결
            - 한번 생성된 String 값(문자열)은 불변 (immutable)
            - 두 개의 문자열을 연결하면 새로운 인스턴스가 생성 됨
            - 문자열 연결을 계속하면 메모리에 gabage가 많이 생길 수 있음
            - StringBuilder, StringBuffer 사용하기
                - 내부적으로 가변적인 char[] 배열을 가지고 있는 클래스
                - 문자열을 여러 번 연결하거나 변경할 때 사용하면 유용함
                - 매번 새로 생성하지 않고 기존 배열을 변경하므로 gabage가 생기지 않음
                - StringBuffer는 멀티 쓰레드 프로그래밍에서 동기화(sybchronization)을 보장
                - 단일 쓰레드 프로그램에서는 StringBuilder를 사용하기를 권장
                - toString() 메서드로 String 반환
    - Wrapper 클래스 : 기본 자료형(primitive data type)에 대한 클래스
    - 오토 박싱(autoboxing)과 언박싱(unboxing)
        - integer는 객체이고, int는 4바이트 기본 자료형임
        - 두 개의 자료를 같이 연산할 때 자동으로 변환이 일어남
        - int = Integer(num.intBalue()로 변환(언박싱)) + int
        - integer = num2(Integer.valueOf(num2)로 변환(오토박싱))
    - class 클래스
        - 자바의 모든 클래스와 인터페이스는 컴파일 후 class 파일로 생성됨
        - class 파일에는 객체의 정보 (멤버변수, 메서드, 생성자 등)가 포함되어 있음
        - Class 클래스는 컴파일된 class 파일에서 객체의 정보를 가져올 수 있음
        - reflection 프로그래밍 : Class 클래스를 이용하여 클래스의 정보(생성자, 멤버변수, 메서드)를 가져오고 이를 활용하며 인스턴스를 생성하고, 메서드를 호출하는 등의 프로그래밍 방식
        - 로컬 메모리에 객체가 없어서 객체의 데이터 타입을 직접 알 수 없는 경우(원격에 객체가 있는 경우 등) 객체 정보만을 이용하여 프로그래밍 할 수 있음
        - Constructor, Method, Filed 등 java.lang.reflect 패키지에 있는 클래스들을 활용하여 프로그래밍
        - 일반적으로 자료 형을 알 수 있는 경우에는 사용하지 않음
        - class.forName() 메서드로 동적 로딩 하기
            - 동적 로딩 : 컴파일 시에 데이터 타입이 모두 binding 되어 자료형이 로딩되는 것(static loding)이 아니라 실행 중에 데이터 타입을 알고 binding 되는 방식
            - 프로그래밍 할 때는 어떤 클래스를 사용할지 모를 때 변수로 처리하고 실행될 때 해당 변수에 대입된 값의 클래스가 실행될 수 있도록 Class 클래스에서 제공하는 static 메서드
            - 실행 시에 로딩되므로 경우에 따라 다른 클래스가 사용될 수 있어 유용함
            - 컴파일 타임에 체크 할 수 없으므로 해당 문자열에 대한 클래스가 없는 경우예외(ClassNotFoundException)이 발생할 수 있음