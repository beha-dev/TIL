### Do it! 오라클로 배우는 데이터베이스 입문 정리

## Database, DBMS
- 데이터베이스 : 특정 목적을 위해 여러 사람이 공유하여 사용할 수 있으며, 효율적인 관리와 검색을 위해 구조화한 데이터 집합
- DBMS : 효율적인 데이터 관리 조건을 만족하며 서비스 제공의 효율성을 높이기 위한 데이터베이스 관리 시스템

## 데이터 모델
- 계층형 데이터 모델
    - 나뭇가지 형태의 트리 구조를 활용하여 데이터 관련성을 계층별로 나누어 부모 자식 같은 관계를 정의하고 데이터를 관리
    - 일대다 관계
- 네트워크형 데이터 모델
    - 그래프 구조를 기반으로 함
    - 개체 간 관계를 그래프 구조로 연결하므로 자식 개체가 여러 부모 개체를 가질 수 있음
- 객체 지향형 데이터 모델
    - 객체 지향 프로그래밍에서 사용하는 객체 개념을 기반으로 한 데이터 모델
    - 데이터를 독립된 객체로 구성하고 관리하며 상속, 오버라이드 등 객체 지향 프로그래밍에 사용되는 강력한 기능을 활용할 수 있음
- 관계형 데이터 모델
    - 현대에 가장 많이 사용하는 관계형 데이터베이스의 바탕이 되는 모델
    - 각 데이터의 독립 특성만을 규정하여 데이터 묶음을 나눔
    - 중복이 발생할 수 있는 데이터는 별개의 릴레이션으로 정의
    - 개체(entity)
        - 데이터베이스에서 데이터화하려는 사물, 개념의 정보 단위
        - 관계형 데이터베이스의 테이블 개념과 대응
        - 테이블은 릴레이션으로 표기하기도 함
    - 속성(attribute)
        - 개체를 구성하는 데이터의 가장 작은 논리적 단위
        - 데이터의 종류, 특성, 상태 등을 정의
        - 관계형 데이터베이스의 열 개념과 대응
    - 관계(relationship)
        - 개체와 개체 또는 속성 간의 연관성을 나타내기 위해 사용
        - 관계형 데이터베이스에서는 테이블 간의 관계를 외래키 등으로 구현하여 사용

## 관계형 데이터베이스(RDBMS)
- 관계형 데이터 모델 개념을 바탕으로 데이터를 저장, 관리하는 데이터베이스를 의미
- SQL(Structured Query Language)
    - 데이터를 다루고 관리하는 데 사용하는 데이터베이스 질의 언어
    - DQL(Data Query Language) : RDBMS에 저장한 데이터를 원하는 방식으로 조회하는 명령어
    - DML(Data Manipulation Language) : RDBMS 내 테이블의 데이터를 저장, 수정, 삭제하는 명령어
    - DDL(Data Definition Language) : RDBMS 내 데이터 관리를 위해 테이블을 포함한 여러 객체를 생성, 수정, 삭제하는 명령어
    - TCL(Transaction Control Language) : 트랜잭션 데이터의 영구 저장, 취소 등과 관련된 명령어
    - DCL(Data Control Language) : 데이터 사용 권한과 관련된 명령어

## 관계형 데이터베이스의 구성 요소
- 테이블
    - 데이터를 2차원 표 형태로 저장하고 관리
    - 가로줄을 행(row, 로) : 저장하려는 하나의 개체를 구성하는 여러 값을 가로로 늘어뜨린 형태
    - 세로줄을 열(column, 열) : 데이터를 대표하는 이름과 공통 특성을 정의
- 키
    - 데이터를 구별할 수 있는 유일한 값
    - 기본키(primary key)
        - 한 테이블 내에서 중복되지 않는 값만 가질 수 있는 키
        - 테이블에 저장된 행을 식별할 수 있는 유일한 값
        - 값의 중복이 없어야 함
        - NULL 값을 가질 수 없음
    - 후보키(candidate key)
        - 대체키(alternate key)라고도 부르며 후보키(candidate key)에 속해 있는 키
        - 후보키 중에서 기본키로 지정되지 않은 열
    - 외래키(foreign key)
        - 특정 테이블에 포함되어 있으면서 다른 테이블의 기본키로 지정된 키
    - 복합키(composite key)
        - 여러 열을 조합하여 기본키 역할을 할 수 있게 만든 키를 뜻함
        - 적게는 두세 개, 많게는 열 개가 넘는 열을 조합하기도 함

## 오라클 데이터베이스
- 자료형 : 테이블을 구성하는 열에 지정
    - VARCHAR2(길이) : 4000byte만큼의 가변 길이 문자열 데이터를 저장할 수 있음
    - NUMBER(전체 자리수, 소수점 이하 자릿수)
        - +38자릿수의 숫자를 저장할 수 있음
        - NUMBER(p, s)와 같이 표기할 경우 s자리만큼 소수점 이하 자릿수를 표현하고, 이 소수점 자리를 포함한 전체 p자리만큼 숫자 데이터를 저장
    - DATE : 날짜 형식을 저장하기 위해 사용하는 자료형으로 세기, 연, 월, 일, 시, 분, 초 저장이 가능
    - CHAR(길이) : 4000byte만큼의 고정 길이 문자열 데이터를 저장할 수 있음
    - NVARCHAR2(길이) : 4000byte만큼의 가변 길이 국가별 문자 세트 데이터를 저장할 수 있음
    - BLOB : 최대 크기 4GB의 대용량 이진 데이터를 저장할 수 있음
    - CLOB : 최대 크기 4GB의 대용량 텍스트 데이터를 저장할 수 있음
    - BFILE : 최대 크기 4GB의 대용량 이진 데이터 파일을 저장할 수 있음
- 객체
    - 오라클 데이터베이스 내에서 데이터를 저장하고 관리하기 위한 논리 구조를 가진 구성 요소
    - 테이블(table) : 데이터를 저장하는 장소
    - 인덱스(index) : 테이블의 검색 효율을 높이기 위해 사용
    - 뷰(view) : 하나 또는 여러 개의 선별된 데이터를 논리적으로 연결하여 하나의 테이블처럼 사용하게 해 줌
    - 시퀀스(sequence) : 일련 번호를 생성해 줌
    - 시노님(synonym) : 오라클 객체의 별칭(다른 이름)을 지정함
    - 프로시저(procedure) : 프로그래밍 연산 및 기능 수행이 가능함(반환 값 없음)
    - 함수(function) : 프로그래밍 연산 및 기능 수행이 가능함(반환 값 있음)
    - 패키지(package) : 관련 있는 프로시저와 함수를 보관함
    - 트리거(trigger) : 데이터 관련 작업의 연결 및 방지 관련 기능을 제공함
- PL/SQL
    - 데이터 관리를 위한 별도의 프로그래밍 언어
    - 변수, 조건문, 반복문 등 프로그래밍 언어에서 제공하는 요소를 사용하여 데이터를 관리할 수 있음

## 데이터 조회
- 셀렉션
    - 행 단위로 원하는 데이터를 조회하는 방식
- 프로젝션
    - 열 단위로 원하는 데이터를 조회
