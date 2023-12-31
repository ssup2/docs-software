---
title: 정보처리기사 자격증 이론 정리
---

## 1. DB

### 1.1. SQL 종류

* DDL (Data Definititon Language)
  * CREATE : Table 생성한다.
    * ex) CREATE TABLE Persons ( PersonID int, LastName varchar(255) );
  * ALTER : Table 변경한다.
    * ex) ALTER TABLE Persons ADD Email varchar(255);
    * ex) ALTER TABLE Persons DROP Email;
    * ex) ALTER TABLE Persons MODIFY ( Email varchar(128) );
    * ex) ALTER TABLE Persons RENAME Email TO Address;
  * DROP : Table을 삭제한다.
    * ex) DROP TABLE Persons; 
  * TRUNCATE : Table의 모든 내용을 삭제한다.
    * ex) TRUNCATE TABLE Persons;
* DML (Data Manipulation Language)
  * SELECT : Table에서 Data를 읽는다.
    * ex) SELECT PersonID, LastName FROM Persons WHERE PersonID = 1;
    * ex) SELECT PersonID, LastName FROM Persons WHERE PersonID IN (1, 2);
    * ex) SELECT PersonID, LastName FROM Persons BETWEEN 1 AND 10;
    * ex) SELECT * FROM Persons;
  * INSERT : Table에 Data를 넣는다.
    * ex) INSERT INTO Persons (PersonID, LastName) VALUES (1 , ssup2);
  * UPDATE : Table의 Data를 변경한다.
    * ex) UPDATE Persons SET PersonID = 10 WHERE LastName = 'ssup2';
  * DELETE : Table의 Data를 삭제한다.
    * ex) DELETE FROM Persons WHERE PersonID = 1;
* DCL (Data Control Language)
  * COMMIT : 변경내용을 반영한다.
  * ROLLBACK : 변경내용을 반영하지 않고 되돌린다.
  * GRANT : 사용권한을 부여한다.
  * REVOKE : 사용권한을 제거한다.

### 1.2. Table 구성 

* Degree : Row (Attributes, Tuble, Record) 개수
* Cardinality : Colunm 개수
* 슈퍼키 (Super Key): 각 행을 유일하게 식별할 수 있는 하나 또는 그 이상의 속성들의 집합을 의미한다.
* 후보키 (Candidate Key) : 각 행을 유일하게 식별할 수 있는 최소한의 속성들의 집합을 의미한다.
* 기본키 (Primary Key) : 후보키들 중에서 하나를 선택한 키를 의미한다.
* 대체키 (Alternate Key) : 후보키가 두개 이상일 경우 그 중에서 어느 하나를 기본키로 지정하고 남은 후보키들을 대체키라한다.
* 외래키 (Foreign Key) : Table 사이의 관계를 나타내기 위해 이용하는 Key를 의미한다.

### 1.3. Index

* Clustered Index : 영어사전 형태의 Index를 의미한다. 각 Table당 하나밖에 존재하지 못한다.
* Non-Clustered Index : 책의 찾아보기 형태의 Index를 의미한다. 각 Table당 여러개가 존재할 수 있다.

### 1.4. 정규화

* 완전 함수적 종속성 : 하나의 속성이 모든 기본키에 종속하는 경우를 의미한다.
* 부분 함수적 종속성 : 하나의 속성이 일부 기본키에 종속하는 경우를 의미한다.
* 이행적 함수 종속성 : X->Y, Y->Z 일때 X->Z의 관계를 갖는 경우를 의미한다.
* 1NF : 하나의 속성이 단일값을 갖도록 변경하는 과정을 의미한다.
* 2NF : 1NF 조건을 만족시키면서 완전 함수적 종속성을 만족시키도록 변경하는 과정을 의미한다.
* 3NF : 2NF 조건을 만족시키면서 이행적 함수 종속성을 제거하는 과정을 의미한다.
* BCNF : 3NF 조건을 만족시키면서 결정자 함수 종속성을 제거하는 과정을 의미한다.
* 4NF : BCNF 종건을 만족시키면서 다중값 종속성을 제거하는 과정을 의미한다.
* 5NF : 4NF 조건을 만족시키면서 결합 (Join) 종속성을 제거하는 과정을 의미한다.

### 1.5. 이상 (Anomaly)

* 삽입이상 : 데이터를 삽입할 경우, 원하지 않는 데이터까지 삽입해야하는 현상을 의미한다.
* 갱신이상 : 데이터를 갱신하는 경우, 일부의 데이터만 변경되어 정합성이 깨지는 현상을 의미한다.
* 삭제이상 : 데이터를 삭제하는 경우, 원하지 않는 데이터까지 삭제해야하는 현상을 의미한다.

### 1.6. Transaction ACID

* 원자성 (Atomicity) : Transaction은 수행되거나 수행되지 않거나 2가지 상태만을 갖는다. 
* 일관성 (Consistency) : Transaction 수행후에도 일관성이 유지되어야 한다.
* 격리성 (Isolation) : Transaction은 다른 Transaction의 동작에 영향을 주면 안된다.
* 지속성 (Durability) : 수행 완료된 Transaction은 영원히 반영되어야 한다.

### 1.7 관계대수

* 합집합 U
* 교집합 ∩
* 차집합 -
* 교차곱 X

### 1.8 순수 관계 연산자

* Select σ : 조건을 만족하는 튜플을 구하는 연산을 의미한다.
* Project π : 튜플중에서 특정 속성만 추출하는 연산을 의미한다.
* Join ⋈ : 두 개의 릴레이션의 공통 속성으로 합쳐서 하나의 릴레이션을 생성하는 연산을 의미한다.
* Division ÷ : 두 개의 릴레이션에 모두 있는 속성을 가진 튜플에서 우항에 있는 속성만 구하는 연산을 의미한다.

### 1.9 Scheme

* 외부 스키마 : 외부 스키마는 사용자가 프로그래머가 각 개인의 입장에서 필요로 하는 데이터베이스의 논리적 구조를 의미한다.
* 개념 스키마 : 개념 스키마는 데이터베이스의 전체적인 논리적 구조를 의미한다.
* 내부 스키마 : 내부 스키마는 물리적 저장장치의 입장에서 본 데이터베이스의 구조를 나타낸다.

### 1.10 ETC

* 참조 무결성 : 참조할 수 없는 외래키값을 가질수 없음을 의미하는 제약 조건을 의미한다.
* 시스템 카탈로그 : 시스템 자신이 필요하는 여러가지 객체에 관한 정보를 포함하고 있는 시스템 테이터베이스를 의미한다.
* 데이터 웨어하우스 : 의사결정 지원을 위한 별도의 데이터베이스를 의미한다.

## 2. 업무프로세스

* ERP (Enterprise Resource Planning) : 기업 자산 관리
* CRM (Customer Relationship Management) : 고객 관계 관리
* SCM (Supply Chain Management) : 공급 사슬 관리
* EIP (Enterprise Integration Patterns) : 기업 통합 정보 시스템

## 3. 참조

* DB Table Key : [https://jerryjerryjerry.tistory.com/49](https://jerryjerryjerry.tistory.com/49)


