# kakaopayProject
kakaopayProject

● 실행환경
- tomcat 8.5
- JDK 1.8

● 개발 프레임워크
- Spring

● 테이블 설계

데이터를 담기위한 테이블
SETTINFO - settSeq(관리자번호,Seq) , oriManageNo(오리지날 관리자번호, 결제취소의 경우에만 있음), settInfoStr (string 데이터)

현재 남은 금액 확인용 테이블
CURSETTINFO - manageNo(관리자번호), settAmt(결제금액), settAmt(부가가치세)

● 문제해결 전략
코드로 배우는 스프링 웹 프로젝트 참고

● 실행방법
http://localhost:8080/enter /enter
결제, 결제취소, 조회
결과값 - pop창으로 노출(json형식으로)
