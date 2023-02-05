# 리액트 테스트
- 더 안정적인 어플리케이션을 위해서는 여러 방법으로 테스트를 해줘야 더 안정적인 어플리케이션이 될 수 있음
- 이점
    - 테스팅 환경이 구축되어 있으면 자동화 된 유닛 테스팅으로 특정 버그를 쉽게 찾아 내 디버깅 시간을 단축함
    - 많은 테스트 코드와 함께 작성된 코드의 어플리케이션이 되기 때문에 훤씬 안정적인 어플리케이션이 됨
    - 재설계 시간의 단축, 추가로 무언가를 더 구현해야 할 떄 더 용이하게 할 수 있는 등의 이점들이 있음
- React Testing Library
    - React 구성 요소 작업을 위한 API를 추가하여 DOM Testing Library 위에 구축
    - DOM Testing Library란 Dom 노드(Node)를 테스트하기 위한 매우 가벼운 솔루션
    - Create React App으로 생성된 프로젝트는 즉시 React Testing Library를 지원함
    - RTL(행위 주도 테스트) = Enzyme(구현 주도 테스트) 을 대처하는 솔루션
- DOM(Document Object Model)
    - XML, HTML 문서의 각 항목을 계층으로 표현하여 생성, 변형 삭제할 수 있도록 돕는 인터페이스
    - HTML 요소들의 구조화된 표현
    - HTML이 브라우저의 렌더링 엔진에 의해 분석되고 분석이 모두 끝나고난 HTML 파일이 DOM
    - DOM은 HTML 문서의 내용과 구조가 객체 모델로 변화되어 다양한 프로그램에서 사용될 수 있음
    - DOM은 자바스크립트에 의해 수정될 수 있음
- Jest
    - FaceBook에 의해서 만들어진 테스팅 프레임 워크
    - 최소한의 설정으로 동작하며 Test Case 를 만들어서 어플리케이션 코드가 잘 돌아가는지 확인
    - 단위(Unit) 테스트를 위해서 이용
    - 파일을 찾는 방법
        - {filename}.test.js
        - {filename}.spec.js
        - All files inside "tests" folders
    - 구조
        - "describe" : 여러 관련 테스트를 그룹화하는 블록을 만듬
        - "it" same as test : 개별 테스트를 수행하는 곳. 각 테스트를 작은 문장처럼 설명 
        - "expect" : 값을 테스트 할 때마다 사용. 혼자서는 거의 사용 되지 않으며 matcher 와 함께 사용
            - ex) expect(2+2).toBe(4);
        - "matcher" : 다른 방법으로 값을 테스트 하도록 "매처"를 사용
- React Testing Library 주요 API
    - "render" 함수
        - DOM에 컴포넌트를 랜더링하는 함수
        - 인자로 랜더링할 React 컴포넌트가 들어감
        - Return은 RTL에서 제공하는 쿼리 함수와 기타 유틸리티 함수를 담고 있는 객체를 리턴
- 쿼리 함수
    - 페이지에서 요소를 찾기 위해 테스트 라이브러리가 제공하는 방법
    - 여러 유형의 뭐리("get", "find", "query")가 있음
    - 차이점은 요소가 발견되지 않으면 쿼리에서 오류가 발생하는지 또는 Promise를 반환하고 다시 시도하는지 여부
    - getBy... 
        - 쿼리에 대해 일치하는 노드를 반환하고 일치하는 요소가 없거나 둘 이상의 일치가 발견되면 실행 오류를 발생
        - 둘 이상의 요소가 예상되는 경우 대신 getAllBy 사용
    - queryBy... 
        - 쿼리에 대해 일치하는 노드를 반환하고 일치하는 요소가 없으면 null을 반환
        - 존재하지 않는 요소를 어설션하는 데 유용
        - 둘 이상의 일치 항목이 발견되면 오류가 발생
        - 확인된 경우 대신 queryAllBy 사용
    - findBy...  
        - 주어진 쿼리와 일치하는 요소가 발견되면 해결되는 Promise를 반환
        - 요소가 발견되지 않거나 기본 제한 시간인 1000ms 후에 둘 이상의 요소가 발견되면 약속이 거부
        - 둘 이상의 요소를 찾아야 하는 경우 findAllBy를 사용