- 셀렉션 + 프로젝션 : 특정 테이블에서 조회하려는 행과 열을 모두 선별
- 조인
    - 두 개 이상의 테이블을 양옆에 연결하여 마치 하나의 테이블인 것처럼 데이터를 조회하는 방식
- SELECT 절, FROM 절
    - SELECT [조회할 열1 이름], [열2 이름], ..., [열N 이름] FROM [조회할 테이블 이름];
- DISTINCT : 중복 데이터 삭제
    - SELECT문으로 데이터를 조회한 후 DISTINCT를 사용하려 중복을 제거
- ORDER BY : 원하는 순서로 출력 데이터를 정렬
    - ASC : 오름차순(낮음 -> 높음)
    - DESC : 내림차순(높음 -> 낮음)
    - 정렬시 시간이 걸려서 꼭 필요한 경우가 아니라면 넣지 않는게 좋음
- WHERE
    - SELECT문으로 데이터를 조회할 때 특정 조건을 기준으로 원하는 행을 출력하는데 사용
    - AND, OR 연산자
    - 산술 연산자 : 더하기, 빼기 같은 수치 연산에서 사용
    - 비교 연산사(>, >=, <, <=, =, !=, <>, ^=) : 연산자 앞뒤에 있는 데이터 값을 비교하는데 사용
    - 논리 부정 연산자 
        - NOT : 값이 true인 경우 false 반환, 복잡한 조건식에서 정반대의 최종 결과를 얻고자 할 때 사용
        - IN : 특정 열에 포함된 데이터를 여러 개 조회할 때 활용
        - BETWEEN A AND B : 일정 범위 내의 데이터를 조회할 때 사용
        - LIKE 연산자 와일드 카드 
            - _ : 어떤 값이든 상관없이 한 개의 문자 데이터를 의미
            - % : 길이와 상관없이 한 개의 문자 데이터를 의미
        - IS NULL : Null인 데이터 출력
        - IS NOT NULL : Null이 아닌 데이터 출력
    - 집합 연산자 : 두 개 이상의 SELECT문의 결과 값을 연결할 때 사용
        - UNION : 연결된 SELECT 문의 결과 값을 합집합으로 묶어 줍니다. 결과값의 중복은 제거됩니다.
        - UNION ALL : 연결된 SELECT문의 결과 값을 합집합으로 묶어줍니다. 중복된 결과 값도 제거 없이 모두 출력됩니다.
        - MINUS : 먼저 작성한 SELECT문의 결과 값에서 다음 SELECT문의 결과 값을 차집합 처리합니다. 먼저 작성한 SELECT문의 결과 값 중 다음 SELECT문에 존재하지 않는 데이터만 출력됩니다.
        - INTERSECT : 먼저 작성한 SELECT문과 다음 SELECT문의 결과 값이 같은 데이터만 출력됩니다. 교집합과 같은 의미입니다.

## 오라클 함수
- 내장 함수
    - 문자 함수 : 문자 데이터를 가공
        - UPPER(문자열) : 괄호 안 문자 데이터를 모두 대문자로 변환하여 반환
        - LOWER(문자열) : 괄호 안 문자 데이터를 모두 소문자로 변환하여 반환
        - INITCAP(문자열) : 괄호 안 문자 데이터 중 첫 글자는 대문자로, 나머지 문자를 소문자로 변환 후 반환
        - LENGTH(문자열) : 문자열의 길이를 반환
        - LENGTHB(문자열) : 문자열의 바이트 수를 반환
        - SUBSTR(문자열 데이터, 시작 위치, 추출 길이) : 문자열 데이터의 시작 위치부터 추출 길이만큼 추출
        - SUBSTR(문자열 데이터, 시작 위치) : 문자열 데이터의 시작 위치부터 문자열 데이터 끝까지 추출
        - INSTR([대상 문자열 데이터(필수)], [위치를 찾으려는 부분 문자(필수)], [위치 찾기를 시작할 대상 문자열 데이터 위치(선택, 기본값은 1)], [시작 위치에서 찾으려는 문자가 몇 번째인지 지정(선택, 기본값은 1)]) : 문자열 데이터 안에 특정 문자나 문자열이 어디에 포함되어 있는지를 알고자 할 때 사용
        - REPLACE([문자열 데이터 또는 열 이름(필수)], [찾는 문자(필수)], [대체할 문자(선택)]) : 특정 문자열 데이터에 포함된 문자를 다른 문자로 대체
        - LPAD([문자열 데이터 또는 열이름(필수)], [데이터의 자릿수(필수)], [빈 공간에 채울 문자(선택)]) : 데이터의 빈 공간을 특정문자로 왼쪽에 채움
        - RPAD([문자열 데이터 또는 열이름(필수)], [데이터의 자릿수(필수)], [빈 공간에 채울 문자(선택)]) : 데이터의 빈 공간을 특정문자로 오른쪽에 채움
        - CONCAT(문자열, 문자열) : 두 문자열 데이터를 합침
        - TRIM([삭제 옵션(선택)][삭제할 문자(선택)] FROM [원본 문자열 데이터(필수)])
            - 삭제할 문자가 생략될 경우에 기본적으로 공백을 제거
            - LTRIM([원본 문자열 데이터(필수)], [삭제할 문자 집합(선택)]) : 왼쪽의 지정 문자을 삭제
            - RTRIM([원본 문자열 데이터(필수)], [삭제할 문자 집합(선택)]) : 오른쪽의 지정 문자을 삭제
    - 숫자 함수 : 숫자 데이터를 연산하고 수치를 조정
        - ROUND([숫자(필수)], [반올림 위치(선택)]) : 특정 숫자를 반올림한 결과를 출력, 반올림 위치를 지정하지 않으면 소수점 첫 번째 자리에서 반올림이 수행 
        - TRUNC([숫자(필수)], [버림 위치(선택)]) : 특정 위치에서 숫자를 버림한 결과를 출력, 버림 위치를 지정하지 않을 경우 소수점 첫 번째 자리에서 버림이 수행
        - CEIL([숫자(필수)]) : 입력된 숫자에 가장 가까운 큰 정수를 반환
        - FLOOR([숫자(필수)]) : 입력된 숫자에서 가장 작은 정수를 반환
        - MOD([나눗셈 될 숫자(필수)], [나눌 숫자(필수)]) : 특정 숫자를 나누고 그 나머지를 출력하는 함수
    - 날짜 함수
        - 날짜 데이터 + 숫자 : 날짜 데이터보다 숫자만큼 일수 이후의 날짜
        - 날짜 데이터 - 숫자 : 날짜 데이터보다 숫자만큼 일수 이전의 날짜
        - 날짜 데이터 - 날짜 데이터 : 두 날짜 데이터 간의 일수 차이
        - 날짜 데이터 + 날짜 데이터 : 연산불가, 지원하지 않음
        - SYSDATE : 오라클 데이터베이스 서버가 놓인 os의 현재 날짜와 시간을 보여줌
        - ADD_MONTHS([날짜 데이터(필수)], [더할 개월 수(정수)(필수)]) : 특정 날짜에 지정한 개월 수 이후 날짜 데이터를 반환
        - MONTHS_BETWEEN([날짜 데이터1(필수)], [날짜 데이터2(필수)]) : 두 날짜 데이터 간의 날짜 차이를 개월 수로 계산하여 출력
        - NEXT_DAY([날짜 데이터(필수)], [요일 문자(필수)]) : 특정 날짜를 기준으로 돌아오는 요일의 날짜를 출력
        - LAST_DAY([날짜 데이터(필수)]) : 특정 날짜가 속한 달의 마지막 날짜를 출력
        - ROUND([날짜데이터(필수)], [반올림 기준 포맷]) 
        - TRUNC([날짜데이터(필수)], [버림 기준 포맷])
    - 형 변환 함수 : 자료형을 변환
        - TO_CHAR([날짜데이터(필수)], '[출력되기 원하는 문자 형태(필수)]', 'NLS_DATE_LANGUAGE = language'(선택)) 
            - 숫자 또는 날짜 데이터를 문자 데이터로 변환
            - TO_CHAR(SYSDATE, 'MON', 'NLS_DATE_LANGUAGE = KOREAN')
        - TO_NUMBER('[문자열 데이터(필수)]', '[인식될 숫자형태(필수)]')
            - 문자열을 지정한 형태의 숫자로 인식하여 숫자 데이터로 변환
        - TO_DATE('[문자열 데이터(필수)]', '[인실될 날짜형태(필수)]')
            - 문자열 데이터를 날짜형의 데이터로 변환
    - NULL 처리 함수
        - NVL([NULL인지 여부를 검사할 데이터 또는 열(필수)], [앞의 데이터가 NULL일 경우 반환할 데이터(필수)])
        - 열 또는 데이터를 입력하여 해당 데이터가 NULL이 아닐 경우 데이터를 그대로 반환하고, NULL인 경우 지정한 데이터를 반환
        - NVL2([NULL인지 여부를 검사할 데이터 또는 열(필수)], [앞 데이터가 NULL이 아닐 경우 반환할 데이터 또는 계산식(필수)], [앞 데이터가 NULL일 경우 반환할 데이터 또는 계산식(필수)])
        - 열 또는 데이터를 입력하여 해당 데이터가 NULL이 아닐 떄와 NULL일 때 출력 데이터를 각각 지정
    - 상황에 따라 다른 데이터를 반환하는 함수
        - DECODE : 기준이 되는 데이터를 먼저 지정한 후 해당 데이터 값에 따라 다른 결과 값을 내보냄
        - DECODE([검사 대상이 될 열 또는 데이터, 연산이나 함수의 결과], [조건1], [데이터가 조건1과 일치할 때 반환할 결과], [조건2], [데이터가 조건2와 일치할 때 반환할 결과], ... [조건n], [데이터가 조건n과 일치할 때 반환할 결과],[위 조건들과 일치한 경우가 없을 때 반환할 결과])
        - CASE문 : 각 조건에 사용하는 데이터가 서로 상관없이도 가능
        - CASE [검사 대상이 될 열 또는 데이터, 연산이나 함수의 결과(선택)] WHEN [조건1] THEN [조검 1의 결과 값이 true일때, 반환할 결과]... ELSE [위 조건들과 일치하는 경우가 없을 때 반환할 결과]

