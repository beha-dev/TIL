# 리액트교과서 (아자트 마르단) 정리

## React 기초
-React 살펴보기
  - React : 템플릿 언어가 없는 순수한 자바스크립트를 기반으로 UI 컴포넌트 라이브러리를 구현
    -React UI 컴포넌트 : 매우 독립적이며 특정 관심사가 집중된 기능 블록
  - React가 해결할 수 있는 문제
    - 시간에 따라 변화하는 데이터를 다루는 거대한 애플리케이션의 개발
    - DOM 요소를 매번 새롭게 생성 - UI를 함수로 만들어서 데이터를 전달하고 호출하여 뷰를 렌더링
  - React의 장점 : 단순한 앱 개발, 빠른 UI, 코드량 감소
    - 간결성 
      - 선언형 스타일 채택
        - 개발자가 순서대로 무엇을 해야 할지를 작성하는 명령형 스타일과 달리, 실행 결과가 어떻게 되어야 할지를 코드로 작성하는 것
        - 복잡도를 줄여줄 뿐만 아니라 코드에 대한 이해도와 가독성을 높일 수 있음
        - 명령형 스타일에서 명령문이 늘어나서 마지막 결과가 어떻게 될지 예측하기 어려울 때 사용함
        - 개발자가 UI요소를 선언형 스타일로 작성한 후 쀼에 변경이 발생하는 경우 React가 알아서 뷰를 갱신
        - DOM  비교(diffing) : React는 내부적으로 가상DOM을 사용하여 브라우저에 이미 반영된 뷰와 새로운 뷰의 차이점을 찾아냄
        - 상태와 뷰의 보정(reconciliation) : 상태를 갱신하며 뷰는 이에 따라 자동으로 갱신
        - jQuery는 개발자가 직접 뷰의 갱신 과정을 하나하나 작성해야하며, AngularJS는 프레임워크가 모든 것을 처리
      - 순수한 자바스크립트를 이요한 컴포넌트 기반 아키텍처
        - 단일 페이지 애플리케이션은 복잡한 사용자 입력을 처리하고 브라우저에서 랜더링을 수행
        - React는 순수한 자바스크립트이므로 새로운 언어를 배울 필요가 없음
      - 강력한 추상화
        - 내부의 인터페이스는 숨기고, 대신에 정규화 과정을 거친 합성 메서드와 속성을 제공
        - 예를 들어, 이벤트 핸들러는 브라우저의 원본 이벤트 객체 대신 이 원본 객체를 감싼 합성 이벤트 객체를 전달받음
        - 서버 측 렌더링
    - 속도와 테스트 용이성
      - 데이터를 변경하면 React는 가상 DOM을 먼저 비교하고, 렌더링 변경이 필요한 경우에만 실제 DOM에 렌더링
      - 결과적으로 꼭 필요한 부분만 갱신하여 내부상태(가상 DOM)와 뷰(실제 DOM)를 같게 만듬
    - React의 폭넓은 개발 커뮤니티와 생태계
      - React 컴포넌트 목록
      - 구글 머티리얼 디자인 명세에 따라 구현한 React 컴포넌트
      - 또 다른 머티리얼 디자인 React 컴포넌트
      - 마이크로소프트 오피스의 디자인 언어를 사용한 오피스 및 오피스 365용 React 컴포넌트
      - 오픈 소스 자바스크립트 패키지를 소개하는 웹 사이트
      - React 컴포넌트 모음
      - 칸 아카데미의 React 컴포넌트
      - React 컴포넌트 검색
  - React의 단점
    - React는 모든 기능을 갖춘 프레임워크는 아님(그러나 기존의 기술 스택에 더할 간단한 UI 라이브러리가 필요하다면 장점)
    - React는 다른 프레임워크만큼 성숙하지 않음
    - React는 웹 개발에 새로운 방법을 제시했지만, JSX나 데이터 라이브러리로 사용하는 Flux는 초심자에게 난감할 수도 있음
    - React는 단방향 데이터 바인딩만 제공
    - React를 리액티브 프로그래밍이라고 볼 수는 없음
  - 웹 애플리케이션에 React 적용하기
    - React를 기존 웹 앱에 적용하는 경우
      - UI 라이브러리로 React와 관련된 Redux나 React Router를 활용한 단일 페이지 애플리케이션 스택의 구성
      - MVC의 V를 대체하는 UI라이브러리로 기존 MVC 프레임워크와의 결합
      - jQuery를 기반으로 서버 측 랜더링을 거친 애플리케이션에서 자동완성 등 일부 기능을 위한 UI 컴포넌트로 활용
      - 대부분의 로직을 직접 처리하는 전통적인 방식의 백엔드에서 서버 측 랜더링 템플릿 라이브러리로 활용
      - 백엔드와 프론트엔드에서 모두 자바스크립트를 사용하는 경우(express-react-views)를 활용한 Express.js 백엔드를 예로 들 수 있음
    - React 라이브러리와 렌더링 대상
      - 여러 가지 랜더링 대상에 React를 적용할 수 있는 패키지를 선보임
    - 단일 페이지 애플리케이션과 React 
      - SPA 방식은 UI 랜더링을 대부분 브라우저 상에서 해결
      - SPA에서는 데이터만 주고 받음
    - React 개발 스택
      - 데이터 모델링과 백엔드 : RefluxJS, Redux, Meteor, Flux
      - 라우팅 : React Router
      - React용 Bootstrap 컴포넌트 : React-Bootstrap
