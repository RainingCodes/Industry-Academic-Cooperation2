# DID Web study에 연장선
기반 프로젝트 (https://github.com/hyperledger/aries-cloudagent-python)
<br>

## 목표 2 : manager가 생성한 field 값만 client에게 입력받기
1. index_ma 화면에서 manager가 client에게 입력받을 field 정보(schema) 요청하도록 변경
   * 첫화면에 Create Schema 버튼 추가
   * Create Schema 버튼을 누르면 요청할 필드에 대한 정보가 보이며 체크박스 선택시 그 필드를 schema에 추가할 것을 의미
   * Add Field 버튼을 누르면 manager가 새로 요청받을 field를 입력하는 input field와 생성한 field를 제거할 Remove Field가 나타남
   * Remove Field 누르면 해당 field 제거
   * Submit 버튼을 누르면 manager가 요청한대로 서버에 요청함
   * 기존 코드는 manager 서버 실행시 schema를 생성하는 로직이 들어가 있어서 그 부분을 주석처리 (schema 등록은 manager에 요청에 의해서만 등록되게 함)
   * schema를 manager가 등록하고 client에게 schema id를 전달하기 위해서는 client 쪽의 connection이 생성되어 있어야 함
   * submit 버튼 누르면 schema가 생성되고 schema id가 client에게 전달됨 & 모든 처리가 끝나면 Result에 "Schema Creation Success!!!"란 문구가 생김

2.  index 화면 수정, manager가 요청한 필드만 보이게하기
   * DID Web study에서는 처음부터 field가 전부 보였지만 이번엔 안보이게 설정
   * Make Connection을 누르고 Manager 쪽에서 Create Schema, Submit을 누른 후에 Register Information을 누르면 Manager가 요청한대로 필드를 선별해서 볼 수 있음
   * 사용자가 추가한 필드는 기본적으로 text 타입으로 입력받게 설정함
   * Field를 입력하고 Submit 버튼을 누르면 인증서가 생성되도록 함

3. 실행과정과 실행 화면
    - client 화면에서 Make Connection 클릭 <br>
    - manager 화면에서 Create Schema 클릭 <br>
    - manager 화면에서 client에게서 입력받고자하는 field 선택
    - manager 화면에서 Submit 버튼 클릭 (오래 걸림)
  <br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img19.JPG" width="1000px" height="700px" alt="result1"></img><br/>
    - manager 화면에서 Result가 출력된 걸 먼저 확인함
    - client 화면에서 Register Information을 누르면 manager가 등록한 schema에 맞는 field들이 선택되어 나옴
    - field 입력후 Submit 버튼 클릭

 <br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img20.JPG" width="1000px" height="1200px" alt="result2"></img><br/>
 <br>
    - client server에서 전달내용을 확인할 수 있음
  
 <br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img21.JPG" width="1000px" height="1200px" alt="result3"></img><br/>
 <br>