## 다중행 함수와 데이터 그룹화
- 다중행 함수 : 여러 행을 바탕으로 하나의 결과 값을 도출해내기 위해 사용하는 함수
    - SUM([DISTINCT, ALL 중 하나를 선택하거나 아무 값도 지정하지 않음(선택)] [합계를 구할 열이나 연산자. 함수를 사용한 데이터(필수)]) : 합계를 구할 데이터를 지정 
    - COUNT([DISTINCT, ALL 중 하나를 선택하거나 아무 값도 지정하지 않음(선택)] [개수를 구할 열이나 연산자, 함수를 사용한 데이터(필수)]) : 결과 행의 개수를 출력 
    - MAX([DISTINCT, ALL 중 하나를 선택하거나 아무 값도 지정하지 않음(선택)] [최댓값을 구할 열이나 연산자, 함수를 사용한 데이터(필수)]) : 결과 행에서 최댓값을 출력
    - MIN([DISTINCT, ALL 중 하나를 선택하거나 아무 값도 지정하지 않음(선택)] [최솟값를 구할 열이나 연산자, 함수를 사용한 데이터(필수)]) : 결과 행에서 최솟값을 출력, 날짜 데이터에도 사용 가능
    - AVG([DISTINCT, ALL 중 하나를 선택하거나 아무 값도 지정하지 않음(선택)] [평균값을 구할 열이나 연산자, 함수를 사용한 데이터(필수)]) : 결과 행의 평균 값을 반환
- GROUP BY : 결과 값을 원하는 열로 묶어 출력
    - GROUP BY (그룹화할 열을 지정(여러 개 지정 가능)) : 특정 열 또는 데이터를 기준으로 데이터를 그룹으로 묶음
    - 다중행 함수를 사용하지 않은 일반 열은 GROUP BY절에 명시하지 않으면 SELECT절에서 사용할 수 없음
    - HAVING : GROUP BY절이 존재할 때만 사용할 수 있고, 그룹화된 결과 값의 번위를 제한하는데 사용
        - HAVING [출력 그룹을 제한하는 조건식] : GROUP BY 절을 사용해 그룹화된 결과 중 출력 그룹을 선별하는 조건식을 지정
- ROLLUP [그룹화 열 지정(여러 개 지정 가능)] : 그룹화 데이터의 합계를 함께 출력하는데 사용(명시한 열에 한하여 결과가 출력), 그룹 함수는 지정할 수 없음 
- CUBE [그룹화 열 지정(여러 개 지정 가능)] : 그룹화 데이터의 합계를 함께 출력하는데 사용(지정한 모든 열에서 가능한 조합의 결과를 모두 출력)
- GROUPING SETS [그룹화 열 지정(여러 개 지정 가능)] : 여러 그룹화 대상 열의 결과 값을 각각 같은 수준으로 출력
- 그룹화 함수 : 데이터 자체의 가공이나 틀벽한 연산 기능을 수행하지는 않지만 그룹화 데이터의 식별이 쉽고 가독성을 높이기 위한 목적으로 사용
    - GROUPING [GROUP BY절에 ROLLUP 또는 CUBE에 명시한 그룹화 할 열 이름] : 현재의 결과가 그룹화 대상 열의 그룹화가 이루어진 상태의 집계인지 여부를 출력
    - GROUPING_ID [그룹화 여부를 확인할 열(여러 개 지정 가능)] : GROUPING 함수처럼 특정 열의 그룹화 여부를 출력할 수 있으며, 검사할 열을 여러 개 지정할 수 있음

## 조인
- 두 개 이상의 테이블을 연결하여 하나의 테이블처럼 출력할 때 사용하는 방식
- 등가 조인
    - 테이블을 연결한 후에 출력 행을 각 테이블의 특정 열에 일치한 데이터를 기준으로 선정하는 방식
    - FROM 테이블1 별칭1, 테이블2 별칭2
- 비등가 조인
    - 조인 조건이 특정 열의 일치 여부를 검사하는 방식 외에 다른 방식도 사용할 수 있음
- 자체 조인
    - 하나의 테이블을 여러 개의 테이블처럼 활용하여 조인하는 방식
