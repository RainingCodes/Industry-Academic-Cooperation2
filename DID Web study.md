기반 프로젝트 (https://github.com/hyperledger/aries-cloudagent-python)
(https://github.com/sktston/acapy-controller-java)


# 1. 기본적인 웹 구조 확인
 * localhost:8041 --> client 화면
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img7.JPG" width="1300px" height="500px" alt="index"></img><br/>
 * localhost:8040/index_ma --> manager 화면
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img8.JPG" width="1300px" height="500px" alt="index_ma"></img><br/>
<br><br>
 * client 화면에서의 요청 list
   - Make Connection
   - Get DID Credential
   - Prove DID Credential
   - Revoke DID Credential
 * client 화면에서의 Result (각 요청별 결과 표시)
<br><br>
 * 사용된 기술 list
   - docker (container)
   - swagger(docker container에서 실행됨) & von-network
   - spring
   - js(+ jQuery), html
<br><br>

# 2. 요구사항 (추가될 예정)
## 목표 : client 화면의 정보 --> client controller --> manager controller로 전달
<br>
  1.  client 화면의 정보 --> controller 전달 처리 : SSO 인증서 기본 form 제작 (아주 기본적인 form, 추후 수정 가능성 O)
   <br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img9.JPG" width="700px" height="550px" alt="form"></img><br/>
    위와 같이 form을 만들고 js(+ jQeury)를 이용하여 json형식으로 값을 controller에게 전달(RequestBody로 넘어감) <br>
    Client Controller에서 Request Body를 전달받아 Client Service로 전달  
  <br><br>

  2.  SSO 인증서 기본 form에 입력한 정보를 manager & authenticator service에 전달
   * 분석대상 : swagger api/doc#/ (docker 실행후 localhost:8021 접속하면 이용 가능한 rest service 규칙 확인 가능함)
   * service는 swagger를 이용해 통신하는 것으로 추정
   * 눈여겨 본 document
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img9.JPG" width="1300px" height="1000px" alt="swagger_basicmessage"></img><br/>

   * content에 2(요구사항) - 1번에서 전달받은 form의 내용을 다른 controller로 전달할 수 있을 것으로 확인됨
   * connectionId가 있어야 이용할 수 있음
   * 1(기본적인 웹 구조) client 화면에 표시된 버튼 중 makeConnection 후에 정보를 controller로 전달하도록 button 추가
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img12.JPG" width="500px" height="500px" alt="register information button"></img><br/>
   
   * client service에서 manager service로 값을 전달 + manager service에서 값을 받아 등록
<br><br>
요구사항을 반영한 실행 화면

* client 화면에서 Make Connection 실행 -> filed 입력 후 Register Information 실행(email, nickname, birth만 전달됨테스트함)
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img13.JPG" width="1000px" height="700px" alt="connect&register"></img><br/>
 <br>

* client 서버의 실행 로그
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img14.JPG" width="1000px" height="300px" alt="log1"></img><br/>
 <br>

* manager 서버의 실행 로그 (필요한 부분만 남기고 다른 부분 제거)
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img15.JPG" width="1000px" height="300px" alt="log2"></img><br/>
 <br>

* client 화면에서 Get DID Credential -> Prove DID Credential 실행
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img16.JPG" width="1000px" height="700px" alt="did"></img><br/>
 <br>

* authenticator 서버의 실행 로그
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img17.JPG" width="1000px" height="300px" alt="authenticator"></img><br/>
 <br>