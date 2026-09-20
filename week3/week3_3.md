# SQL_ADVANCED 3주차 정규 과제 

📌SQL_ADVANCED 정규과제는 매주 정해진 분량의 『*혼자 공부하는 SQL*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **SQL_ADVANCED_3rd_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=1YmWy-7-OhQ&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=10
https://www.youtube.com/watch?v=tuQFkzjqEGw&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=11
https://www.youtube.com/watch?v=IOCsreDYqFE&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=12
-->

**교재 실습 예제 파일은 08_SQL_ADVANCED_Template 레포지토리의 src 폴더에 업로드되어 있습니다. market_db 파일도 해당 폴더에 함께 포함되어 있으니 참고하시기 바랍니다.**

**👀(수행 인증샷은 필수입니다.)** 

## SQL_ADVANCED_3rd_TIL

### 4장 SQL 고급 문법
#### 01. MySQL의 데이터 형식
#### 02. 두 테이블을 묶는 조인
#### 03. SQL 프로그래밍 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~99    | ✅         |
| 2주차 | p.102~155   | ✅         |
| 3주차 | p.158~213  | ✅         |
| 4주차 | p.216~271 | 🍽️         |
| 5주차 | p.274~327 | 🍽️         |
| 6주차 | p.330~369 | 🍽️         |
| 7주차 | p.372~407 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. MySQL의 데이터 형식

<!-- MySQL의 데이터 형식에 관해 배우게 된 점을 적어주세요. -->
#### 정수형
인원 수, 가격, 수량 등에 많이 사용. 정수형에 UNSIGHNED를 붙이면 범위가 0부터 지정됨

#### 문자형
입력할 최대 글자의 개수를 지정해야됨. 대표적인 문자형으로는 CHAR(개수) - 자릿수가 고정됨
VARCHAR(개수) - 가변길이 문자형
VARCHAR이 CHAR보다 공간을 효율적으로 운영할 수 있지만, 내부적으로 성능면에서는 CHAR이 더 낫다

#### 대량의 데이터 형식
TEXT: 최대 65535까지 저장
LONGTEXT: 최대 42억자까지 저장
BLOB: 이진 데이터. 사진이나 동영상 저장

#### 실수형
소수점이 있는 숫자 저장
FLOAT: 소수점 아래 7자리까지 표현
DOUBLE: 소수점 아래 15자리까지 표현

#### 날짜형
DATE는 날짜만, TIME은 시간만 저장
둘다 저장하고 싶을 땐 DATETIME

### 변수의 사용
다른 언어들처럼 변수를 선언하고 사용
SET 변수이름
SELECCT 변수이름

### 데이터 형 변환
명시적인 변환: CAST(), CONVERT() - 형식만 다를뿐 둘다 동일한 기능
암시적인 변환: CAST나 CONVERT함수 사용하지 않고 자연스럽게 형이 변환

<!-- 과제 설명 예시처럼 직접 실습 후 사진 한 장 이상을 첨부해주세요. -->
![alt text](<화면 캡처 2026-09-20 223308.png>)



> **확인문제: 다음 보기에서 데이터 형식의 변환에 사용되는 함수를 2개 고르세요.**

보기는 아래와 같습니다.
```
CONVERT() / DATA() / CAST() / MOVE() / TYPE() / SUM() / AVG() / CURRENT_DATE()
```

```
CAST(), CONVERT()
```


## 2. 두 테이블을 묶는 조인

<!-- 두 테이블을 묶는 조인에 관해 배우게 된 점을 적어주세요. -->
### 내부 조인

SELECT 열목록
FROM 첫번째 테이블
    INNER JOIN 두번째 테이블
    ON 조인될 조건
WHERE 검색 조건;

내부 조인은 두 테이블에 모두 있는 내용만 조인됨. 만약 양쪽 중에 한곳이라도 내용이 있을 때 조인하려면 외부 조인 사용

### 외부 조인
두 테이블을 조인할 때 필요 내용이 한테이블에만 있어도 결과 추출 가능

SELECT 열 목록
FROM 첫 번째 테이블
    LEFT OUTER JOIN 두 번째 테이블
    ON 조인될 조건
WHERE 검색 조건;

#### 기타 조인
상호조인: 한쪽 테이블의 모든 행과 다른 쪽 테이블의 모든 행을 조인
on 구문 사용 못함. 랜덤 조인이므로 결과내용에 의미 없음.

#### 자체 조인
자신이 자신과 조인. 1개의 테이블 사용


<!-- 과제 설명 예시처럼 직접 실습 후 인증 사진 4장 이상을 첨부해주세요. -->
![alt text](<화면 캡처 2026-09-20 225144.png>)
![alt text](<화면 캡처 2026-09-20 225329.png>)
![alt text](<화면 캡처 2026-09-20 225531.png>)
![alt text](<화면 캡처 2026-09-20 225944.png>)


> **확인문제: 다음 SQL은 회원으로 가입만 하고, 한 번도 구매한 적이 없는 회원의 목록을 조회하는 쿼리입니다. 빈칸에 들어갈 가장 적절한 구문을 고르세요..**

