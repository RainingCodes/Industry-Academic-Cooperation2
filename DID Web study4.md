# DID Web study에 연장선3
기반 프로젝트 (https://github.com/hyperledger/aries-cloudagent-python)
(https://github.com/sktston/acapy-controller-java)
<br>

## 목표 4 : controller에 기록되는 로그를 client 화면에 띄우기
 1. 작업 전 확인 사항 : manager와 authenticator를 통합하면서 client쪽 로직의 변화
   - client가 입력한 내용을 Command 객체로 받아서 전달됨
   - client가 입력한 내용을 manager에게 전달 후 credential 발급한 것을 바로 그 내용대로 발급받도록 변경됨
 2. 현재 프로젝트의 로그는 Slf4j을 이용하여 로그를 console에 기록하고 있음
   - 로그를 file로 저장해 그 파일을 읽어들여 화면에 출력하는 방식 채택
   - logback-spring.xml 파일을 아래 참고 자료를 이용해 수정
   - 로그 저장되는 위치 logs/log.txt로 저장
   - 참고 자료 : https://frozenpond.tistory.com/88
 3. 실시간 file 읽기 with JS
   - js로는 로컬에 있는 파일을 읽는 것이 보안상 불가능함
   - Chrome 확장 프로그램을 이용해서 해결할 수 있음 (https://stackoverflow.com/questions/39007243/cannot-open-local-file-chrome-not-allowed-to-load-local-resource)
   - Web Server for Chrome (https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb) 설치
   - log가 저장되는 폴더를 가상 서버로 실행시킴
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img25.JPG" width="300px" height="700px" alt="web server for chrome"></img><br/>
 <br>

   - iframe을 이용해 내용 출력
   - 매 실행시 로그 파일 변화를 반영할 때에는 js 이용
   - client 실행화면
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img26.JPG" width="2000px" height="1000px" alt="log"></img><br/>
 <br>

## 목표 5 : email 검증을 위해 email로 code 확인하기 위한 ui 추가
  1. 'validation' 버튼을 누르면 코드를 넣을 수 있는 input tag js로 생성
  2.  input tag에 입력한 값이 email로 전송된 code와 같은 지 확인하는 check button도 js로 같이 생성
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img27.JPG" width="2000px" height="700px" alt="log"></img><br/>
 <br>