### 추상 클래스(abstract class)
- 추상 메서드를 포함한 클래스
- 추상 메서드는 구현코드 없이 메서드의 선언만 있음
- abstract 예약어 사용
- 추상 클래스는 new (인스턴스 화) 할 수 없음
- 하위 클래스에 위임해야 하는 부분을 추상 클래스로 만듬
- 상위 클래스를 만들떄 정확히 구현되야 하는 걸 모를때 사용
- 하위 클래스에서 다르게 구현되어야 하는 부분은 추상 메서드로 선언해서 하위 클래스가 구현

### 템플릿 메서드
- 추상 메서드나 구현된 메서드를 활용하여 전체 기능의 흐름(시나리오)을 정의하는 메서드
- final로 선언하면 하위 클래스에서 재정의 할 수 없음
- 프레임 워크에서 많이 사용되는 설계 패턴
- 추상 클래스로 선언된 상위 클래스에 템플릿 메서드를 활용하여 전체적인 흐름을 정의 
