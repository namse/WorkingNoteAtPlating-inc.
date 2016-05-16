환경
- Local
- Test
- Production
* 각 환경 별로
  - 서버
  - DB

NODE_ENV
- 로컬 : ```'undefined'``` or ```'development'```
- 테스트 : ```'test'```
- 프로덕션 : ```'production'```

getconfig
  - ```config/default.json```
  - ```config/{{NODE_ENV}}.json```

Environment별 배포 및 설정
  - Jenkins Build Pipeline

DB 배포
  - Jenkins NodeJS
  - knex-schema-builder

레포지토리
  - API 서버
  - DB Schema
  - 클라이언트

문제
- Node 실행 시 NODE_ENV를 어떻게 주입할 것인가?
  - Docker에서 실행할 ```Node실행.sh```를 jenkins에서 주입?
- Node 실행 전 ```config/{{NODE_ENV}}.json```을 어떻게 주입할 것인가?
- 로그는 어떻게 찍을 것인가?
  - 테스트 서버의 로그
  - 프로덕션 서버의 로그
- 서버는 바뀌었지만 클라이언트가 아직 바뀌지 않았을 경우는?
- 젠킨스에서 파일을 주입하는 방법은?
  - 미리 만들어 놓고 사용하는 방법
    - 미리 만들어 놓은 파일들의 버전관리는?


절대 보여선 안되는 정보
- Credentials

보여도 상관없는 정보
- Constance Values
- URLs

NODE_ENV에 따라
- 달라지는 정보
- 안달라지는 정보

보여도 되고
- NODE_ENV에 따라 달라지는 정보
  - ```config/{{NODE_ENV}}.json```
- NODE_ENV와 관계 없이 일정한 정보
  - ```config/default.json```

보여선 안되는데
- NODE_ENV에 따라 달라지는 정보
  - 해당 Environment에 맞게 Credentials Inject
- NODE_ENV와 관계 없이 일정한 정보
  - 항상 동일하게 Credentials Inject
