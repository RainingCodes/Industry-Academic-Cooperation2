# DID Web study에 연장선4
기반 프로젝트 (https://github.com/hyperledger/aries-cloudagent-python)
<br>

## 목표 6 : 로그 출력 완성하기
 1. 모든 ui 화면에 로그 출력 화면 적용하기
   - 기존에는 index.html에서만 로그를 출력하도록 구현되어 있음
   - index_ma.html & index_au.html도 로그가 출력되게 구성함
<br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img28.JPG" width="2000px" height="1300px" alt="ui with log"></img><br/>
 <br>

 2. 로그 파일의 분리
   - 기존엔 로그를 console에 출력되는 모든 걸 출력하도록 구성했음
   - manger / authenticator / client 별로 log가 각각 다른 파일에 등록되도록 파일 로직을 수정함
   - Custom Marker class를 만들어 manager, authenticator, client String 값을 정해둠
   - log를 출력하는 모든 곳에 manager/ authenticator / client에 해당하는 Marker를 넣음
   - 참고 사이트 : https://eclipse4j.tistory.com/276
   - 파일이 저장되는 위치
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img29.JPG" width="700px" height="300px" alt="log location"></img><br/>
   - 실행 화면
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img30.JPG" width="2000px" height="2000px" alt="uui with log2"></img><br/>