- 외부 조인
    - 조인 조건 데이터 중 어느 한쪽이 NULL임에도 결과를 출력할 때 포함시켜야 하는 경우 사용
    - 조인 기준 열의 어느 한쪽이 NULL이어도 강제로 출력하는 방식
    - Left Outer Join
    - Right Outer Join
- NATURAL JOIN : 등가 조인을 대신해 사용할 수 있는 조인 방식으로 조인 대상이 되는 두 테이블에 이름과 자료형이 같은 열을 찾은 후 그 열을 기준으로 등가 조인을 해줌
- JOIN ~ USING : USING 키워드에 조인 기준으로 사용할 열을 명시하여 사용
- JOIN ~ ON : 기존 WHERE절에 있는 조인 조건식을 ON 키워드 옆에 작성
- OUTER JOIN
    - Left Outer Join
    - Right Outer Join
    - Full Outer Join

## 서브쿼리
- SQL문을 실행하는 데 필요한 데이터를 추가로 조회하기 위해 SQL문 내부에서 사용하는 SELECT문을 의미
- 서브쿼리의 결과 값을 사용하여 기능을 수행하는 영역은 메인쿼리
- 특징
    - 서브쿼리는 연산자와 같은 비교 또는 조회 대상의 오른쪽에 놓이며 괄호 ()로 묶어서 사용
    - 특수한 몇몇 경우를 제외한 대부분의 서브쿼리에서는 ORDER BY절을 사용할 수 없음
    - 서브쿼리의 SELECT절에 명시한 열은 메인쿼리의 비교 대상과 같은 자료형과 같은 개수로 지정해야 함
    - 메인쿼리의 비교 대상 데이터가 하나라면 서브쿼리의 SELECT절 역시 같은 자료형인 열을 하나 지정해야 함
    - 서브쿼리에 있는 SELECT문의 결과 행 수는 함께 사용하는 메인쿼리의 연산자 종류와 호환 가능해야 함
- WHERE절에 사용하는 서브쿼리
    - 단일행 서브쿼리
        - 실행 결과가 단 하나의 행으로 나오는 서브쿼리를 뜻함
    - 다중행 서브쿼리
        - 실행 결과 행이 여러 개로 나오는 서브쿼리를 가리킴
        - IN : 메인쿼리의 데이터가 서브쿼리의 결과 중 하나라도 일치한 데이터가 있다면 true
        - ANY, SOME : 메인쿼리의 조건식을 만족하는 서브쿼리의 결과가 하나 이상이면 true
        - ALL : 메인쿼리의 조건식을 서브쿼리의 결과 모두가 만족하면 true
        - EXISTS : 서브쿼리의 결과가 존재하면(즉, 행이 1개 이상일 경우) true
    - 다중열 서브쿼리
        - 서브쿼리의 SELECT절에 비교할 데이터를 여러 개 지정하는 방식
        - 비교할 열을 괄호로 묶어 명시하고 서브쿼리에서는 괄호로 묶은 데이터와 같은 자료형 데이터를 SELECT절에 명시하여 사용할 수 있음
- FROM절에 사용하는 서브쿼리와 WITH절
    - 인라인 뷰라고도 함
    - 특정 테이블 전체 데이터가 아닌 SELECT문을 통해 일부데이터를 먼저 추출해 온 후 별칭을 줌
    - FROM절에 직접 데이터를 명시하여 사용하기에는 테이블 내 데이터 규모가 너무 크거나 현재 작업에 불필요한 열이 너무 많아 일부 행과 열만 사용하고자 할 떄 유용
    - WITH : FROM 절에 너무 많은 서브쿼리를 지정하면 가독성이나 성능이 떨어질 수 있기 때문에 사용
        - WITH [별칭1] AS (SELCET문 1), [별칭2] AS (SELECT문 2), ... SELECT FROM 별칭1, 별칭2
- SELECT절에 사용하는 서브쿼리
    - 스칼라 서브쿼리라고도 함
    - SELECT절에 하나의 열 영역으로서 결과를 출력할 수 있음
    - SELECT절에 명시하는 서브쿼리는 반드시 하나의 결과만 반환하도록 작성해 주어야 함

## 데이터를 추가, 수정, 삭제하는 데이터 조작어
- 테이블에 데이터 추가하기
    - 테이블 생성 : CREATE TABLE 
    - 테이블 삭제 : DROP TABLE
    - 테이블에 데이터 추가
        - INSERT INTO 테이블 이름 [(열1, 열2, ... , 열N)] VALUES (열1에 들어갈 데이터, 열2에 들어갈 데이터, ... , 열N에 들어갈 데이터);
        - INSERT문에서 지정한 열 개수와 각 열에 입력할 데이터 개수가 일치하지 않거나 자료형이 맞지 않는 경우 또는 열 길이를 초과하는 데이터를 지정하는 경우에 오류 발생
        - NLUU : 특정 열에 들어갈 데이터가 확정되지 않았거나 굳이 넣을 필요가 없는 데이터의 경우 사용
        - TO_DATE : 운영체제의 종류나 사용하는 기본 언어군에 따라 날짜 표기방식이 다른경우가 있어 함수 사용
        - SYSDATE : 현재시점으로 날짜를 입력
        - 서브쿼리
            - VALUES절은 사용하지 않음
            - 데이터가 추가되는 테이블의 열 개수와 서브쿼리의 열 개수가 일치해야 함
            - 데이터가 추가되는 테이블의 자료형과 서브쿼리의 자료형이 일치해야 함
- 테이블에 있는 데이터 수정하기
    - UPDATE [변경할 테이블] SET [변경할열1]=[데이터], [변경할열2]=[데이터], ... [WHERE 데이터를 변경할 대상 행을 선별하기 위한 조건];
    - ROLLBACK : 수정한 내용을 되돌리고 싶을 떄
    - UPDATE문을 실행하기 전에 SELECT문으로 WHERE절의 조건식이 정확한지 확인
- 테이블에 있는 데이터 삭제하기
    - DELETE [FROM] [테이블 이름] [WHERE 삭제할 대상 행을 선별하기 위한 조건식]

## 트랜잭션 제어와 세션
- 하나의 트랜잭션 내에 있는 여러 명령어을 랗ㄴ 번에 수행하여 작업을 완료하거나 아예 수행하지 않는 상태, 즉 모든 작업을 취소
- TCL(Transaction Control Language)
    - ROLLBACK : 모든 작업의 수행을 취소
    - COMMIT : 지금까지 수행한 트랜잭션 명령어를 데이터베이스에 영구히 반영
- 세션
    - 어떤 활동을 위한 시간이나 기간
    - 데이터베이스 접속을 시작으로 여러 데이터베이스에서 관련 작업을 수행한 후 접속을 종료하기까지 전체 기간
    - 세션이 여러 개인 경우 한쪽에서 commit하지 않은 내용은 다른쪽에서 확인할 수 없음
- LOCK
    - 특정 세션에서 조작중인 데이터는 트랜잭션이 완료되기 전까지 다른 세션에서 조작할 수 없는 상태가 되는 것
    - 조작 중인 데이터를 다른 세션은 조작할 수 없도록 접근을 보류시키는 것을 뜻함