- JSX
  - 정의 : 함수 호출과 객체 생성을 위한 문법적 편의를 제공하는 자바스크립트의 확장으로, React.createElement() 호출을 반복해야 하는 불편을 해소
  - 장점
    - 개발자 경험 개선 : 표현력이 뛰어나 코드를 읽기 쉽고, XML과 문법이 유사하여 중첩된 선언형 구조를 더 잘 나타냄
    - 팀의 생산성 향상 : 전문 개발자 외에도 개발 지식이 있는 팀원이 있다면 직접 코드를 수정할 수 있음
    - 문법 오류와 코드량 감소 : 작성해야 할 코드가 줄어들며, 이는 곧 실수나 반복으로 인한 스트레스를 줄여줌
  - React는 UI와 자바스크립트 로직에 대한 설명을 한 곳으로 모아, 기존의 어긋난 관심사 분리르 고쳐 놓음
  - JSX는 여러 가지 도구를 사용해서 표준 ECMAScrip로 컴파일 할 수 있음
  - JSX를 사용하려면 브라우저에서 실행하기 전에 컴파일 또는 트랜스파일 과정을 거쳐 일반적인 자바스크립트로 변환해야 함
    - Babel 명령줄 인터페이스 도구: babel-cli 패키지가 제공하는 트랜스파일레이션 명령을 사용
    - Node.js 또는 브라우저 자바스크립트로 작성한 스크립트(API 방식) : babel-core 패키지를 이용해서 스크립트를 작성하여 JSX를 변환하는 방식
    - 빌드 도구 : Grunt, Gulp, Webpack 같은 도구에서 Babel을 플러그인으로 사용(인기!)
  - React와 JSX의 까다로운 부분
    - 특수문자
      - 배열로 출력해서 여러 개의 문자열로 분리할 수 있음 ex)<span>{[<span>&copy;&&mdash;&ldquo;</span>]}</span>
      - 배열 안의 엘리먼트에 key 속성을 작성하면 콘솔에 표시되는 경고를 없앨 수 있음
      - 소스 코드에 특수문자를 직접 복사해서 넣음(반드시 UTF-8 문자셋을 사용해야 함)
      - 특수문자를 \u로 싲가하는 이스케이프 시퀀스로 바꾼 후에 유니코드 번호를 찾아 사용
      - String.fromCharCode(charCodeNumber)를 이용해서 유니코드 번호에서 문자로 변경
    - data- 속성
      - DOM 노드를 추가 데이터를 전달해야 하는 경우 => 안티패턴으로 DOM을 데이터베이스나 로컬 스토리지처럼 사용하지 않아야 함
      - 위의 경우 사용자 정의 속성을 렌더링해야 한다면 속성의 접두사로 data-를 사용
    - 스타일 속성
      - JSX에서는 문자열 대신 자바스크립트 객체를 전달하고, CSS 속성은 카멜 표기법으로 작성
        - background-image => backgroundImage
        - font-size => fontSize
        - font-family => fontFamily
    - class와 for 속성
      - React와 JSX는 class와 for를 제외하면 표준 HTML 속성을 모두 사용할 수 있음
      - class => className
      - for => htmlFor
    - 불 값을 속성 값으로 사용하는 경우
      - disabled, required, checked, autofocus, readOnly 같은 일부 속성은 폼 요소에만 사용
      - 속성 값을 {} 안에 반드시 자바스크립트 식으로 작성, 문자열로 입력하지 않도록 함
      - 속성 값을 생각하면 React는 생략된 값을 true로 간주
