# Introduction
 Search the information of DM

# Index
1. [Database](#Database)
2. [Entity & Relationship model (객체 관계 모델)](#entity--relationship-model-객체-관계-모델)
3. [SQL (Structured Query Language, 구조화 질의어)](#sql-structured-query-language-구조화-질의어)
4. [Normalization(정규화)](#normalization정규화)
5. [Functional Dependancy(FD)(함수 종속성)](#functional-dependancyfd함수-종속성)
6. [Microsoft SQL Server](#microsoft-sql-server)
7. [Tuning](#tuning)
8. [Note](#note)


# Database 

* 튜블(Record)(세로줄)

* 칼럼(Attribute)(가로줄)

* 식별자(identifier)(아이디가 대표적)

# Entity & Relationship model (객체 관계 모델)
Entity - 객체

* Arribute type
    - Simple
    - Composite           ㄱ
    - Multiple-Value      --- in general
    - Derived             -  derivable from value of a related attribute, or set of attributes, not necessarily in the same entity type

* Weak Entity type
    - No key attribute.
    - must participate in an identifying relationship type with an owner or entity type.
    - Combination of - partial key + particular entity

* Concepts
    - Structural constraints
    - Cardinality ratio (functionality)


# SQL (Structured Query Language, 구조화 질의어)
관계형 데이터베이스 관리 시스템의 데이터 관리를 위한 국제 표준 언어
* 언어
    + 정의
        - CREATE      - 새로운 관계(테이블), VIEW, 인덱스, 저장 프로시저 만들기
        - DROP        - 이미 존재하는 데이터베이스 관계(테이블), 뷰, 인덱스, 저장 프로시저를 제거
        - ALTER       - 이미 존재하는 데이터베이스 개체에 대한 변경, RENAME
        - TRUNCATE    - 행(레코드) 삭제
    + 조작
        - SELECT      - 검색
        - INSERT      - 삽입
        - UPDATE      - 업데이트,수정
        - DELETE      - 삭제
    + 제어
        - GRANT       - 권한 부여
        - REVOKE      - 권한 박탈
        - 권한
            * CONNECT- 데이터베이스 또는 스키마에 연결하는 권한
            * SELECT - 데이터를 검색하는 권한
            * INSERT - 데이터를 등록할 수 있는 권한
            * UPDATE - 데이터를 업데이트 할 수 있는 권한
            * DELETE - 데이터를 삭제할 수 있는 권한
            * USAGE - 스키마 또는 함수와 같은 데이터베이스 개체를 사용할 수 있는 권한
* 장단점
    - 장점
        * High performance
        * No code needed
        * Well defined standards
        * Portability
        * Structured system
        * Multiple data views
    - 단점
        * Complexity
        * Cost
        * Partial Control
        * Scalability and Flexibility

# Normalization(정규화)
Relational database 설계에서 중복된 데이터가 최소화되도록 데이터베이스의 구조를 결정하는 것.
A database design technique that reduces data redundancy and eliminates undesirable characteristics like Insertion, Update and Deletion Anomalies.
* Normal Forms in SQL
    + 1NF (First Normal Form)
        - Each table cell should contain a single value.
        - Each record needs to be unique.
    + 2NF (Second Normal Form)
        - Rule 1- Be in 1NF
        - Rule 2- Single Column Primary Key that does not functionally dependant on any subset of candidate key relation
    + 3NF (Third Normal Form)
        - Rule 1- Be in 2NF
        - Rule 2- Has no transitive functional dependencies
    + BCNF (Boyce-Codd Normal Form)
        - Even when a database is in 3rd Normal Form, still there would be anomalies resulted if it has more than one Candidate Key. Sometimes is BCNF is also referred as 3.5 Normal Form.
    + 4NF (Fourth Normal Form)
        - If no database table instance contains two or more, independent and multivalued data describing the relevant entity, then it is in 4th Normal Form.
    + 5NF (Fifth Normal Form)
        - A table is in 5th Normal Form only if it is in 4NF and it cannot be decomposed into any number of smaller tables without loss of data.
    + 6NF (Sixth Normal Form)
        - 6th Normal Form is not standardized, yet however, it is being discussed by database experts for some time. Hopefully, we would have a clear & standardized definition for 6th Normal Form in the near future…


# Functional Dependancy(FD)(함수 종속성)
함수 종속(functional dependency)이란 데이터베이스의 관계(relation)에서 두 개의 필드(attribute) 집합 간 제약의 일종이다.

In relational database theory, a functional dependency is a constraint between two sets of attributes in a relation from a database. In other words, a functional dependency is a constraint between two keys. 

함수 종속성은 수학에서의 함수와 같이 두 필드의 집합이 many-to-one 관계로 사상되는 것을 말한다. 즉, 함수와 같이 어떠한 값을 통해 종속 관계에 있는 다른 값을 유일하게 결정할 수 있다는 것이다. 데이터베이스에서의 함수 종속성을 더욱 명확하게 정의하면 다음과 같다.

어떤 테이블 R에 존재하는 필드들의 부분집합을 각각 X와 Y라고 할 때, X의 한 값이 Y에 속한 오직 하나의 값에만 사상될 경우에 "Y는 X에 함수 종속 (Y is functionally dependent on X)"이라고 하며, X→Y라고 표기한다.

예를 들어, 테이블에 '생일'과 '나이'라는 필드가 존재할 경우에 '나이' 필드는 '생일' 필드에 함수 종속이다. 즉, 생일을 알고 있다면, 나이에 대한 필드를 참조하지 않거나, 아예 필드를 유지하지 않아도 나이를 결정할 수 있다. 

데이터베이스 설계 단계에서 함수 종속 관계에 있는 필드를 찾는다면, 그 만큼 중복된 데이터를 줄일 수 있다. 그러므로, 데이터베이스 설계 단계에서 각 정보들 간의 함수 종속 관계를 찾는 것은 매우 중요하다.
* 성질
    + augmentation (증가성) : 만약 X→Y이면, XZ→YZ이다.
    + transitivity (타동성) : 만약 X→Y이고 Y→Z이면, X→Z이다.
    + reflexivity (재귀성) : 만약 Y가 X의 부분집합이면, X→Y이다.
    + self-determination (자기 결정성) : 자기 자신은 자신에 의해 함수 종속적이다. 즉, X→X이다.
    + union (융합성) : 만약 X→Y이고 X→Z이면, X→YZ이다.
    + decomposition (분해성) : 만약 X→YZ이면, X→Y이고 X→Z이다.

* Types
    + Multivalued Dependency
        - Multivalued dependency occurs in the situation where there are multiple independent multivalued attributes in a single table. 
    + Trivial Functional Dependency
        - The Trivial dependency is a set of attributes which are called a trivial if the set of attributes are included in that attribute.
    + Non-Trivial Functional Dependency
        - If attribute B is not a subset of attribute A, then it is considered as a non-trivial dependency.
    + Transitive Dependency
        - A Transitive Dependency is a type of functional dependency which happens when t is indirectly formed by two functional dependencies.

* Applications to normalization
    + Heath's theorem
        - ?
    + Normal forms
        - database normalization levels which determine the "goodness" of a table.

* Closure 개념을 이용한 Super key 판별
    * Closure
        - 일급 객체 함수(first-class functions)의 개념을 이용하여 스코프(scope)에 묶인 변수를 바인딩 하기 위한 일종의 기술이다.
        기능상으로, 클로저는 함수를 저장한 레코드(record)이며, 스코프(scope)의 인수(Factor)들은 클로저가 만들어질 때 정의(define)되며, 스코프 내의 영역이 소멸(remove)되었어도 그에 대한 접근(access)은 독립된 복사본인 클로저를 통해 이루어질 수 있다.
        - 스코프(Scope) : 유효범위를 말하는 것으로, 변수 사용 가능 여부를 영역을 구분짓는 것

    * 본론
        - 어떠한 테이블에서 주어진 필드의 집합이 해당 테이블의 super key인지를 판별하기 위해 closure라는 개념을 이용할 수 있다. 
        어떠한 테이블의 모든 필드가 주어진 필드의 집합 S에 대해 함수 종속이라면, 주어진 필드의 집합 S는 해당 테이블의 super key라고 할 수 있다. 
        - 따라서, 함수 종속성과 암스트롱의 공리, closure 개념을 이용하여 super key를 판별할 수 있다.

# Microsoft SQL Server
* RDBMS(Relational database management system, 관계형 데이터베이스 시스템)
    + 관계형 모델(relational model)을 기반으로 한 데이터베이스 관리 시스템(DMS), 주요 데이터베이스 모델들의 기반
    + 테이블 데이터 조작을 위한 관계 연산자 제공

* Main components
    * Database Engine
        + Relational Engine
        + Storage Engine
    * SQL OS
        + OS under database engine
        + Handling and synchronization services
    * Tools
        + SSMS(SQL Server Management Studio)


# Tuning
원하는 정보를 빠르게 출력하기 위해 시스템을 조정하는 작업
기업의 경영활동에 있어 정보의 수집, 축적, 가공 및 효과적인 활용은 필수적이다. 점차 대형화, 복잡화되어가
는 기업의 정보시스템에서 관계형 데이터베이스는 데이터의 관리와 활용에 있어 기존의 파일시스템과 비교할
때 매우 간편하고 강력한 기능을 제공한다.

* 튜닝 종류
    + 데이터베이스 설계
    + 데이터베이스 환경
        - 공유 풀 튜닝
        - - 라이브러리 캐시 튜닝
        - - 딕셔너리 캐시 튜닝
        - 데이터베이스 버퍼 캐시 튜닝
        - 디스크 I/O 튜닝
        - 로우 마이그레이션 & 로우 체이닝
    + SQL 문장

* 튜닝 방법론
    + 비율 기반 분석
        - 소규모 용량의 데이터베이스에선 효율적
        - 복잡한 환경에서의 분석에 한계 있음(대규모 용량 처리 필요성)

    + 대기 이벤트 기반 분석
        - 연결된 동시 세션들이 데이터베이스의 어떤 자원에 대해 대기하고 있는가를 진단
        - 서비스 처리 시간과 운영체제 자원에 대한 대기시간은 고려되지 않음(서비스 처리 시간'도' 포함할 필요있음)

    + 응답 시간 분석
        - 응답 시간 = 처리 시간 + 대기 시간
        - 2000년대부터 현존하는 가장 효율적인 방법

* 웹 기반 시스템의 튜닝

* 통합 정보 시스템의 튜닝

# Note

전사적 자원 관리(ERP), 고객 관계 관리(CRM), 데이터 웨어하우스(DW)

register Thesis proposal -> contact teacher -> topic -> Register Thesis -> Defend thesis at the end