## 데이터 정의어
- 데이터베이스 데이터를 보관하고 관리하기 위해 제공되는 여러 객체의 생성, 변경, 삭제 관련 기능을 수행
- 데이터 정의어를 실행하면 자동 commit되기 때문에 이전에 사용한 데이터 조작어는 영구히 데이터 베이스에 반영
- rollback을 통한 실행 취소가 불가능
- CREATE
    - 오라클 데이터베이스 객체를 생성하는 데 사용하는 명령어
    - CREATE TABLE 소유 계정.테이블 이름(열1 이름 열1 자료형, 열2 이름 열2 자료형, ...);
- ALTER
    - 이미 생성된 오라클 데이터베이스 객체를 변경할 때 사용
    - 테이블에 새 열을 추가 또는 삭제하거나 열의 자료형 또는 길이를 변경하는 등 테이블 구조 변경과 관련된 기능을 수행
    - ADD : 추가할 열 이름과 자료형을 명시하면 테이블에 새 열을 추가할 수 있음
        - ALTER TABLE 테이블 이름 ADD 열1이름 열1자료형;
    - RENAME : 테이블의 열 이름을 변경
        - ALTER TABLE 테이블 이름 RENAME COLUMN 열1이름 TO 변경할열1이름
    - MODIFY : 테이블의 특정 열의 자료형이나 길이를 변경할 때 사용
        - ALERT TABLE 테이블이름 MODIFY 열1이름 열1자료형;
    - DROP : 테이블의 특정 열을 삭제할 때 사용
        - ALTER TABLE 테이블 이름 DROP COLUMN 컬럼명
- RENAME
    - 테이블 이름 변경
    - RENAME 테이블이름 TO 변경된 테이블 이름
- TRUNCATE
    - 특정 테이블의 모든 데이터를 삭제
    - TRUNCATE TABLE 테이블 이름;
    - DELETE문의 수행으로도 가능하지만, TRUNCATE는 데이터 정의어이기 떄문에 ROLLBACK이 되지 않음
- DROP : 데이터베이스 객체를 삭제하는 데 사용
    - DROP TABLE 테이블명;

## 객체종류
- 사용자 테이블 : 데이터베이스를 통해 관리할 데이터를 저장하는 테이블
- 데이터 사전 : 데이터베이스를 구성하고 운영하는 데 필요한 모든 정보를 저장하는 특수한 테이블로 데이터베이스가 생성되는 시점에 자동으로 만들어짐
    - 사용자가 데이터 사전 정보에 직접 접근하거나 작업하는것을 허용하지 않음
    - 데이터 사전 뷰로 제공된 정보들을 열람할 수 있음
    - USER_XXXX : 현재 데이터베이스에 접속한 사용자가 소유한 객체 정보
    - ALL_XXXX : 현재 데이터베이스에 접속한 사용자가 소유한 객체 또는 다른 사용자가 소유한 객체 중 사용 허가를 받은 객체, 즉 사용 가능한 모든 객체 정보
    - DBA_XXXX : 데이터베이스 관리를 위한 정보(데이터베이스 관리 권한을 가진 SYSTEM, SYS 사용자만 열람 가능)
    - V$_XXXX : 데이터베이스 성능 관련 정보(X$_XXXX 테이블의 뷰)
- 인덱스 : 데이터 검색 성능의 향상을 위해 테이블 열에 사용하는 객체
    - 사용자가 직접 특정 테이블의 열에 지정할 수도 있지만 열이 기본키 또는 고유키일 경우에 자동으로 생성
    - 인덱스 생성 
        - CREATE INDEX 인덱스 이름 ON 테이블 이름(열 이름1 ASC or DESC, 열 이름2 ASC or DESC, ...);
        - 단일 인덱스(single index) : CREATE INDEX IDX_NAME ON EMP(SAL);
        - 복합 인덱스(concatenated index), 결합 인덱스(composite index)
            - 두 개 이상 열로 만들어지는 인덱스
            - WHERE 절의 두 열이 AND 연산으로 묶이는 경우
            - CREATE INDEX IDX_NAME ON EMP(SAL, ENAME, ...);
        - 고유 인덱스(unique index)
            - 열에 중복 데이터가 없을 때 사용
            - UNIQUE 키워드를 지정하지 않으면 비고유 인덱스(non unique index)가 기본값
            - CREATE UNIQUE INDEX IDX_NAME ON EMP(EMPNO);
        - 함수 기반 인덱스(function based index)
            - 열에 산술식 같은 데이터 가공이 진행된 결과로 인덱스 생성
            - CREATE INDEX IDX_NAME ON EMP(SAL*12 + COMM);
        - 비트맵 인덱스(bitmap index)
            - 데이터 종류가 적고 같은 데이터가 많이 존재할 때 주로 사용
            - CREATE BITMAP INDEX IDX_NAME ON EMP(JOB);
    - 인덱스 삭제
        - DROP INDEX 인덱스 이름;
- 뷰 : 하나 이상의 테이블을 조회하는 SELECT문을 저장한 객체
    - 사용 목적
        - 편리성 : SELECT문의 복잡도를 완화하기 위해 
        - 보안성 : 테이블의 특정 열을 노출하고 싶지 않을 경우
    - 뷰 생성
        - CREATE [OR REPLACE] [FORCE : NOFORCE] VIES 뷰 이름 (열 이름1, 열 이름2,...) AS (저장할 SELECT문) [WITH CHECK OPTION [CONSTRAINT 제약 조건]] [WITH READ ONLY [CONSTRAINT 제약 조건]];
    - 뷰 삭제
        - DROP VIEW 뷰 이름;
        - 뷰는 실제 데이터가 아닌 SELECT문만 저장하므로 뷰를 삭제해도 테이블이나 데이터가 삭제되는 것은 아님
    - 인라인 뷰 : 일회성으로 만들어서 사용하는 뷰
        - SELECT문에서 사용되는 서브쿼리, WITH절에서 미리 이름을 정의해 두고 사용하는 SELECT문 등이 이에 해당
- 시퀀스 : 오라클 데이터베이스에서 특정 규칙에 맞는 연속 숫자를 생성하는 객체
    - 시퀀스 생성 : CREATE SEQUENCE 시퀀스 이름 [INCREMENT BY n] [START WITH n] [MAXVALUE n : NOMAXVALUE] [MINVALUE n : NOMINVALUE] [CYCLE : NOCYCLE] [CACHE n : NOCACHE]
    - 시퀀스 사용
        - 시퀀스이름.CURRVAL : 시퀀스에서 마지막으로 생성한 번호를 반환
        - 시퀀스이름.NEXTVAL : 다음 번호를 생성
    - 시퀀스 수정
        - ALTER SEQUENCE 시퀀스 이름 [INCREMENT BY n] [MAXVALUE n : NOMAXVALUE] [MINVALUE n : NOMINVALUE] [CYCLE : NOCYCLE] [CAHCE n : NOCACHE]
    - 시퀀스 삭제
        - DROP SEUQENCE 시퀀스 이름
        - 시퀀스를 삭제해도 시퀀스를 사용하여 추가된 데이터는 삭제되지 않음
- 동의어 : 테이블,뷰,시퀀스 등 객체 이름 대신 사용할 수 있는 다른 이름을 부여하는 객체
    - 테이블 이름이 너무 길어 사용이 불편할 때 좀 더 간단하고 짧은 이름을 하나 더 만들어 주기 위해 사용
    - 동의어 생성 : CREATE [PUBLIC] SYNONYM 동의어 이름 FOR [사용자.][객체 이름];
    - 동의어 삭제 : DROP SYNONYM E;

