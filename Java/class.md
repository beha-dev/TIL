# 변수의 유효범위
- 지역변수(로컬 변수)
    - 함수 내부에 선언
    - 함수 내부에서만 사용
    - 스택영역
    - 함수가 호출될 때 생성되고 함수가 끝나면 소멸함
- 멤버 변수(인스턴스 변수)
    - 클래스 멤버 변수로 선언
    - 클래스 내부에서 사용하고 private이 아니면 참조 변수로 다른 클래스에서 사용 가능
    - 힙 영역
    - 인스턴스가 생성될 때 힙에 생성되고, 가비지 컬렉터가 메모리를 수거할 떄 소멸됨
    - 클래스에서 생성된 각각의 객체이며 생성될 때 각각의 메모리가 할당됨
- static 변수(클래스 변수) : 인스턴스가 공유하는 어떤 값을 선언하는 변수
    - static 예약어를 사용하여 클래스 내부에 선언
    - 클래스 내부에서 사용하고 private이 아니면 클래스 이름으로 다른 클래스에서 사용 가능
    - 데이터 영역
    - 프로그램이 처음 시작할 때 상수와 함께 데이터 영역에 생성되고 프로그램이 끝나고 메모리를 해제할 때 소멸됨
    - 인스턴스의 생성과 관계 없이 클래스 이름으로 직접 참조

# singleton 패턴
- 단 한 개만 존재하는 객체
- 클래스 생성후 생성자를 private로 설정
- 단 하나의 객체 private static으로 생성
- 외부에서 가져갈때는 getter로 가져감
```
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