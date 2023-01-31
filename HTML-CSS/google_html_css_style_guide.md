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
    - HTML Formatting Rules
        - HTML Quotation Marks
            - 속성 값을 입력할 때 큰 따옴표를 사용
            - 추천 예시
            ```
            <a class="maia-button maia-button-secondary">Sign in</a>
            ```
            - 비추천 예시
            ```
            <a class='maia-button maia-button-secondary'>Sign in</a>
            ```
- CSS
    - CSS Style Rules
        - Class Naming
            - 의미 있거나 일반적인 클래스 이름을 사용
            - 추천 예시
            ```
            .gallery {}
            .login {}
            .video {}
            .aux {}
            .alt {}
            ```
            - 비추천 예시
            ```
            .yee-1901 {}
            .button-green {}
            .clear {}
            ```
        - Class Name Style
            - 이해 가능한 정도까지만 약식으로 표시
            - 예시
            ```
            .navigation {} -> .nav {}
            .atr {} -> .author {}
            ```
        - Class Name Delimiters(구분자)
            - -(하이픈) 으로 클래스를 구분
            - 추천 예시
            ```
            .video-id {}
            .ads-sample {}
            ```
            - 비추천 예시
            ```
            .demoimage {}
            .error_status {}
            ```
        - Type Selectors
            - 유형 선택자를 클래스 이름으로 설정하지 않음
            - 필요하지 않은 경우 클래스와 함께 요소 이름을 사용하지 않음
            - 추천 예시
            ```
            .example {}
            .error {}
            ```
            - 비추천 예시
            ```
            ul.example {}
            div.error {}
            ```
        - ID Selectors
            - ID 선택자 사용을 피함
            - ID 속성은 전체 페이지에서 고유한 값을 가져야 하는데, 여러 개발자들이 작업하는 경우 고유 값을 보장하기가 어려움
            - class 선택자를 사용하는 편이 좋음
            - 추천 예시
            ```
            .example {}
            ```
            - 비추천 예시
            ```
            #example {}
            ```
        - Shorthand Properties
            - 가능한 경우 shorthand 속성을 사용
            - 추천 예시
            ```
            border-top: 0;
            font: 100%/1.6 palatino, georgia, serif;
            padding: 0 1em 2em;
            ```
            - 비추천 예시
            ```
            border-top-style: none;
            font-family: palatino, georgia, serif;
            font-size: 100%;
            line-height: 1.6;
            padding-bottom: 2em;
            padding-left: 1em;
            padding-right: 1em;
            padding-top: 0;
            ```
        - 0 and Units
            - 필요한 경우가 아니면 "0" 값 뒤에 단위 지정을 생략
            - 예시
            ```
            flex: 0px; /* This flex-basis component requires a unit. */
            flex: 1 1 0px; /* Not ambiguous without the unit, but needed in IE11. */
            margin: 0;
            padding: 0;
            ```
        - Leading 0s
            - -1과 1 사이의 값은 0을 포함
            - 예시
            ```
            font-size: 0.8em;
            ```
        - Hexadecimal Notation
            - 가능한 경우 3자리 16진수 표기법을 사용
            - 예시
            ```
            color: #eebbcc; -> color: #ebc;
            ```
        - Important Declarations
            - "!important" 사용을 지양
            - 예시
            ```
            .example { # 비추천
                font-weight: bold !important;
            }   

            .example { # 추천
                font-weight: bold;
            }
            ```
    - CSS Formatting Rules
        - Declaration Order
            - 알파벳 순으로 작성(선택)
            - 프로젝트 내에서 일관되게 순서를 정해서 작성
            - 예시
            ```
            background: fuchsia;
            border: 1px solid;
            -moz-border-radius: 4px;
            -webkit-border-radius: 4px;
            border-radius: 4px;
            color: black;
            text-align: center;
            text-indent: 2em;
            ```
        - Block Content Indentation
            - 들여쓰기를 사용해 계층 구조에 대한 이해를 높임
            - 예시
            ```
            @media screen, projection {

                html {
                    background: #fff;
                    color: #444;
                }

            }
            ```
        - Declaration Stops
            - 모든 줄 끝에는 세미콜론을 사용
            - 추천 예시
            ```
            .test {
                display: block;
                height: 100px;
            }
            ```
            - 비추천 예시
            ```
            .test {
                display: block;
                height: 100px
            }
            ```
        - Property Name Stops
            - 항목명의 콜론 뒤에는 공백을 사용
            - 추천 예시
            ```
            h3 {
                font-weight: bold;
            }
            ```
            - 비추천 예시
            ```
            h3 {
                font-weight:bold;
            }
            ```
        - Declaration Block Separation
            - 추천 예시
            ```
            .video {
                margin-top: 1em;
            }
            ```
            - 비추천 예시
            ```
            .video{
                margin-top: 1em;
            }

            .video
            {
                margin-top: 1em;
            }
            ```
        - Selector and Declaration Separation
            - 추천 예시
            ```
            h1,
            h2,
            h3 {
                font-weight: normal;
                line-height: 1.2;
            }
            ```
            - 비추천 예시
            ```
            a:focus, a:active {
                position: relative; top: 1px;
            }
            ```
        - Rule Separation
            - 예시
            ```
            html {
                background: #fff;
            }
            (여기에 공백 줄을 넣어줘야 함)
            body {
                margin: auto;
                width: 50%;
            }
            ```
        - CSS Quotation Marks
            - "" 보다 ''를 사용
            - url() 에는 인용 마크 사용하지 않음
            - 예외 : @charset을 사용할때는 ""를 사용
            - 추천 예시
            ```
            @import url(https://www.google.com/css/maia.css);

            html {
                font-family: 'open sans', arial, sans-serif;
            }
            ```
            - 비추천 예시
            ```
            @import url("https://www.google.com/css/maia.css");

            html {
                font-family: "open sans", arial, sans-serif;
            }
            ```