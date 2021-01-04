# Nuber Eats

The Backend of Nuber Eats Clone

```
---------------------------------------------
BACKEND 설치
---------------------------------------------

1. NestJS 설치
 : nest g application

2. 패키지명 입력
 : nuber_eats-backend

3. 패키지 내 모두 인스톨
 : npm i

4. Git 연결
 - git init
 - git remote add origin https://github.com/simhyun/nubere-eats-backend.git
 - 소스만 업로드 하고 싶으면 Extensions(왼쪽 아래 환경설정 아이콘) > gitignore 설치
 - .gitignore 파일 설정
 - git add .
 - git commit -m "first"
 - git push origin master

#1.0 Apollo Server Setup
 npm i @nestjs/graphql graphql-tools graphql apollo-server-express
 [참고] https://docs.nestjs.com/graphql/quick-start
 [설명] Apollo server 위에서 작동

#1.1 Our First Resolver (09:56)
 - 모듈 생성
 : nest g mo restaurants

#1.5 Validating ArgsTypes
 - 유효성 검증 설치
npm i class-validator
npm i class-transformer


#2.0 TypeORM and PostgreSQL
- 데이타베이스 설치
1. postgres 설치
https://www.postgresql.org/download/
https://www.enterprisedb.com/downloads/postgres-postgresql-downloads

2. pgAdmin 설치(현재 1번 설치시 같이 설치됨)
https://www.pgadmin.org/download/pgadmin-4-windows/


#2.3 TypeORM Setup (06:57)
npm install --save @nestjs/typeorm typeorm pg
[참고] (mysql) npm install --save @nestjs/typeorm typeorm msyql
[참고] https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
[참고] https://github.com/typeorm/typeorm#readme

#2.4 Introducing ConfigService (06:13)
npm i --save @nestjs/config
[참고] https://docs.nestjs.com/techniques/configuration

다양한 환경(Windows, Mac)에서 동일 설정 가능
npm i cross-env


#2.6 Validating ConfigService (05:44)
유효성 검사
npm i joi
[참고] https://joi.dev

#3.0 Our First Entity (07:44)
[정의] Entity : TypeORM이 DB에 해당 항목을 저장
[정의] Object Type : 자동으로 스키마를 빌드하기 위해 사용되는 GraphQL decorator

#3.1 Data Mapper vs Active Record (07:04)
우리는 Data Mapper 사용 
[이유]
- 대규모 앱을 만들 때 Data Mapper 도움이 됨
- NestJS의 경우 자동으로 Repository를 사용할 수 있도록 클래스에서 알아서 준비, Data Mapper 패턴을 이용해서 Repository를 테스트하고 simulate 할 수 있음

#3.5 Mapped Types (12:23)
entity와 dto를 통합


#3.6 Optional Types and Columns (08:42
할차례
```