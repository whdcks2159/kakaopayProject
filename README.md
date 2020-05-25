# kakaopayProject
kakaopayProject

● 실행환경

- tomcat 8.5
- JDK 1.8

● 개발 프레임워크

- SpringMVC

● 테이블 설계

- 데이터를 담기위한 테이블 (SETTINFO)

settSeq(관리번호, PrimaryKey) , oriManageNo(오리지날 관리번호, 결제취소의 경우에만 있음), settInfoStr (string 데이터)
조회시 취소데이터들의 찾기위해 oriManageNo 컬럼값 추가

- 현재 남은 금액 확인용 테이블 (CURSETTINFO)

manageNo(관리번호), settAmt(결제금액), settAmt(부가가치세)

● 문제해결 전략

코드로 배우는 스프링 웹 프로젝트 참고

EnterController에서 웹 화면을 띄워 MainController(RESTController)로 데이터를 보내 API통신

결제

데이터를 받아 카드정보는 암호화하고 하나의 String데이터로 만들고 SEQ만들어 관리번호로 사용하여 SETTINFO 테이블에 삽입 후 관리번호 노출.

현재 결제한 금액이 얼마 남았는지 알기 위해 관리번호, 결제금액, 부가가치세데이터를 CURSETTINFO 테이블에 삽입.

결제취소

오리지날 관리번호, 취소금액 데이터를 받아 기존 결제 정보를 조회하여 기존 정보와 오리지날 관리번호, 취소금액을 String데이터로 만들고 SEQ만들어 관리번호로 사용하여 SETTINFO 테이블에 삽입 후 관리번호 노출.

현재 결제한 금액이 얼마 남았는지 알기 위해 관리번호, 결제금액, 부가가치세데이터를 CURSETTINFO 테이블에 결제금액에서 취소데이트를 뺀 값을 업데이트.

조회

관리번호를 가지고 string데이터를 찾아 하나씩 잘라 SettInfo 객체에 담아 결과값 노출.

● 실행방법

http://localhost:8080/enter /enter

결제, 결제취소, 조회

결과값 - pop창으로 노출(json형식으로)