- 테스팅에 도움을 주는 모듈
    - ESLint
        - 개발자들이 특정한 규칙을 가지고 코드를 깔끔하게 짤 수 있게 도와주는 라이브러리
        - 자바스크립트를 쓰는 가이드 라인 제시, 문법에 오류가 나면 알려주는 역할 등
        - ESLint는 포멧터(formatter) 역할도 하지만 주요 기능은 문법 오류 잡는 것
        - ESLint 설정
            - 설정 파일(.eslintrc.json) 생성
            - package.json 파일 내의 eslintConfig 영역 삭제 후 .eslintrc.json 내에 설정
        - 테스트에 특화된 ESLint 설정
            - ESLint Testing Plugin
                - Plugin : eslint에서 기본으로 제공하지 않는 다양한 규칙을 플러그인을 통해 사용할 수 있음
                - npm install eslint-plugin-testing-library eslint-plugin-jest-dom --save-dev
                - plugin 항목 : 플러그인 추가(추가 시 eslint-plugin-부분 생략 가능)
                - extends 항목 : 플러그인을 추가 한 후에 규칙을 정해줘야 사용 가능
    - Prettier
        - 주로 코드 형식을 맞추는 데 사용
        - 작은 따옴표(')를 사용할지 큰 따옴표(")를 사용할지, Indent 값을 2로 줄지 4로 줄지 등등, 에러 찾는것이 아닌 코드 포맷터 역할
- 테스트 주도 개발(Test Driven Development)
    - 실제 코드를 작성하기 전에 테스트 코드를 먼저 작성
    - 테스트 코드를 작성한 후 그 테스트 코드를 Pass 할 수 있는 실제 코드를 작성
    - 장점
        - 많은 기능을 테스트하기에 소스 코드에 안정감이 부여됨
        - 디버깅 시간이 줄어들고 실제 개발 시간도 줄어듬
        - 깨끗한 코드가 나올 확률이 높음
    - FireEvent API
        - 유저가 발생시키는 액션(이벤트)에 대한 테스트를 해야하는 경우 사용
    - userEvent API
        - fireEvent를 사용해서 만들어짐
        - 실제 유저가 보기에 실제 버튼을 클릭하는 행위가 더 잘 표현되기에 userEvent를 사용하는 게 더 추천 됨
        - userEvent.clear()
            - input이나 textarea에 텍스트를 선택(select) 한 후 제거(delete) 해 줍니다.
            - 같은 엘리먼트를 위한 userEvent를 사용했다면 clear 해준 후에 userEvent.type()을 사용하는게 좋음
- Query 사용 우선 순위
    - testing library에서 추천하는 쿼리 사용 우선 순위
    - getByRole : ex) getByRole('button', {name: /submit/i})
    - getByLabelText
    - getByPlaceholderText
    - getByText
    - getByDisplayValue
- Mock Service Worker
    - 요청을 처리하고 모의 응답(mocked response)을 보내줌
    - 작동 방식
        - 브라우저에 서비스 워커를 등록하여 외부로 나가는 네트워크 리퀘스트를 감지
        - 그 요청을 실제 서버로 갈 때 중간에 가로채서(intercept) MSW 클라이언트 사이트 라이브러리로 보냄
        - 등록된 핸들러에서 요청을 처리한 후 모의 응답을 브라우저로 보냄
        - 핸들러 생성
            - 핸들러 type : rest or graphql
            - Http method : get, post...
            - req : 매칭 요청에 대한 정보
            - res : 모의 응답을 생성하는 기능적 유틸리티
            - ctx : 모의 응답의 상태 코드, 헤어, 본문 등을 설정하느 도움이 되는 함수 그룹
    - 브라우저와 통합
        - 서비스 워커 생성
        - 생성한 서비스 워커 브라우저에 등록
    - 노드와 통합(Jest 사용하는 테스트 환경)
        - 서버 생성
        - API mocking 설정
- 리액트에서 데이터 흐름 컨트롤 하는 방법(state 관리)
    - state와 props를 사용해서 컴포넌트 간에 전달
    - React Context 사용
        - 일반적인 React 애플리케이션에서 데이터는 위에서 아래로 props를 통해 전달되지만, 애플리케이션 안의 여러 컴포넌트들에 전해줘야 하는 props가 있을 때 사용
        - 명시적으로 props를 넘겨주지 않아도 많은 컴포너트가 값을 공유
        - 사용 방법
            - context 생성
            - provider 생성
            - provider를 위한 함수 생성(복잡한 경우)
            - 생성한 함수로 context를 사용할 컴포넌트 감싸기
            - context 사용하기
    - mobx 사용
    - redux 사용
- Custom Render 
    - 모든 케이스에 wrapper를 주는 게 불편해서 적용
    - 사용방법
        - Custom Render를 만들 파일 생성
        - Custom Render 생성
            - ui : 렌더하고자 하는 jsx
            - options : wrapper 옵션 이외에 우리가 주고자 하는 다른 옵션들
        - 원래 TLR에서 import 했던 것을 생성한 파일에서 import