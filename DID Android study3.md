# DID Web + Android study의 연장선
기반 프로젝트 (https://github.com/sktston/vcx-demo-android)

## 목표 1 안드로이드 앱을 종료시켰다 다시 켰을 때 정보 불러오기

 * 발생했던 문제
    - Button을 다시 누르면 새로 요청을 시도함 (wallet, connection이 새로 됨)
    - 기존에 Register Information을 눌렀을 경우에 나타나는 Activity는 edit text, date picker, gallery 사진 선택 등을 하는 수정 가능한 form  
    - 사진을 gallery를 통해서 불러올 경우 그 경로가 외부 경로라서 다시 그 사진을 불러오기 어려움
    - default 사진을 drawable에 있는 ic_foreground_icon으로 지정되어 있었음

 * 해결방안
    - SharedPreferences : 앱 종료 후 다시 실행시켰을 때 정보가 남아있을 수 있도록 key, value 쌍을 저장해 두는 방법
    - SharedPreferences에 wallet, connection 여부, 사용자의 정보를 저장하도록 변경
    - 변경이 불가능하도록 입력한 정보들이 textview, imageview가 고정인 화면 새로 추가
    - 갤러리에서 선택한 사진을 앱 내 저장소에 저장하도록 함
    - schema에 photo가 포함되어 있을 때 기본 이미지 파일을 jpg 파일로 설정함


 * 참고했던 사이트
   - https://stickode.tistory.com/211
   - https://minggu92.tistory.com/8
  