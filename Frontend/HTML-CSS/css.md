# CSS

## 웹 레이아웃
- 문서의 흐름 
    - HTML 요소들이 배치 되는 순서
- table -> float -> flex -> 그리드
- flex 
    - 가로 축 또는 세로 축 한 방향으로 배치 및 정렬
- grid
    - 가로와 세로 두 방향으로 배치 및 정렬

---

## HTML에 스타일을 적용하는 방법
- 인라인 (Inline)
    - HTML 태그 내부에 Style 속성을 사용해서 요소들에 직접 스타일을 지정 
    ```
    <h1 style="color:red"></h1>
    ```
- 인터널 (Internal)
    - style 태그 내부에 스타일시트를 작성해서 적용
    ```
    <style>h1{color:red}</style>
    ```
    - 하나의 html 문서가 양이 많지 않은 고유한 스타일을 가질 때 사용할 수 있음
- 익스터널 (External)
    - .css 확장자를 가진 별도의 파일에 스타일을 작성하고 HTML에는 링크로 연결만 해주는 방식
    ```
    <link rel="stylesheet" href="style.css">
    ```

---

## 식별자
- 태그 : ex) h1, div, p
- id : ex) #red
- class : ex) .red, .blue

---

## 가상 선택자
- html 웹 문서에 실제로 존재하지는 않지만 필요에 의해서 임의로 지정해서 사용하는 선택자

---

## flex
- 모바일 환경에 대응하기 위해 탄생한 레이아웃 기술
- 단 방향의 레이아웃을 지정
- 축(Axis) : 정렬을 위한 기준점
    - 메인 축 : 아이템이 배치된 방향의 축
    - 교차 축 : 메인 축과 수직을 이루는 축
- container
    - display : flex
    - flex-direction : 아이템이 배치되는 축의 방향을 지정
        - row : 가로(기본)
        - row-reverse : 가로를 거꾸로 지정
        - column : 세로
        - column-reverse : 세로를 거꾸로 지정
    - flex-wrap
        - 아이템의 크기가 컨테이너의 전체 크기보다 커질 때 아이템의 줄바꿈 설정
        - nowrap(default) : 줄 바꿈을 하지 않음
        - wrap : 총 너비가 컨테이너 크기를 넘는 경우에 줄바꿈을 하게 됨
        - wrap-reverse : 줄바꿈을 할 때 아이템을 역순으로 배치하게 됨
    - flex-flow
        - flex-direction 과 flex-wrap을 한번에 지정
        - flex-flow : flex-direction flex-wrap
        ```
        flex-flow : row wrap;
        ```
    - justify-content : 메인축 방향의 아이템 정렬을 지정하는 속성
        - center : 중간에 위치
        - flex-start : 레이아웃의 시작점부터 정렬
        - flex-end :레이아웃의 끝점부터 정렬
        - space-between :첫번째 아이템은 시작점에 마지막 아이템은 끝점에 위치하고 나머지 아이템을 균등하게 정렬
        - space-around :전체 아이템돌의 균일한 여백을 따라서 정렬
        - space-evenly (IE, Edge X) : 양쪽 끝과 아이템들 사이에 균일한 여백을 갖도록 정렬
    - align-items : 교차 축 방향으로 아이템들을 정렬하는 속성
        - 메인축이 가로인 경우 교차 축은 세로
        - stretch (default) : 컨테이너의 높이만큼 늘어남
        - flex-start : 교차축의 시작점을 기준으로 정렬
        - flex-end : 교차축의 끝점을 기준으로 정렬
        - center : 교차축의 중심에 정렬
        - baseline : 문자의 기준선에 정렬
    - align-content : 교차 축 방향으로 아이템들을 정렬하는 속성
        - "flex-wrap : lab" 으로 지정되어 있는 상태에서 아이템이 여러줄로 배치되어 있을 때만 적용
        - 메인축이 가로인 경우 교차 축은 세로
        - stretch (default) : 컨테이너의 높이만큼 늘어남
        - flex-start : 교차축의 시작점을 기준으로 정렬
        - flex-end : 교차축의 끝점을 기준으로 정렬
        - center : 교차축의 중심에 정렬
        - space-between : 첫번째 아이템은 시작점에 마지막 아이템은 끝점에 위치하고 나머지 아이템을 균등하게 정렬
        - space-around :전체 아이템돌의 균일한 여백을 따라서 정렬
        - space-evenly (IE, Edge X) : 양쪽 끝과 아이템들 사이에 균일한 여백을 갖도록 정렬
