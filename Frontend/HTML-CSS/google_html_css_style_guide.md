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
                