## 제약 조건
- 테이블의 특정 열에 지정
- NOT NULL : 지정한 열에 NULL을 허용하지 않습니다. NULL을 제외한 데이터의 중복은 허용 
    - 이미 생성한 테이블에 제약 조건 지정 : ALTER TABLE 테이블 이름 MODIFY(열이름 NOT NULL);
    - 제약 조건 삭제 : ALTER TABLE 테이블 이름 DROP CONSTRAINT 제약 조건 이름
- UNIQUE : 지정한 열이 유일한 값을 가짐. 중복될 수 없음. NULL은 값의 중복에서 제외
    - 이미 생성한 테이블에 제약 조건 지정 : ALTER TABLE 테이블 이름 MODIFY(열이름 UNIQUE);
    - 제약 조건 삭제 : ALTER TABLE 테이블 이름 DROP CONSTRAINT 제약 조건 이름
- PRIMARY KEY : 지정한 열이 유일한 값이면서 NULL을 허용하지 않음
- FOREIGN KEY : 다른 테이블의 열을 참조하여 존재하는 값만 입력할 수 있음
    - CREATE TABLE 테이블 이름(...(다른 열 정의), 열 자료형 CONSTRAINT [제약 조건 이름] REFERENCES 참조 테이블(참조할 열));
- CHECK : 설정한 조건식을 만족하는 데이터만 입력 가능
- DEFAULT : 특정 열에 저장할 값이 지정되지 않았을 경우에 기본값을 지정
- 제약조건 비활성화, 활성화
    - ALTER TABLE 테이블 이름 DISABLE [NOVALiDATE / VALIDATE(선택)] CONSTRAINT 제약조건이름;
    - ALTER TABLE 테이블 이름 ENABLE [NOVALiDATE / VALIDATE(선택)] CONSTRAINT 제약조건이름;

## 사용자 관리
- 사용자 : 데이터베이스에 접속하여 데이터를 관리하는 계정을 사용자로 표현
- 스키마 : 데이터 간 관계, 데이터 구조, 제약 조건 등 데이터를 저장 및 관리하기 위해 정의한 데이터베이스 구조의 범위
- 사용자 생성 : CREATE USER 사용자 이름(필수) IDENTIFIED BY 패스워드(필수)...
- 사용자 정보 조회 : SELECT * FROM ALL_USER WHERE USERNAME = '사용자이름';
- 사용자 정보 변경 : ALTER USER 사용자 이름 IDENTIFIED BY 변경될 비밀번호;
- 사용자 삭제 : DROP USER 사용자이름;
- 사용자와 객체 모두 삭제 : DROP USER 사용자이름 CASCADE;

## 권한 관리
- 시스템 권한(system privilege) : 사용자 생성과 정보 수정 및 삭제, 데이터베이스 접근, 오라클 데이터베이스의 여러 자원과 객체 생성 및 관리 등의 권한을 포함
    - 시스템 권한 부여 : GRANT [시스템 권한] TO [사용자 이름/롤(Role)이름/PUBLIC][WITH ADMIN OPTION];
    - 시스템 권한 취소 : REVOKE [시스템 권한] FROM [사용자 이름/롤(Role)이름/PUBLIC];
- 객체 권한(object privilege) : 특정 사용자가 생성한 테이블,인덱스,뷰,시퀀스 등과 관련된 권한
    - 객체 권한 부여 : GRANT [객체 권한/ALL PRIVILEGES] ON [스키마,객체 이름] TO [사용자 이름/롤(Role)이름/PUBLIC][WITH GRANT OPTION];
    - 객체 권한 취소 : REVOKE [객체 권한/ALL PRIVILEGES(필수)] ON [스키마,객체 이름(필수)] FROM [사용자 이름/롤(Role) 이름/PUBLIC(필수)][CASCADE CONSTRAINTS/FORCE(선택)]

## 롤 관리
- 롤 : 여러 종류의 권한을 묶어 놓은 그룹
- 사전 정의된 롤
    - CONNECT 롤 : 사용자가 데이터베이스에 접속하는 데 필요한 CREATE SESSiON 권한
    - RESOURCE 롤 : 테이블, 시퀀스를 비롯한 여러 객체를 생성할 수 있는 기본 시스템 권한
    - DBA 롤 : 데이터베이스를 관리하는 시스템 권한
- 사용자 정의 롤 
    - CREATE ROLE문으로 롤을 생성 : CREATE ROLE ROLESTUDY;
    - GRANT 명령어로 생성한 롤에 권한을 포함 : GRANT CONNECT, RESOURCE, CREATE VIEW, CREATE SYNONYM TO ROLESTUDY;
    - GRANT 명령어로 권한이 포함된 롤을 특정 사용자에게 부여 : GRANT ROLESTUDY TO 사용자이름;
    - REVOKE 명령어로 롤을 취소 : REVOKE ROLESTUDY FROM 사용자이름;
    - 롤 삭제 : DROP ROLE ROLESTUDY;

## PL/SQL 구조
- 블록 : PL/SQL은 데이터베이스 관련 특정 작업을 수행하는 명령어와 실행에 필요한 여러 요소를 정의하는 명령어 등으로 구성되며, 이러한 명령어를 모아 둔 PL/SQL 프로그램의 기본 단위
    - DECLARE [실행에 필요한 여러 요소 선언]; (선언부) : 실행에 사용될 변수,상수,커서 등을 선언
    - BEGIN [작업을 위해 실제 실행하는 명령어]; (필수) : 조건문,반복문,SELECT,DML,함수 등을 정의
    - EXCEPTION [PL/SQL 수행 도중 발생하는 오류 처리]; (선택) : PL/SQL 실행 도중 발생하는 오류(예외 상황)를 해결하는 문장 기술
    - END;
- PL/SQL 주석 : PL/SQL 코드에 포함되어 있지만 실행되지 않는 문장을 뜻함
    - 한 줄 주석 : --[주석 처리 내용] : 현재 줄만 주석 처리
    - 여러 줄 주석 : /* [주석 처리 내용] */ : /*에서 */까리 여러 줄에 걸처 주석 처리됨
- 변수와 상수
    - 변수 선언과 값 대입하기 : 변수는 데이터를 일시적으로 저장하는 요솔 이름과 저장할 자료형을 지정하여 선언부에서 작성
    - 기본 변수 선언과 사용 : 변수 이름 자료형 := 값 또는 값이 도출되는 여러 표현식;
    - 상수 정의하기 : 변수 이름 CONSTANT 자료형 := 값 또는 값을 도출하는 여러 표현식;
    - 변수의 기본값 지정 : 변수 이름 자료형 DEFAULT 값 또는 값 도출되는 여러 표현식;
    - 변수의 NULL 값 저장 막기 : 변수 이름 자료형 NOT NULL := 또는 DEFAULT 값 또는 값이 도출되는 여러 표현식;
