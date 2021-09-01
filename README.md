# Introduction
 Search the information of DM

# Database 

* 튜블(Record)(세로줄)

* 칼럼(Attribute)(가로줄)

* 식별자(identifier)(아이디가 대표적)

# Entity & Relationship model (객체 관계 모델)
Entity - 객체

* Arribute type
    Simple
    Composite           ㄱ
    Multiple-Value      --- in general
    Derived             -  derivable from value of a related attribute, or set of attributes, not necessarily in the same entity type

* Weak Entity type
    No key attribute.
    must participate in an identifying relationship type with an owner or entity type.
    Combination of - partial key + particular entity

* Concepts
    - Structural constraints
    - Cardinality ratio (functionality)


# SQL (Structured Query Language, 구조화 질의어)
관계형 데이터베이스 관리 시스템의 데이터 관리를 위한 국제 표준 언어
* 언어
    + 정의
        CREATE      - 새로운 관계(테이블), VIEW, 인덱스, 저장 프로시저 만들기
        DROP        - 이미 존재하는 데이터베이스 관계(테이블), 뷰, 인덱스, 저장 프로시저를 제거
        ALTER       - 이미 존재하는 데이터베이스 개체에 대한 변경, RENAME
        TRUNCATE    - 행(레코드) 삭제
    + 조작
        SELECT      - 검색
        INSERT      - 삽입
        UPDATE      - 업데이트,수정
        DELETE      - 삭제
    + 제어
        GRANT       - 권한 부여
        REVOKE      - 권한 박탈
        - 권한
            CONNECT- 데이터베이스 또는 스키마에 연결하는 권한
            SELECT - 데이터를 검색하는 권한
            INSERT - 데이터를 등록할 수 있는 권한
            UPDATE - 데이터를 업데이트 할 수 있는 권한
            DELETE - 데이터를 삭제할 수 있는 권한
            USAGE - 스키마 또는 함수와 같은 데이터베이스 개체를 사용할 수 있는 권한
* 장단점
    - 장점
        High performance
        No code needed
        Well defined standards
        Portability
        Structured system
        Multiple data views
    - 단점
        Complexity
        Cost
        Partial Control
        Scalability and Flexibility


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
