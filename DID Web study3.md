# DID Web study에 연장선2
기반 프로젝트 (https://github.com/hyperledger/aries-cloudagent-python)
<br>

## 목표 3 : manager를 작업한 분의 작업물과 통합하기
   1. DID Web study2에서 작업한 manager controller, service에 했던 것과 동일한 로직으로 구현한 것을 확인함
   2. controller와 service에 client와 통신하는 부분만 일단 추가해서 작업하도록 해둠 <br>
   * 기반 : manager 작업하신 분꺼에 DID Web study2에 구현된 일부 기능 추가<br>
   * manager --> client 통신 로직 추가 
    <br>
   3. 웹 UI를 manager / authenticator가 같은 구조로 되어있어서 client쪽도 내용츨 추가함 <br>
   * 기반 : DID Web study2에서의 index.html <br>
   * 일부 field 명 변경 (authentication type, email, id, birthday, photo로 field 명 보이게 함) <br>
   * Register Information에 성공한 것을 client쪽에서 확인 가능하도록 View Information 항목 추가 (manager 쪽에서 가져옴 + 일부 내용 client에 맞게 수정) <br>
      - Register 후 생기는 버튼이 toggle로 작동 <br>
   * Log 출력하는 항목 추가 (manager 쪽에서 가져옴)
   <br>
   4. 실행 결과
   - client : Make Connection 버튼 클릭
   - client : Connection Id 출력 (출력 후 다음으로 진행)
   - manager : Create Schema 항목 체크 (필요하다면 필드 추가)
   - manager : Create Schema 버튼 틀릭
   - manager : Create Schema Success 출력 (출력 후 다음으로 진행)
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img22.JPG" width="2000px" height="1000px" alt="result1"></img><br/>
 <br>
   - client : Register Information 버튼 클릭 (Result 내용 출력도 동시에 발생)
   - client : field 작성
   - client : submit 버튼 클릭
   <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img23.JPG" width=300px" height="1000px" alt="result2"></img><br/>
 <br>
   - client : SSO(생성한 Authentication Type으로 생성된) 버튼 클릭
   <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img23.JPG" width=250px" height="1000px" alt="result3"></img><br/>