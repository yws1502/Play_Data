# SUB QUERY
- 쿼리(insert, delete, update, select) 안에서 select 쿼리를 사용하는 것.
- 보통 `delete`, `update`는 `where절`에 쓰임
- 메인 쿼리(밖) - 서브쿼리(안)

### 1. 서브쿼리 사용 구절
    - select절, from절, where절, having절
 
### 2. 서브쿼리 종류
- 어느 구절에 사용되었는지에 따른 구분
    - `스칼라 서브쿼리` : `select절`에 사용. 반드시 서브쿼리 결과가 1행 1열(값 하나-스칼라) 0행이 조회되면 null을 반환
    - `인라인 뷰` : `from절`에 사용되어 테이블의 역할을 한다.
- 서브쿼리 조회결과 행수에 따른 구분
    - `단일행 서브쿼리` : 조회결과 행이 한행인 것. - pk로 조회(조회 결과가 없거나 한행이 나오는거)
    - `다중행 서브쿼리` : 조회결과 행이 여러행인 것.
    - `단일행`|`다중행`에 따라 **연산자**가 달라진다.
- 동작 방식에 따른 구분
    - `select문`과 관계된다.
    - `비상관(비연관) 서브쿼리` 
        - 메인쿼리에 사용할 값을 서브쿼리가 제공하는 역할을 한다.
        - 안쪽에 있는 쿼리문이 바깥쪽 쿼리문과 상관없이 일한다.
        - ![메인컬서브컬](https://user-images.githubusercontent.com/77317312/106843016-69e51a00-66e8-11eb-87e5-5e7d6755a77d.PNG)
        
    - `상관(연관) 서브쿼리` 
        - 서브쿼리에서 메인쿼리의 컬럼을 사용한다. 
        - 메인쿼리가 먼저 수행되어 읽혀진 데이터를 서브쿼리에서 조건이 맞는지 확인하고자 할때 주로 사용한다.
        - 안쪽에 있는 궈리문이 바깥쪽 쿼리문과 연관있게 일한다.
        - ![상관쿼리관계](https://user-images.githubusercontent.com/77317312/106843048-7b2e2680-66e8-11eb-9cc0-74f0a70208d8.PNG)
                            

## **서브쿼리는 반드시 `( )` 로 묶어줘야 한다.**