- React 컴포넌트의 상태 객체
  - 컴포넌트를 다시 생성하지 않고, 사용자 조작으로 발생한 이벤트를 처리하여 뷰를 갱신
  - 상태(state)는 React 컴포넌트에 데이터를 저장하고, 데이터의 변경에 따라 자동으로 뷰를 갱신하도록 하는 핵심 개념
  - 상태 : 컴포넌트의 변경 가능한 데이터 저장소
    - 컴포넌트를 속성과 상태가 있는 함수라고 생각하면 함수의 결과가 UI표현(뷰)
    - 속성과 상태는 둘 다 뷰를 갱신하기 위해 사용할 수 있지만, 서로 다른 목적으로 사용
    - 상태 객체에 접근할 때는 이름(this.state 객체의 속성)을 이용 ex)this.state.autocompleMatches
    - 상태 데이터는 흔히 뷰의 렌더링이 갱신될 때 동적 정보를 출력하기 위해 사용
    - 본질적으로 상태를 변경하면 뷰에서 변경한 상태에 관련된 부분만 갱신, DOM에 있는 그 외의 다른 부분은 그대로 
  - 상태 객체 다루기
    - 상태 객체에 접근하기
      - 상태 객체는 컴포넌트의 멤버 변수로 this를 통해 접근할 수 있음 ex)this.state.name
      - render()에서 this.state를 렌더링 할 수 있음
    - 초기 상태 설정하기
      - render()에서 상태 데이터를 사용하려면 먼저 상태를 초기화 해야 함
      ```
      class MyFancyComponent extends React.Component {
        constructor(props) {
          super(props)
          this.state = {...}
        }
        render() {
        ...
        }
      }
      ```
      - this.state의 값은 반드시 객체여야 함
      - 객체지향 프로그래밍 언어에서 클래스의 인스턴스가 생성될 때 constructor()가 호출됨
      - 생성자 메서드의 이름은 반드시 constructor로 함
      - constructor() 메서드 내에서 한 번만 this.state로 직접 상태를 선언
      - 이외의 부분에서 this.state = ... 으로 직접 상태를 선언하지 않도록 해야 함
    - 상태 갱신하기
      - 클래스 메서드인 this.setState(data, callback)를 사용하면 상태를 변경할 수 있음
      - 위 메서드를 실행하면 React는 전달하는 data를 현재 상태에 병합하고 render()를 호출
      - 이후 React가 callback 함수를 실행
      - 새로운 상태에 의존하는 경우, 콜백함수를 사용해야 새로운 상태가 적용된 후에 필요한 작업을 수행할 수 있음
      - setState()로 전달하는 상태는 상태 객체의 일부분만 갱신함(완벽하게 교체하지 않음)
        - 매번 상태 객체를 완전히 바꾸지 않음
        - 상태 객체에 세 항목이 있을 때 하나를 변경한다면, 나머지 둘은 그대로 유지되어 바뀌지 않음
        - 만약 상태 세 가지를 모두 갱신하고 싶다면 setState()에 이 상태에 대한 새로운 값을 명시적으로 전달
  - 상태 객체(this.state)와 속성(this.props)
    - 상태 객체는 변경 가능한 반면, 속성은 변경이 불가능
    - 속성은 부모 컴포넌트에서 전달하지만, 상태는 부모 컴포넌트가 아닌 해당 컴포넌트 자체에서 정의
    - 속성값을 변경하는 것은 오직 부모 컴포넌트에서만 가능하고, 자체적으로는 변경할 수 없다는 원리
    - 속성은 뷰 생성 시에 정해지고, 정적인 상태로 유지(변경되지 않음)
    - 상태는 해당 컴포넌트에서 설정되고 갱신
    - 속성과 상태는 둘 다 컴포넌트 클래스에서 접근이 가능하고, 다른 표현으로 여러 컴포넌트를 구성할 수 있도록 도와줌
    - 모든 컴포넌트가 상태를 가져야 하는것은 아님
  - 상태비저장 컴포넌트
    - 상태 객체가 없으며, 컴포넌트 메서드 또는 다른 React의 라이프사이클 이벤트 또는 메서드를 갖지 않음
    - 상태비저장 컴포넌트의 목적은 오직 뷰를 렌더링
    - 이 컴포넌트가 할 수 있는 것은 속성을 전달받아 처리하는 것뿐
    - 상태비저장 컴포넌트는 속성을 입력받아 UI 엘리먼트를 출력하는 간단한 함수
    - 상태비저장 컴포넌트는 예측할 수 잇다는 이점이 있음
    - 상태가 필요하지 않다면 React 컴포넌트를 함수로 선언할 수 있음
    - 상태비저장 컴포넌트(함수)에서는 엘리먼트 참조(refs)를 사용할 수 없음
    - refs를 사용하려면 상태비저장 컴포넌트를 일반적인 React 컴포넌트로 감싸야 함
