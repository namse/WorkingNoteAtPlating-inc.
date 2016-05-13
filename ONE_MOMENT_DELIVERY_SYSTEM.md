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
  - config/default.json
  - config/{{NODE_ENV}}.json

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
- Node 실행 전 config/{{NODE_ENV}}.json을 어떻게 주입할 것인가?
- 로그는 어떻게 찍을 것인가?
  - 테스트 서버의 로그
  - 프로덕션 서버의 로그
- 서버는 바뀌었지만 클라이언트가 아직 바뀌지 않았을 경우는?
