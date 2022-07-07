# react native 환경 구축
참고 사이트 : https://dev-yakuza.posstree.com/ko/react-native/install-on-windows/

## 1. npm, vue, python 설치된 버전 확인
nodejs와 npm은 vue를 학습하면서 이미 깔려 있었고
python도 오래 전 이미 깔아두어 버전만 확인함 

<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img1.JPG" width="900px" height="1000px" alt="버전 확인"></img><br/>

## 2. java 설치된 버전 확인
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img3.JPG" width="900px" height="1000px" alt="버전 확인2"></img><br/>

## 3. React Native CLI 설치
설치
```
npm install -g react-native-cli
```
버전확인
```
npx react-native --version
```
<br>
<img src="https://github.com/RainingCodes/BlockChainProjectStudy/blob/main/img/img1.JPG" width="900px" height="1000px" alt="설치 & 버전 확인"></img><br/>


# 프로젝트 구축
## 1. 프로젝트 설치
프로젝트 원본 : https://github.com/hyperledger/aries-mobile-agent-react-native

```
git clone https://github.com/hyperledger/aries-mobile-agent-react-native.git
cd aries-mobile-agent-react-native
npm install
```
aries-mobile-agent-react-native\app 아래에 .env 파일 추가
```
MEDIATOR_URL=http://mediator3.test.indiciotech.io:3000?c_i=eyJAdHlwZSI6ICJkaWQ6c292OkJ6Q2JzTlloTXJqSGlxWkRUVUFTSGc7c3BlYy9jb25uZWN0aW9ucy8xLjAvaW52aXRhdGlvbiIsICJAaWQiOiAiYjE5YTM2ZjctZjhiZi00Mjg2LTg4ZjktODM4ZTIyZDI0ZjQxIiwgInJlY2lwaWVudEtleXMiOiBbIkU5VlhKY1pzaGlYcXFMRXd6R3RtUEpCUnBtMjl4dmJMYVpuWktTU0ZOdkE2Il0sICJzZXJ2aWNlRW5kcG9pbnQiOiAiaHR0cDovL21lZGlhdG9yMy50ZXN0LmluZGljaW90ZWNoLmlvOjMwMDAiLCAibGFiZWwiOiAiSW5kaWNpbyBQdWJsaWMgTWVkaWF0b3IifQ==
GENESIS_URL=https://raw.githubusercontent.com/Indicio-tech/indicio-network/main/genesis_files/pool_transactions_testnet_genesis
```


## 2. 안드로이드 스튜디오 실행
File > import > aries-mobile-agent-react-native/app

## 3. 안드로이드 폰 연결
연결 잭을 이용하여 연결, 휴대폰은 안드로이드여야 하며 개발자 모드에서 usb 디버깅이 허용된 상태로 연결


## 4. 프로젝트 실행 
```
cd app
npm run start
```
터미널 하나 더 열기 (안드로이드 버전 실행)
```
cd app
npm run android
```

## 5. 에러 고치기
실행 중 발생한 에러
```
'adb'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
배치 파일이 아닙니다.
```
참고 사이트 : https://curiousengineer.tistory.com/12
시스템 환경변수 PATH에 adb.exe의 위치를 넣어줌

기존 터미널들은 닫고 재실행(VSCode는 껐다 켜야 함)