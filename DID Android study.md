기반 프로젝트 (https://github.com/sktston/vcx-demo-android)

# 1. 프로젝트 실행 환경 구성
 * wget download(https://eternallybored.org/misc/wget/)
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img32.JPG" width="1600px" height="700px" alt="wget download"></img><br/>
   - C:/Windows/System32에 exe 파일 이동
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img33.JPG" width="1500px" height="300px" alt="move wget.exe"></img><br/>
 * git bash에 아래 명령어 입력, demo program src 다운로드 <br>
  ```
  $ git clone https://github.com/sktston/vcx-demo-android.git
  ``` <br>
 * Anroid studio로 다운받은 프로젝트 open
   - 상단 메뉴에서 Tools > SDK Manager click
   - 새로 뜬 창에서 Sdk Tools 탭 click, Show Package details 버튼 check, NDK 20.1.XXX 버전 check, OK 버튼 click
   <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img31.JPG" width="1500px" height="1000px" alt="NDK download"></img><br/>
   - 상단 메뉴에서 File > Project Structure click
   - 새로 뜬 창에서 SDK Location 탭 click
   - 아래와 같이 ndk location 지정
   <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img36.JPG" width="1000px" height="700px" alt="NDK location"></img><br/>
   - build.gradle(Module)에서 ndk 부분을 아래와 같이 수정
  ```
  ndk { abiFilters 'armeabi-v7a', 'arm64-v8a' }
  ```
  ```
   - Sync Now click

 * populate_libraries.sh 수정
   - 주석을 바꿈, armeabi-v7a, arm64-v8a 부분을 활성화
    <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img37.JPG" width="1000px" height="300px" alt="edit populate_libraries.sh 1"></img><br/>
  <br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img39.JPG" width="1000px" height="700px" alt="edit populate_libraries.sh 2"></img><br/>
 * populate_libraries.sh 실행
 * android 프로젝트에서 app\jniLibs 아래에 arm64-v8a, armeabi-v7a 폴더 생성후 위에 지정한 ndk 폴더에 직접 가서 sources\cxx-stl\llvm-libc++\libs\\(넷중아무거나)\libc++_shared.so 파일을 복사
  - 아래처럼 프로젝트 app\jniLibs에 붙여넣기
<br>
  <img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img38.JPG" width="400px" height="500px" alt="jniLibs"></img><br/>


  
