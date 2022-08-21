# DID Android study에 연장선
기반 프로젝트 (https://github.com/sktston/vcx-demo-android)
<br>

## 목표 2 : Android client 화면에 로그를 출력하라
참고 사이트 : (https://coderwall.com/p/s0wo3q/android-read-the-logcat-programmatically)
   * 지난번과 달리 server가 작동하는 상태의 Android App Project를 전달받음
       - Android App에서 버튼을 누르면 log가 태그와 함께 출력되고 있는 상황
       - 실행 화면
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img42.jpg" width="300px" height="500px" alt="default"></img><br/>

   * Android App 화면에 logcat에 출력되는 로그 출력하는 방법 : https://coderwall.com/p/s0wo3q/android-read-the-logcat-programmatically
     - Runtime.getRuntime().exec(), StringBuilder를 이용해 출력
     - 전체 로그를 아래 textview에 출력하도록 구성
     - 실행 화면
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img43.jpg" width="300px" height="500px" alt="full logs"></img><br/>

  * 지정한 Tag의 로그만 출력하는 방법
     - 전체 로그를 출력할 때에 logcat에서 한 줄씩 읽어와 StringBuilder에 추가하는 반복문이 수행되고 있음
     - 그 한 줄에 지정한 Tag가 포함되어있으면 textview에 넣고 그렇지 않으면 넣지 않도록 logic 수정
     - switch button을 이용해 off일땐 message가 보이지 않도록 하고, on일땐 message가 보이도록 설정함(https://developer.android.com/guide/topics/ui/controls/togglebutton?hl=ko & https://stackoverflow.com/questions/5052288/how-can-i-hide-show-an-element-when-a-button-is-pressed)
     - 실행 화면
    <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img44.jpg" width="300px" height="500px" alt="logs off"></img> <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img45.jpg" width="300px" height="500px" alt="logs on"></img><br/>


## 목표 3 : 웹과 동일하게 동작하도록 Android 화면을 구성하라
  * Make Connection 후에 Register Information 버튼을 누르도록 지정 (field 입력 후 Issue Credential을 수행하도록)
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img46.jpg" width="300px" height="500px" alt="Button Change"></img><br>

  * DID Android study에 적용했던 사용자가 입력하는 필드 화면 적용 (사진 필드 추가)
  * 화면의 크기가 작으므로, 새로운 Activity를 호출하도록 지정 (Schema로 지정된 값만 화면에 보이도록 설정)
  * 응답 message 중 schema에 대한 정보는 따로 parsing 하도록 지정
  * 날짜 선택은 사용자가 입력하기 편하게 date picker 적용
  * 사진 선택은 사진 부분을 누르면 갤러리에서 선택할 수 있도록 구성

  <br> <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img47.jpg" width="300px" height="500px" alt="new Activity"></img> <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img48.jpg" width="300px" height="500px" alt="date picker"></img><img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img49.jpg" width="300px" height="500px" alt="call gallery"></img><img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img50.jpg" width="300px" height="500px" alt="sample"></img><br/>