- React 컴포넌트 라이프사이클 이벤트
  - 컴포넌트를 좀 더 세밀하게 제어하기 위해 컴포넌트 라이프사이클 이벤트를 사용
  - React 컴포넌트 라이프사이클 이벤트 한눈에 살펴보기
    - 마운팅 이벤트 : React 엘리먼트를 DOM 노드에 추가할 때 발생
    - 갱신 이벤트 : 속성이나 상태가 변경되어 React 엘리먼트를 갱신할 떄 발생
    - 언마운팅 이벤트 : React 엘리먼트를 DOM에서 제거할 떄 발생
    - 라이프 사이클 이벤트는 컴포넌트가 수행한 작업이나 앞으로 수행할 작업에 다라 특정 시점에 실행
    - 라이프사이클 이벤트를 이용하면 컴포넌트의 작업 수행을 향상시키는 사용자 정의 로직을 구현할 수 있음
  - 이벤트 분류
    - constructor() : 엘리먼트를 생성하여 기본 속성과 상태를 설정할 때 실행
    - 마운트 : React 인벤트가 한번만 실행
      - componentWillMount() : DOM에 삽입하기 전에 실행
      - componentDidMount() : DOM에 삽입되어 렌더링이 완료된 후 실행
    - 갱신 : React가 이벤트를 여러 번 실행
      - componentWillReceiveProps(nextProps) : 컴포넌트가 속성을 받기 직전에 실행
      - shouldComponentUpdate(nextProps, nextState) : 컴포넌트가 갱신되는 조건을 정의해서 재렌더링을 최적화 할 수 있음
      - componentWillUpdate(nextProps, nextState) : 컴포넌트가 갱신되기 직전에 실행
      - componentDidUpdate(prevProps, prevState) : 컴포넌트가 갱신된 후에 실행
    - 언마운트 : React가 이벤트를 한번만 실행
      - componentWillUnmout() : 컴포넌트를 DOM에서 제거하기 전에 실행, 구독한 이벤트를 제거하거나 다른 정리 작업을 
  - 이벤트 구현
    - 라이프사이클 이벤트를 구현하려면 클래스에 메서드를 정의해야 함
    - React는 이벤트 이름에 해당하는 메서드가 있는지 확인 후 해당 메서드를 실행
    - 이벤트 이름은 자바스크립트의 다른 이름들과 마찬가지로 대소문자를 구분해서 작성
  - 마운팅 이벤트
    - 실제 DOM에 컴포넌트를 추가하는 것에 대한 이벤트
    - 마운팅은 React 엘리먼트가 DOM에 노출되는 것
    - componentWillMount() : React 엘리먼트가 실제 DOM에 곧 추가될 것을 알려줌
      - 단 한번만 실행되고, 실행시점은 초기 렌더링 직전
      - React 컴포넌트를 서버에서 렌더링하면 기본적으로 HTML 문자열을 얻을 수 있는데, 서버에는 DOM이 없으므로 HTML을 DOM에 추가하는 작업은 없지만, 서버 렌더링 과정에서도 componentWillMount()는 실행
    - componentDidMount() : React 엘리먼트를 실제 DOM에 추가한 시점으로, 이 시점의 React 엘리먼트는 DOM 노드
      - 초기 렌더링을 마친 후에 실행되고, 브라우저에서만 한번 실행되고, 서버 렌더링에서는 실행되지 않음
      - 자식 컴포넌트의 componentDidMount() 메서드는 부모 컴포넌트의 componentDidMount()보다 먼저 호출
      - componentDidMount() 이벤트는 다른 자바스크립트 라이브러리를 통합하기에 가장 적절한 위치
  - 갱신 이벤트
    - 컴포넌트를 갱신하는 것과 관련되어 있음
    - componentWillReceiveProps(newProps)
      - 컴포넌트가 새로운 속성을 전달받을 때 실행
      - 컴포넌트에 새로운 속성을 받아오는 시점에 끼어들어서 render()를 호출하기 전에 일부 로직을 추가할 수 있음
      - 새로운 속성을 인자로 받음
      - 컴포넌트를 최초로 렌더링 할때는 실행되지 않고, 새로운 속성을 전달받고 다시 렌더링이 이러지기 전, 새로운 속성에 따라 상태를 변경하려는 경우에 유용
    - shouldComponentUpdate()
      - 렌더링 직전에 실행
      - 렌더링은 새로운 속성이나 상태가 전달된 후에 이뤄짐
      - false를 반환하도록 구현하면 react가 다시 렌더링되지 않도록 할 수 있음
      - 변경된 부분이 없고, 불필요한 성능 저하를 피하고자 할 때 유용한 방법
    - componentWillUpdate()
      - 새로운 속성이나 상태를 받은 후 렌더링 직전에 호출
      - 초기 렌더링 시에는 호출되지 않음
      - 갱신 전에 필요한 준비 작업을 처리할 때 사용
      - 이 메서드 내에서 this.setState()를 사용하는 것은 피하는것이 좋음
      - shouldComponentUpdate()가 false를 반환하면, componentWillUpdate()는 실행되지 않음
    - componentDidUpdate()
      - 컴포넌트의 갱신 결과가 실제 DOM에 반영된 직후에 실행
      - 초기 렌더링 시에는 호출되지 않음
  - 언마운팅 이벤트
    - DOM에서 요소를 분리하거나 제거하는것을 의미
    - componentWillUnmount() 
      - DOM에서 컴포넌트가 제거되기 직전에 호출됨
      - 정리하기 위한 코드를 이 메서드에 추가할 수 있음