- item
    - flex-basis : 플렉스 아이템의 기본 크기를 지정
        - 메인 축의 방향에 따라서 크기 지정
        - 내용에 따라서 유동적인 사이즈를 가지게 함
        - width : 내용에 상관없이 사이즈 고정
    - flex-grow : flex-basis 속성으로 지정된 기본값에서 얼마나 늘어날 수 있는지를 지정하는 속성
        - 0 이상의 값을 가지면 flex-basis 제외한 남는 공간을 flex-grow에 지정된 숫자의 비율로 분배
        - 0 (default) : 늘어나지 않음
    - flex-shrink : flex-basis 속성으로 지정된 기본값에서 얼마나 줄어들 수 있는지를 지정하는 속성
        - 컨테이너가 작아져도 특정 레이아웃을 유지할 수 있음
        - 0 : 컨텐츠 내용하고 상관없이 지정한 크기 이하로는 줄어들지 않음
    - flex : flex-basis, flex-grow, flex-shrink 속성을 한번에 지정할 수 있는 단축 속성
        - flex : flex-grow flex-shrink flex-basis
        - flex-basis 값을 auto로 지정할 수 있음
        - flex-shrink, flex-basis 는 생략 가능
        - ex) flex : 1 0 100px;
    - align-self : 교차축에서 개별 아이템의 정렬방법을 지정
        - 아이템 자기 자신 하나만 교차축 정렬을 지정
        - container의 align-items 보다 우선순위가 높음
        - auto (default) : align-items를 상속받음
        - stretch : 컨테이너의 높이만큼 늘어남
        - flex-start : 교차축의 시작점을 기준으로 정렬
        - flex-end : 교차축의 끝점을 기준으로 정렬
        - center : 교차축의 중심에 정렬
        - baseline : 문자의 기준선에 정렬
    - order : 아이템들의 시각적인 순서를 지정
        - 보이는 순서만 바뀔뿐 데이터의 순서가 바뀌지는 않음
        - 0 (default)
        - 숫자가 낮을 수록 높은 우선순위를 가짐
- tip
    - 중첩
        - flex-item 내부에 또 다른 item 자식 요소가 있는 경우 flex-item을 컨테이너가 되어서 item에 flex-layout을 적용

---

## grid
- flex의 한계를 보완하기 위해 등장
- 행과 열의 두 방향으로 레이아웃을 지정
- 큰 틀을 grid로 잡고 각각의 아이템은 grid로 지정해서 사용
- container
    - gird-template-rows : 지정한 크기로 행의 크기 지정
        - grid-template-rows : 100px 200px 300px;
        - fr : 비율(컨테이너의 높이 안에서)
    - grid-template-columns : 지정한 크기로 열의 크기 지정
        - grid-template-columns : 1fr 2fr 3fr;
        - fr : 비율(컨테이너의 넒이 안에서)
        - grid-template-columns : repeat(3, 1fr);
        - repeat
            - 행이나 열의 개수를 미리 지정하지 않고 가능한 공간의 최대한 많은 셀을 배치하기 위해서 사용
                - grid-template-columns : repeat(auto-fill(비어있는 셀을 만들어서 그리드를 채움), minmax(200px, 1fr));
                - grid-template-columns : repeat(auto-fit(남은 공간에 셀을 늘려서 채움), minmax(200px, 1fr));
    - grid-auto-rows : gird-template-rows에서 지정한 범위를 벗어나는 행의 크기 지정
    - grid-auto-columns : gird-template-columns에서 지정한 범위를 벗어나는 열의 크기 지정
    - column-gap : 열 사이의 간격을 지정
    - row-gap : 행 사이의 간격을 지정
    - gap : 행과 열 사이의 간격을 지정 (column-gap, row-gap 속성을 한번에 지정)
        - gap : row-gap column-gap
        - gap : 30px => 행과 열에 동일한 여백이 지정
    - justify/align/place-content
        - justify-content : 행 방향, 수평으로 정렬
            - center : 그리드의 중심에 정렬
            - start : 그리드의 시작에 정렬
            - end : 그리드의 끝에 정렬
            - space-between : 첫번째 컨텐츠는 시작점에 마지막 컨텐츠는 끝점에 위치하고 나머지 컨텐츠를 균등하게 정렬
            - space-around : 전체 컨텐츠들의 균일한 여백을 따라서 정렬
        - align-content : 열 방향, 수직으로 정렬
            - center : 그리드의 중심에 정렬
            - start : 그리드의 시작에 정렬
            - end : 그리드의 끝에 정렬
            - space-between : 첫번째 컨텐츠는 시작점에 마지막 컨텐츠는 끝점에 위치하고 나머지 컨텐츠를 균등하게 정렬
            - space-around : 전체 컨텐츠들의 균일한 여백을 따라서 정렬
        - place-content : justify-content와 align-content를 한번에 지정
            - place-content : align-content justify-content
    - justify/align/place-items
        - justify-items : 아이템들의 행방향 수평방향 정렬
            - center : 각 아이템들이 중심으로 정렬
            - space-between, space-around 사용불가
        - align-items : 아이템들의 열방향 수직방향 정렬
            - center : 각 아이템들이 중심으로 정렬
            - space-between, space-around 사용불가
        - place-items : justify-items,align-items 를 한번에 지정하는 단축 속성
            - place-items : align-items justify-items
    - grid-template-areas : 어떤 영역을 이름으로 지정해서 그 이름을 사용해서 템플릿을 작성
        - 사용하려는 영역에 각각 이름을 지정
        - css 속성 내 "grid-area: 이름" 과 같이 이름을 지정
        - .container css 속성 내 grid-template-area : "header header header" "aside main main" "aside main main" "footer footer footer" 와 같이 설정
        - 작성한 모양 그대로 화면에 레이아웃이 생성
    - gird-auto-flow : 어떻게 배치할지 정해지지 않은 아이템들에 대해서 어떤 방식으로 자동 배치 될 것인지 지정
        - row(default) : 행 축을 따라서 자동으로 배치
        - column : 열 축을 따라서 자동으로 배치
