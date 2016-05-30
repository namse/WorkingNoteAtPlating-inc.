### 계정 만들기

### 젠킨스 설정

### 디비 설정
- iamport billing data
- iamport purchased logs


### 서버 구축
- token 관리
- queue 관리
- api 제공
- DB 연결

### php와의 연동
- place_order에서 호출

### 클라와의 연동
- billing data 추가


## 서버
- 아이엠포트 워커
- express router에서는 함수만 호출. 그 함수는 promise 반환함.
- 각 함수에서는 Job을 만들고
  - 큐에 넣어놓고
  - Job의 onDone함수에 promise를 resolve시킴.
- Job을 만들어서