- React에서 이벤트 다루기
  - JSX로 작성한 엘리먼트에 속성 값으로 이벤트 핸들러를 정의
  - bind()를 이용하면 이벤트 핸들러 함수가 클래스의 인스턴스인 React 엘리먼트에 대한 참조를 유지
  - 바인딩하지 않으면 use strict를 선언한 상태에서 this는 null이 됨
  - 다음 경우에는 bind(this)로 바인딩하지 않음
    - this를 이용해서 해당 클래스를 참조할 필요가 없을 떄
    - ES6+ 클래스 대신 예전 방식인 React.createClass()를 사용할 때, 이때는 createClass()가 자동으로 바인딩
    - 화살표 함수(() => {})를 사용할 때
  - React가 지원하는 event : https://reactjs.org/docs/events.html
  - 캡처 및 버블링 단계
    - React는 onClick={handleSave}처럼 JSX에 속성으로 이벤트를 선언
    - 버블링 모드에서는 이벤트가 가장 내부에 있는 대상 요소에서 이벤트를 캡처한 후, 대상 요소의 부모 요소를 시작으로 외부의 상위 요소로 이벤트가 전파
    - 캡처 모드에서는 이벤트가 가장 바깥 쪽의 요소에 의해 캡처된 후 내부 요소로 전파
    - 캡처 단계를 위한 이벤트 리스너를 등록할 때는 이벤트 이름 뒤에 Capture를 추가하여 작성
    - 캡처 이벤트가 먼저 출력
    - 이런 동작 원리를 응용해서 이벤트 전파를 중지시키거나 이벤트 간의 우선순위를 정할 수 있음
  - React 합성 이벤트 객체 다루기
    - React 버전 15의 합성 이벤트 인터페이스에 포함되어 있는 몇 가지 프로퍼티와 메서드
      - currentTarget: 이벤트를 캡처한 요소의 DOMEventTarget
      - target: DOMEventTarget, 이벤트가 발생한 요소
        - 이벤트가 캡처된 곳이 아니라 이벤트가 발생한 DOM 노드로 currentTarget과는 차이가 있음
      - nativeEvent: DOMEvent, 브라우저 내장 이벤트 객체
      - preventDefault(): 링크나 폼 전송 버튼처럼 기본 동작을 방지하는 메서드
      - isDefaultPrevented(): 기본 동작이 방지되었을 때 실행하면 true를 반환
      - stopPropagation(): 이벤트 전파 중단
      - isPropagationStopped(): 이벤트 전파가 중단되었을 떄 실행하면 true를 반환
      - type: 태그명 문자열
      - persist(): 합성 이벤트를 이벤트 풀에서 꺼낸 후 사용자 코드에서 이벤트에 대한 참조를 유지할 수 있도록 함
      - isPersistent(): 합성 이벤트를 이벤트 폴에서 꺼낸 경우 실행하면 true를 반환
  - 이벤트와 상태 사용하기
    - 이벤트와 함께 상태를 사용하여 이벤트를 처리하고 컴포넌트의 상태를 변경할 수 있다면 사용자 조작과 상호작용하는 UI를 만들 수 있음
    - 구현해야 할 것 
      - constructor() : this.state에 카운터 값을 0으로 설정해서 뷰에서 사용할 수 있게 함
      - handleClick() : 카운터의 숫자를 증가시키는 이벤트 핸들러
      - render() : JSX로 작성한 버튼을 반환하는 render() 메서드
  - 이벤트 핸들러를 속성으로 전달하기
    - 상태비저장 컴포넌트에서 발생하는 이벤트를 처리하는 방법은 이벤트 핸들러를 상태비저장 컴포넌트의 속성으로 전달
    - 전달할 이벤트 핸들러 함수를 상태비저장 컴포넌트에서 실행하도록 하는 것
  - React가 지원하지 않는 DOM 이벤트 처리하기
    - 미지원 이벤트에 연결하려면 React 컴포넌트의 라이프사이클 이벤트를 사용
    - componentDidMount()에서 이벤트 리스너를 추가
    - componentDidUnmount()에서 이벤트 리스너를 제거