- 변수의 자료형 : 변수에 저장할 데이터가 어떤 종류인지를 특정 짓기 위해 사용하는 자료형
    - 스칼라형 : 숫자, 문자열, 날짜 등과 같이 오라클에서 기본으로 정의해 놓은 자료형으로 내부 구성 요소가 없는 단일 값을 의미 
    - 복합형 : 여러 종류 및 개수의 데이터를 저장하기 위해 사용자가 직접 정의하는 자료형으로 컬렉션, 레코드로 구분
    - 참조형 : 오라클 데이터베이스에 존재하는 특정 테이블 열의 자료형이나 하나의 행 구조를 참조하는 자료형
    - LOB형 : 대용량의 텍스트, 이비지, 동영상, 사운드 데이터 등 대용량 데이터를 저장하기 위한 자료형으로 대표적으로 BLOB, CLOB 등
- 조건 제어문
    - IF 조건문
        - IF-THEN : 특정 조건을 만족하는 경우 작업 수행
            - IF 조건식 THEN 수행할 명령어; END IF;
        - IF-THEN-ELSE : 특정 조건을 만족하는 경우와 반대 경우에 각각 지정한 작업 수행
            - IF 조건식 THEN 수행할 명령어; ELSE 수행할 명령어; END IF;
        - IF-THEN-ELSIF : 여러 조건에 따라 각각 지정한 작업 수행
            - IF 조건식 THEN 수행할 명령어; ELSIF 조건식 수행할 명령어; ELSIF 수행할 명령어; ... ELSE 수행할 명령어 END IF;
    - CASE 조건문
        - 단순 CASE문 : 비교 기준이 되는 조건의 값이 여러 가지일 때 해당 값만 명시하여 작업 수행
            - CASE 비교 기준 WHEN 값1 THEN 수행할 명령어; WHEN 값2 THEN 수행할 명령어; ... ELSE 수행할 명령어; END CASE;
        - 검색 CASE문 : 특정한 비교 기준 없이 여러 조건식을 나열하여 조건식에 맞는 작업 수행
            - CASE WHEN 조건식1 THEN 수행할 명령어; WHEN 조건식2 THEN 수행할 명령어; ... ELSE 수행할 명령어; END CASE;
- 반복 제어문
    - 기본 LOOP : 기본 반복문
        - LOOP 반복 수행 작업; END LOOP;
    - WHILE LOOP : 특정 조건식의 결과를 통해 반복 수행
        - WHILE 조건식 LOOP 반복 수행 작업; END LOOP;
    - FOR LOOP : 반복 횟수를 정하여 반복 수행
        - FOR i IN 시작 값.. 종료 값 LOOP 반복 수행 작업; END LOOP;
        - FOR i IN REVERSE 시작 값.. 종료 값 LOOP 반복 수행 작업; END LOOP;
    - Cursor FOR LOOP : 커서를 활용한 반복 수행
    - EXIT : 수행 중인 반복 종료
    - EXIT-WHEN : 반복 종료를 위한 조건식을 지정하고 만족하면 반복 종료
    - CONTINUE : 수행 중인 반복의 현재 주기를 건너뜀
    - CONTINUE-WHEN : 특정 조건식을 지정하고 조건식을 만족하면 현재 반복 주기를 건너뜀

## 레코드와 컬렉션
- 레코드
    - 자료형이 각기 다른 데이터를 하나의 변수에 저장하는 데 사용
    - TYPE 레코드 이름 IS RECORD ( 변수이름 자료형 NOT NULL := (또는 DEFAULT) 값 또는 값이 도출되는 여러 표현식)
    - 레코드를 사용한 INSERT : CREATE TABLE DEPT_RECORD AS SELECT * FROM DEPT;
    - 레코드를 사용한 UPDATE : UPDATE DEPT_RECORD SET ROW = dept_rec WHERE DEPTNO = 99;
    - 레코드를 포함하는 레코드(중첩레코드) : 레코드에 포함된 변수의 자료형을 지정할 때 다른 레코드를 지정할 수도 있음
- 컬렉션
    - 자료형이 같은 여러 데이터를 저장하는데 사용
    - 특정 자료형의 데이터를 여러 개 저장하는 복합 자료형
    - 연관 배열(associative array (or index by table))
        - 인덱스라고 불리는 키(key), 값(value)으로 구성되는 컬렉션
        - 중복되지 않은 유일한 키를 통해 값을 저장하고 불러오는 방식을 사용
        - TABLE 연관 배열 이름 IS TABLE OF 자료형 [NOT NULL] INDEX BY 인덱스형;
        - 레코드를 활용한 연관 배열 : 연관 배열의 자료형에 레코드를 사용할 수 있으며, 다양한 자료형을 포함한 레코드를 여러 개 사용할 수 있으므로 마치 테이블과 같은 데이터 사용과 저장이 가능
    - 중첩 테이블(nested table)
    - VARRAY(variable-size array)
    - 컬렉션 메서드 : 컬렉션 사용상의 편의를 위해 몇 가지 서브프로그램을 제공하고 있음   

## 커서와 예외 처리
- 커서
    - SELECT문 또는 데이터 조작어 같은 SQL문을 실행했을 때 해당 SQL문을 처리하는 정보를 저장한 메모리 공간
    - 실행된 SQL문의 결과 값을 사용할 수 있음
    - SELECT INTO 방식
        - 조회되는 데이터가 단 하나의 행일 때 사용 가능한 방식
        - SELECT 열1, 열2, ..., 열n INTO 변수1, 변수2, ..., 변수n FORM....
    - 명시적 커서
        - 사용자가 직접 커서를 선언하고 사용하는 커서
        - 1단계(커서 선언) : 사용자가 직접 이름을 지정하여 사용할 커서를 SQL문과 함께 선언
        - 2단계(커서 열기) : 커서를 선언할 때 작성한 SQL문을 실행
        - 3단계(커서에서 읽어온 데이터 사용) : 실행된 SQL문의 결과 행 정보를 하나씩 읽어 와서 변수에 저장한 후 필요한 작업을 수행
        - 4단계(커서 닫기) : 모든 행의 사용이 끝나고 커서를 종료
        - DECLARE CURSOR 커서 이름 IS SQL문; BEGIN OPEN 커서 이름; FETCH 커서이름 INTO 변수 CLOSE 커서이름; END;
        - 커서에 파라미터 사용하기 : CURSOR 커서 이름(파라미터 이름 자료형, ...) IS SELECT ...
    - 묵시적 커서
        - 별다른 선언 없이 SQL문을 사용했을 때 오라클에서 자동으로 선언되는 커서를 뜻함
- 예외 처리
    - 오류 : SQL또는 PL/SQL이 정상 수행되지 못하는 상황
    - 컴파일 오류(문법 오류) : 문법이 잘못되었거나 오타로 인한 오류  
    - 런타임 오류(실행 오류) : 명령문의 실행 중 발생한 오류(예외!)
    - 예외 처리 : EXCEPTION WHEN VALUE_ERROR THEN DBMS_OUTPUT.PUT-LINE('예외처리 : 수치 또는 값 오류 발생');
    - 예외 종류
        - 내부 예외 : 오라클에서 미리 정의한 예외
            - 사정 정의된 예외 : 내부 예외 중 예외 번호에 해당하는 이름이 존재하는 예외
            - 이름이 없는 예외 : 내부 예외 중 이름이 존재하지 않는 예외(사용자가 필요에 따라 이름을 지정할 수 있음)
        - 사용자 정의 예외 : 사용자가 필요에 따라 추가로 정의한 예외

