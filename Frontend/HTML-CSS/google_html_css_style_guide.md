# Google HTML/CSS Style Guide 정리

- General
    - General Style Rules
        - Protocol
            - 임베디드 할 때 언제나 https를 써야함
            - 추천 예시
                ```
                <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
                @import 'https://fonts.googleapis.com/css?family=Open+Sans';
                ```
            - 비추천 얘시
                ```
                <script src="//ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
                <script src="http://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
                @import '//fonts.googleapis.com/css?family=Open+Sans';
                @import 'http://fonts.googleapis.com/css?family=Open+Sans';
                ```
    - General Formatting Rules
        - Indentation(들여쓰기)
            - 스페이스 2번(탭 키나 탭과 스페이스 사용하지 않음)
        - Capitalization
            - 소문자로만 작성
            - 적용 범위 : HTML element names, attributes, attribute values (unless text/CDATA), CSS selectors, properties, and property values (with the exception of strings).
            - 추천 예시
                ```
                <img src="google.png" alt="Google">

                color: #e5e5e5;
                ```
            - 비추천 예시
                ```
                <A HREF="/">Home</A>

                color: #E5E5E5;
                ```
        - Trailing Whitespace
            - 불필요한 공백 삭제
            - 추천 예시
            ```
            <p>Yes please.
            ```
            - 비추천 예시
            ```
            <p>What?_
            ```
    - General Meta Rules
        - Encoding
            - UTF-8을 사용
            ```
            <meta charset="utf-8">
            ```
        - Comments(선택사항)
            - 코드에 대한 설명을 달아줌
            - 내용
                - 이 코드가 무엇을 다루는지
                - 이 코드가 어떤 용도로 사용되는지
                - 각각의 해결방법이 사용되거나 선호되는 이유
        - Action Items
            - "TODO"와 행동을 합쳐 해야 할 일을 기록
            - 예시
                - 특정 인물에게 요청해야 하는 사항이 있을 경우 -> "TODO(contact)" 사용
                ```
                {# TODO(john.doe): revisit centering #}
                <center>Test</center>
                ```
                - 행동은 "TODO :" 이후에 작성
                ```
                <!-- TODO: remove optional tags -->
                <ul>
                <li>Apples</li>
                <li>Oranges</li>
                </ul>
                ```
- HTML
    - HTML Style Rules
        - Document Type
            - HTML5를 사용 : HTML 문서에 표시
            ```
            <!DOCTYPE html>
            # text/html에서 권장
            # XHTML. XHTML에서는 사용하지 않음
            ```
        - Semantics
            - HTML을 목적에 따라서 사용
            - ex) 'p'태그는 단락을 표시하기 위해 사용, 'a'태그는 하나의 페이지에서 다른 페이지를 연결할 때 사용 등
            - 추천 예시
            ```
            <a href="recommendations/">All recommendations</a>
            ```
            - 비추천 예시
            ```
            <div onclick="goToRecommendations();">All recommendations</div>
            ```
        - Multimedia Fallback
            - 이미지, 비디오 등과 같은 멀티미디어는 대체 콘텐츠를 제공해야함
            - 이미지의 경우 'alt'를 사용해 이미지의 의미있는 설명을 표시
            - 비디오의 경우 오디오 스크립트 및 캡션을 표시
            - 추천 예시
            ```
            <img src="spreadsheet.png" alt="Spreadsheet screenshot.">
            ```
            - 비추천 예시
            ```
            <img src="spreadsheet.png">
            <img src="spreadsheet.png" alt="">
            ```
        - Separation of Concerns
            - markup 부분, styling 부분, scripting 부분을 엄격하게 분리해야함
            - styling 부분은 style scheets에 관리
            - scripting 부분은 scripts에 관리
            - 추천 예시
            ```
            <!DOCTYPE html>
            <title>My first CSS-only redesign</title>
            <link rel="stylesheet" href="default.css">
            <h1>My first CSS-only redesign</h1>
            <p>I’ve read about this on a few sites but today I’m actually
            doing it: separating concerns and avoiding anything in the HTML of
            my website that is presentational.
            <p>It’s awesome!
            ```
            - 비추천 예시
            ```
            <!DOCTYPE html>
            <title>HTML sucks</title>
            <link rel="stylesheet" href="base.css" media="screen">
            <link rel="stylesheet" href="grid.css" media="screen">
            <link rel="stylesheet" href="print.css" media="print">
            <h1 style="font-size: 1em;">HTML sucks</h1>
            <p>I’ve read about this on a few sites but now I’m sure:
            <u>HTML is stupid!!1</u>
            <center>I can’t believe there’s no way to control the styling of
            my website without doing everything all over again!</center>
            ```
        - Entity References
            - 추천 예시
            ```
            The currency symbol for the Euro is “€”.
            ```
            - 비추천 예시
            ```
            The currency symbol for the Euro is &ldquo;&eur;&rdquo;.
            ```
        - type Attributes
            - style scheets와 scripts에서 type을 생략할 수 있음
            - 추천 예시
            ```
            <link rel="stylesheet" href="https://www.google.com/css/maia.css">
            <script src="https://www.google.com/js/gweb/analytics/autotrack.js"></script>
            ```
            - 비추천 예시
            ```
            <link rel="stylesheet" href="https://www.google.com/css/maia.css" type="text/css">
            <script src="https://www.google.com/js/gweb/analytics/autotrack.js" type="text/javascript"></script>
            ```
        - id Attributes
            - 불필요한 id 속성을 피하고, styling에는 class 속성을 사용하고 scripting에는 data 속성을 사용
            - id 속성이 반드시 필요한 경우 '-'을 포함하여 javascript 식별자와 일치하지 않도록 사용
            - 추천 예시
            ```
            <div aria-describedby="user-profile">
            …
            <div id="user-profile"></div>
            …
            </div>
            ```
            - 비추천 예시
            ```
            <div id="userProfile"></div>
            ```