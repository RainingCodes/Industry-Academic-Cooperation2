# DID Android study2와 DID Web study 5에 연장선
기반 프로젝트 (https://github.com/sktston/vcx-demo-android)
<br>

## 목표 1 multi client의 요청을 구분해서 받을 수 있도록 client server와 client android를 수정하라

  * web server의 수정사항
    - 문제상황 1 : 기존 프로그램은 전역변수를 주로 이용하고 있어 단일 client만을 신경 씀
    
    - 문제상황 2 
    <br>client의 구분 기준 --> connectionID는 manager와 통신 하기 위해 필요한 수단, 각 client의 구분은 <b><i>JWT(JSON WEB Token)</i></b>을 통해서 할 수 있음

    - 문제상황 3
    <br> Log를 찍을 때 ,와 +를 혼동해 제대로 출력되지 않는 error 발생

    <br> 모든 요청을 처리할 때 JWT를 전역변수로 이용하는 것이 아니라, 매 요청시 client에게서 전달받은 값을 이용하도록 처리 필요
    - <del>문제상황 3 : 로그 출력을 안 하는 버전으로 전달받음 </del>
    <br>(모든 작업이 마무리되면 추가해도 됨) 

  * Android의 수정사항
   - 문제상황 1
    <br>web server 쪽 변수명과 Android 쪽의 변수명을 달리해서 error 발생
   - 문제상황 2
    <br>Android에서 JSON으로 data를 담을 때 / 문자가 포함되어 있으면 앞에 \가 추가되는 문제 발생

  * 문제 해결
  - client의 wallet, connection 등의 정보를 담는 class 추가
  - 정보를 담아서 list에 보관하고 JWT를 이용해 현재 요청중인 client를 찾아서 해결하도록 함
  - birthday를 처리할 때 /가 포함되지 않도록 변경
 