- item
    - grid-column-start, grid-column-end : 지정된 그리드 아이템 열의 시작과 끝 위치를 지정
        - line 기준으로 지정
        - ex) grid-column-start : 2; grid-column-end:4; -> 2번 라인부터 4번 라인까지를 자치하게 됨
    - grid-row-start, grid-row-end : 지정된 그리드 아이템 행의 시작과 끝 위치를 지정
        - line 기준으로 지정
        - ex) grid-row-start : 1; grid-row-end : 3; -> 1번 라인부터 3번 라인까지를 차지하게 됨
    - grid-column / row
        - grid-column : grid-column-start, grid-column-end를 한번에 지정
            - grid-column : 2 / 4; (grid-column-start / grid-column-end)
            - grid-column : 2 / span 2;
                - span 2 : 2칸을 차치
        - grid-row : grid-row-start, grid-row-end를 한번에 지정
            - grid-row : 1 / 3; (grid-row-start / grid-row-end)
            - grid-row : 2 / span 2;
                - span 2 : 2칸을 차치
    - justify / align / place-self : 그리드 아이템 자기 자신의 행 방향(수평)의 정렬을 지정
        - justify-self : 수평 방향의 정렬이 지정
            - start, end, center, stretch
        - align-self : 수직 방향의 정렬이 지정
            - start, end, center, stretch
        - place-self : align-self와 justify-self를 한번에 지정
        place-self : align-self justify-self
        - space-between, space-around 사용불가
    - order : 시각적으로 보이는 순서를 변경
        - 지정된 숫자가 작을수록 높은 우선순위를 가지게 됨

---

## grid-others
- repeat : 동일한 크기 설정을 반복할 때 사용할 수 있음
    - ex) repeat(3, 100px); repeat(2, 100px);
- minmax : 최소값, 최대값을 지정
    - ex) repeat(3, minmax(100px, 300px));
    - 최대 크기 이상으로 늘어나지 않고, 최소 크기 이하로 작아지지 않음
- auto-fill, auto-fit : 가진 공간에 셀을 최대한 많이 배치하기 위해서 사용
    - 몇개의 엘리먼트가 생성될지 모르거나, 사용자 화면의 크기를 정확히 알 수 없어서 몇 번 반복할지 모를 때 사용
    - auto-fill : 보이지는 않지만 비어있는 셀들을 만들어서 그리드를 채움
        - ex) repeat(auto-fill, 100px);
    - auto-fit : 남는 공간에 셀을 늘려서 채움
        - ex) repeat(auto-fit, 100px);

---

## box-model
- content 영역 : 텍스트, 이미지 등 실제 내용이 표시
- padding 영역 : 내부 여백
- border 영역 : 테두리 영역
- margin 영역 : 외부 여백
- box-sizing
    - content-box(기본값) : 컨텐츠 영역만 포함 (content)
    - border-box : 테두리 영역 까지 포함 (content, padding, border)

---

## Media Query
- 조건에 따라 다른 css 스타일을 지정하기 위해 사용되는 css 기술
- 다양한 디바이스에 대응해야 하는 반응형 웹을 만들 때 중요하게 사용
- 사용 방법
    - @media 미디어 타입 (조건 명시)
        - 미디어 타입
            - all and (default) : 모든 장치
            - screen and : 컴퓨터, 스마트기기 화면
        - 조건 명시
            - max-width
            - width : min-content => content를 유지하는 선에서 최소한의 크기 지정
            - width : max-content => 가로 크기가 컨텐츠의 최대 크기로 지정