```sql
SELECT DISTINCT M.mem_id, B.prod_name, M.mem_name, M.addr
  FROM member M
    LEFT OUTER JOIN buy B
    ON M.mem_id = B.mem_id
  __________
  ORDER BY M.mem_id;
```
보기는 아래와 같습니다.
```
1. JOIN B.prod_name IS NULL
2. LIMIT B.prod_name IS NULL
3. HAVING B.prod_name IS NULL
4. WHERE B.prod_name IS NULL
```
```
4번. 이 쿼리는 member 테이블과 buy 테이블을 left outer join으로 연결함. buy테이블 컬럼에서 NULL값만 가지는 행을 필터링하기 위해선 4번 구문이 들어가야함. 
```

## 3. SQL 프로그래밍 

<!-- IF문, CASE문, WHILE문에 관해 배우게 된 점을 적어주세요. -->

### IF문
IF 조건식 THEN
END IF;
두문장 이상 처리될 때는 BEGIN~END로 묶어줘야함

IF ~ ELSE 문은 조건에 따라 다른 부분을 수행함. 

### CASE문
2가지 이상의 여러가지 경우일때 처리가 가능한 '다중 분기'(IF ELSE는 참아니면 거짓 2가지만)
CASE와 END CASE 사이에는 여러 조건을 넣을 수 있음. 


### WHILE문
필요한 만큼 계속 같은 내용을 반복한다
WHILE 조건식 DO
    SQL문장들
END WHILE;

ITERATE: 지정한 레이블로 가서 계속 진행
LEAVE: 지정한 레이블을 빠져나감. WHILE문의 종료

### 동적 SQL
PREPARE:SQL을 실행하지는 않고, 미리 준비해놓음
EXECUTE:준비한 SQL문을 실행
실행후에는 DEALLOCATE PREPARE로 문장 해제


> **확인문제: 다음은 CASE 문의 형식입니다. 빈칸에 들어갈 가장 적절한 명령어를 보기에서 고르세요..**

```sql
CASE
    (1) 조건 THEN
        SQL문장들1
    ELSE
        SQL문장들4
END (2);
```

보기는 아래와 같습니다.
```
WHEN / THEN / CURRENT / DATE / TIME / IF / END IF / CASE
```

```
여기에 답을 적어주세요!
(1) WHEN
(2) CASE
```


---

# 2️⃣ 실습과제

## 1. 데이터베이스 구축

아래 코드를 MySQL Workbench에 붙여넣은 후,  
**전체 드래그 → 실행 (Ctrl + shift + Enter)** 하여 데이터베이스를 구축하세요.

```sql
-- 1. 데이터베이스 생성
CREATE DATABASE IF NOT EXISTS week3_db;

-- 2. 사용할 데이터베이스 선택
USE week3_db;

-- 3. 기존 테이블 삭제 (초기화용)
DROP TABLE IF EXISTS orders;
DROP TABLE IF EXISTS customers;

-- 4. 테이블 생성 (조인 실습용)
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    name VARCHAR(20),
    signup_date_str VARCHAR(8) 
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,           
    order_date_str VARCHAR(8), 
    amount_str VARCHAR(10)     
);

-- 5. 데이터 삽입
INSERT INTO customers VALUES
(1, '신영', '20241528'),
(2, '경모', '20220261'),
(3, '세원', '20203401'),
(4, '진우', '20221024'),
(5, '성환', '20225100'),
(6, '혜준', '20244946'),
(7, '채은', '20250412'),
(8, '다나', '20212774'); -- 주문 없는 고객(외부 조인용)

INSERT INTO orders VALUES
(101, 1, '20240220', '12000'),
(102, 1, '20240303', '30000'),
(103, 2, '20240111', '15000'),
(104, 3, '20221201', '9000'),
(105, 5, '20231111', '20000'),
(106, 7, '20220707', '5000'),
(107, 99, '20240210', '7000'); -- 고객 테이블에 없는 customer_id (외부 조인용)
```

## 2. 실습 문제

다음 SQL 문을 작성하고 실행 결과를 확인 후 인증 사진을 아래에 업로드하세요.

1. **데이터 형식 변환**
   - orders 테이블의 `order_date_str`을 DATE 형식으로 변환하여 조회하시오.
   (힌트: STR_TO_DATE 사용)

2. **데이터 형식 변환**
   - orders 테이블의 `amount_str`을 숫자형으로 변환하여 조회하시오.

3. **내부 조인 (INNER JOIN)**
   - customers와 orders를 customer_id 기준으로 내부 조인하여
     고객 이름(name)과 주문 번호(order_id)를 함께 조회하시오.

4. **외부 조인 (LEFT JOIN)**
   - customers를 기준으로 LEFT JOIN을 수행하여,
     주문이 없는 고객도 함께 조회하시오.

5. **스토어드 프로시저 (IF문 사용)**
   - 입력받은 금액이 10000 이상이면 '고액 주문',
     그렇지 않으면 '일반 주문'을 출력하는
     프로시저를 생성하시오.
   - 생성 후 CALL로 실행 결과를 확인하시오.

![alt text](<화면 캡처 2026-09-20 234524.png>)
![alt text](<화면 캡처 2026-09-20 234552.png>)
![alt text](<화면 캡처 2026-09-20 234615.png>)
![alt text](<화면 캡처 2026-09-20 234640.png>)
![alt text](<화면 캡처 2026-09-20 234812.png>)
### 🎉 수고하셨습니다.