- React에서 폼 다루기
  - 폼 요소는 사용자로부터 텍스트 같은 데이터나 클릭 같은 조작을 전달받는 데 사용
  - React에서 폼을 다루기 위한 권장 방법
    - React의 render() 메서드를 폼 요소의 데이터를 포함한 실제 DOM에 최대한 밀접하게 유지하는 것
    - React 컴포넌트의 render()에서 새로운 값을 포함해야 함
    - render()에서 상태 값을 이용해 엘리먼트를 정의
    - onChange를 이용해서 폼 요소에 발생하는 변경 사항을 감지
    - 이벤트 핸들러에서 내부 상태를 갱신
    - 새로운 값이 상태에 저장되면 새로운 render()가 실행되어 뷰를 갱신
    - React에서 폼과 이벤트 정의
      - input 요소를 공통 목적을 가진 항목끼리 묶어서 <form> 요소로 감쌈
      - React DOM 이벤트와 함께, 폼 요소를 위한 세가지 이벤트를 지원
        - onChange: 폼에 입력 요소에 변경이 생기면 발생
        - onInput: 사용을 추천하지 않음
        - onSubmit: 폼 제출 시 발생, 흔히 enter를 눌렀을 때 발생
        - <form>에 onkey이나 onClick 같은 표준 React이벤트도 사용할 수 있음
        - 폼 이벤트를 사용하면 input 요소 그룹 같은 전체 폼에서 특정 이벤트를 감지해야 하는 경우에 편리
    - 폼 요소 정의
      - HTML의 거의 모든 입력 영역을 <input>, <textarea>, <select>, <option>을 사용해서 구현
      - React에서는 속성을 변경할 수 없지만, 폼 요소는 사용자가 폼 요소와 상호작용하면서 속성을 변경하므로 특별한 경우
      - React는 변경 가능한 속성인 value, checked, selected를 두어 폼 요서를 특별하게 다루고 있음
      - <input> 요소 : type 속성에 입력하는 값에 따라 여러 가지 방식의 입력 영역을 렌더링 할 수 있음
        - text : 일반적인 텍스트 입력 영역
        - password : 보안을 위해 입력 내용이 가려진 텍스트 영역
        - radio : 라디오 버튼, 라디오 버튼 그룹을 만들 때는 name 속성에 같은 값을 입력
        - checkbox : 체크박스 요소, 체크박스 그룹을 만들 때는 name 속성에 같은 값을 입력
        - button : 버튼 폼 요소
  
    