## 저장 서브프로그램
- 익명 블록 : 이름이 정해져 있지 않은 PL/SQL 블록, 작성한 내용을 단 한번 실행하는데 사용
- 저장 서브 프로그램 : PL/SQL프로그램을 오라클에 저장해 두고 필요할 때마다 여러번 사용할 목적으로 이름을 지정하여 오라클에 저장
    - 저장 프로시저(stored procedure) : 일반적으로 특정 처리 작업 수행을 위한 서브프로그램으로 SQL문에서는 사용할 수 없음
        - 프로시저 생성 : CREATE [OR REPLACE] PROCEDURE 프로시저 이름 IS | AS 선언부 BDGIN 실행부 EXCEPTION 예외 처리부 END [프로시저 이름];
        - 프로시저 실행(SQL*PLUS) : EXECUTE 프로시저 이름;
        - 프로시저 실행(PL/SQL) : BEGIN 프로시저 이름; END;
        - 프로시저 내용 확인 : USER_SOURCE 데이터 사전에서 조회
        - 프로시저 삭제 : DROP PROCEDURE 프로시저 이름;
        - 프로시저 오류 정보 확인 : SHOW ERRORS;(최근), SHOW ERR 프로그램 종류 프로그램 이름;(특정 프로그램의 오류 정보를 확인)
    - 저장 함수(stored function) : 일반적으로 특정 연산을 거친 결과 값을 반환하는 서브프로그램으로 SQL문에서 사용할 수 있음
        - 함수 생성하기 : CREATE [OR REPLACE] FUNCTION 함수 이름 [(파라미터 이름1 [IN] 자료형1,...)] RETURN 자료형 IS | AS 선언부 BEGIN 실행부 RETURN (반환 값); EXCEPTION 예외 처리부 END [함수 이름];
        - 함수 실행하기(SQL) : SELECT func_aftertax(3000) FROM DUAL;
        - 함수 삭제하기 : DROP FUNCTION 함수 이름; 
    - 패키지(package) : 저장 서브프로그램을 그룹화하는 데 사용
        - 업무나 기능 면에서 연관성이 높은 프로시저, 함수 등 여러 개의 PL/SQL 서브프로그램을 하나의 논리 그룹으로 묶어 통합, 관리하는 데 사용하는 객체를 뜻함
        - 모듈성 : PL/SQL로 제작한 프로그램의 사용 및 관리에 큰 도움을 줌
        - 쉬운 응용 프로그램 설계 : 전체 소스 코드를 다 작성하기 전에 미리 패키지에 저장할 서브프로그램을 지정할 수 있으므로 설계가 수월
        - 정보 은닉 : 서브프로그램을 사용할 때 보안을 강화할 수 있음
        - 기능성 향상 : 서브프로그램 외에 변수, 커서, 예외 등도 각 세션이 유지되는 동안 선언해서 공용으로 사용할 수 있음
        - 성능 향상 : 패키지를 사용할 때 패키지에 포함한 모든 서브프로그램이 메모리에 한 번에 로딩되는데 메모리에 로딩된 후의 호출은 디스크 I/O를 일으키지 않으므로 성능이 향상
        - 패키지 본문 : 패키지 명세에서 선언한 서브프로그램 코드를 작성
            - CREATE [OR REPLACE] PACKAGE BODY 패키지 이름 IS | AS 패키지 명세에서 선언한 서브프로그램을 포함한 여러 객체를 정의 경우에 따라 패키지 명세에 존재하지 않는 객체 및 서브프로그램도 정의 가능 END [패키지 이름];
        - 서브프로그램 오버로드 : 같은 패키지에서 사용하는 파라미터의 개수, 자료형, 순서가 다를 경우에 한해서만 이름이 같은 서브프로그램을 정의할 수 있음
            - 같은 기능을 수행하는 여러 서브프로그램이 입력 데이터를 각각 다르게 정의할 때 사용
            - CREATE [OR REPLACE] PACKAGE 패키지 이름 IS | AS 서브프로그램 종류 서브프로그램 이름(파라미터 정의); 서브프로그램 종류 서브플그램 이름(개수나 자료형, 순서가 다른 파라미터 정의); END [패키지 이름];
        - 패키지 사용하기 : 패키지 이름과 마침표(.)와 사용할 객체 이름으로 사용할 수 있음
        - 패키지 삭제하기 : 패키지 명세와 본문을 한 번에 삭제하거나 패키지 본문만 삭제할 수도 있음
            - 패키지에 포함된 서브프로그램을 따로 삭제하는 것은 불가능
            - DROP PACKAGE 패키지 이름 : 패키지 명세와 본문을 한 번에 삭제하기
            - DROP PACKAGE BODY 패키지 이름 : 패키지의 본문만을 삭제   
    - 트리거(trigger) : 특정 상황(이벤트)이 발생할 때 자동으로 연달아 수행할 기능을 구현하는 데 사용
        - 데이터베이스 안의 특정 상황이나 동작, 즉 이벤트가 발생할 경우에 자동으로 실행되는 기능을 정의하는 PL/SQL 서브프로그램
        - 데이터 조작어(DML) : INSERT, UPDATE, DELETE
        - 데이터 정의어(DDL) : CREATE, ALTER, DROP
        - 데이터베이스 동작 : SERVERERROR, LOGON, LOGOFF, STARTUP, SHUPDOWN
        - DML 트리거 : INSERT, UPDATE, DELETE와 같은 DML 명령어를 기점으로 동작함
            - CREATE [OR REPLACE] TRIGGER 트리거 이름 BEFORE | AFTER INSERT | UPDATE | DELETE ON 테이블 이름 REFERENCING OLD as old | New as new FOR EACH ROW WHEN 조건식 FOLLOWS 트리거 이름2, 트리거 이름3 ... ENABLE | DISALBE DECLARE 선언부 BEGIN 실행부 EXCEPTION 예외 처리부 END;
        - DDL 트리거 : CREATE, ALTER, DROP과 같은 DDL 명령어를 기점으로 동작함
        - INSTEAD OF 트리거 : 뷰(View)에 사용하는 DML 명령어를 기점으로 동작함
        - 시스템(system) 트리거 : 데이터베이스나 스키마 이벤트로 동작함
        - 단순(simple) 트리거 : 다음 각 시점(timing point)에 동작함
            - 트리거를 작동시킬 문장이 실행되기 전 시점
            - 트리거를 작동시킬 문장이 실행된 후 시점
            - 트리거를 작동시킬 문장이 행에 영향을 미치기 전 시점
            - 트리거를 작동시킬 문장이 행에 영향을 준 후 시점
        - 복합(compound) 트리거 : 단순 트리거의 여러 시점에 동작함
        - 트리거 관리
            - 트리거 정보 조회 : SELECT TRIGGER_NAME, TRIGGER_TYPE, TRIGGERING_EVENT, TABLE_NAME, STATUS FROM USER_TRIGGERS;
        - 트리거 변경 : ALTER TRIGGER 트리거 이름 ENABLE | DISABLE;
        - 트리거 삭제 : DROP TRIGGER 트리거 이름;
