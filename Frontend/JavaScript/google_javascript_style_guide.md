# Google JavaScript Style Guide 정리

- Source file basics
    - File name
        - 파일 이름은 언더바(_)와 대시(-)를 포함한 소문자로 작성되어야 함(추가 구두점 없음)
        - 파일 확장자는 .js여야 함
    - File encoding: UTF-8
        - 소스 파일은 UTF-8로 인코딩되어야함
    - Special characters
        - (배경 지식을 좀 더 공부한 후에 정리)
        - Whitespace characters
        - Special escape sequences
        - Non-ASCII characters
- Source file structure (소스 파일 구조)
    - License or copyright information, if present
        - 라이센스 혹은 저작권 정보가 파일에 속하는 경우
    - @fileoverview JSDoc, if present
    - goog.module statement
    - ES modules
        - Imports
            - 줄 바꿈되지 않아야 하므로 80-column 제한의 예외이다.
            - Import paths
                - ES 모듈 파일은 import 문을 사용하여 다른 ES 모듈 파일을 가져와야 함
                - 예시
                ```
                import './sideeffects.js';

                import * as goog from '../closure/goog/goog.js';
                import * as parent from '../parent.js';

                import {name} from './sibling.js';
                ```
                - File extensions in import paths
                    - .js 파일 확장자는 import 시 항상 포함해야함
                    - 예시
                    ```
                    import '../directory/file'; -> import '../directory/file.js';
                    ```
                - Importing the same file multiple times
                    - 동일한 파일을 여러번 가져오지 않음
                    - 예시
                    ```
                    import {short} from './long/path/to/a/file.js';
                    import {aLongNameThatBreaksAlignment} from './long/path/to/a/file.js';
                    ```
                - Naming imports
                    - Naming module imports
                        - 모듈을 가져올 때 lowerCamelCase로 이름을 지정해서 가져옴
                        - 예시
                        ```
                        import * as fileOne from '../file-one.js';
                        import * as fileTwo from '../file_two.js';
                        import * as fileThree from '../filethree.js';

                        import * as libString from './lib/string.js';
                        import * as math from './math/math.js';
                        import * as vectorMath from './vector/math.js';
                        ```
                    - Naming default imports
                        - 디폴트로 가져올 때는 파일 명을 기준으로 이름을 지정해서 가져옴
                        - 예시
                        ```
                        import MyClass from '../my-class.js';
                        import myFunction from '../my_function.js';
                        import SOME_CONSTANT from '../someconstant.js';
                        ```
                    - Naming named imports
                        - import {name} : 파일명과 같은 이름으로 지정해야 하고, import {SomeThing as SomeOtherThing}와 같은 형식은 피함
                        - 예시
                        ```
                        import * as bigAnimals from './biganimals.js';
                        import * as domesticatedAnimals from './domesticatedanimals.js';

                        new bigAnimals.Cat();
                        new domesticatedAnimals.Cat();
                        ```
                        - import {SomeThing as SomeOtherThing} : 가져온 파일들이 동일한 이름을 사용할 때 이름을 재지정함
                        - 예시
                        ```
                        import {Cat as BigCat} from './biganimals.js';
                        import {Cat as DomesticatedCat} from './domesticatedanimals.js';

                        new BigCat();
                        new DomesticatedCat();
                        ```