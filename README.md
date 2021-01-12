## 설정파일(깃허브 생략)
```
.env.dev
.env.test
```

## Nuber Eats
- The Backend of Nuber Eats Clone

## First. NestJS 설치
```
nest g application
```
## Second. 패키지명 입력
 - nuber_eats-backend

## Third. 패키지 생성 후 실행
 ```
 npm i
 ```

## Git 연결
 - git init
 - git remote add origin https://github.com/simhyun/nubere-eats-backend.git
 - 소스만 업로드 하고 싶으면 Extensions(왼쪽 아래 환경설정 아이콘) > gitignore 설치
 - .gitignore 파일 설정
 - git add .
 - git commit -m "first"
 - git push origin master


## 1.0 Apollo Server Setup
```
 npm i @nestjs/graphql graphql-tools graphql apollo-server-express
 ```
 - [참고] https://docs.nestjs.com/graphql/quick-start
 - [설명] Apollo server 위에서 작동

## 1.1 Our First Resolver (09:56)
 - 모듈 생성
 ```
 nest g mo restaurants
 ```

## 1.5 Validating ArgsTypes
- 유효성 검증 설치
```
npm i class-validator
npm i class-transformer
```


## 2.0 TypeORM and PostgreSQL
- 데이타베이스 설치
- postgres 설치
    - https://www.postgresql.org/download/
    - https://www.enterprisedb.com/downloads/postgres-postgresql-downloads

- pgAdmin 설치(현재 1번 설치시 같이 설치됨)
    - https://www.pgadmin.org/download/pgadmin-4-windows/


## 2.3 TypeORM Setup (06:57)
```
npm install --save @nestjs/typeorm typeorm pg
```
- [참고] mysql 설치시 : npm install --save @nestjs/typeorm typeorm msyql
- [참고] https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
- [참고] https://github.com/typeorm/typeorm#readme

## 2.4 Introducing ConfigService (06:13)
```
npm i --save @nestjs/config
```
- [참고] https://docs.nestjs.com/techniques/configuration

```
npm i cross-env
```
- 설치시, 다양한 환경(Windows, Mac)에서 동일 설정 가능


## 2.6 Validating ConfigService (05:44)
```
npm i joi
```
- 유효성 검사
- [참고] https://joi.dev

## 3.0 Our First Entity (07:44)
- [정의] Entity : TypeORM이 DB에 해당 항목을 저장
- [정의] Object Type : 자동으로 스키마를 빌드하기 위해 사용되는 GraphQL decorator

## 3.1 Data Mapper vs Active Record (07:04)
- 우리는 Data Mapper 사용 
- 이유
    - 대규모 앱을 만들 때 Data Mapper 도움이 됨
    - NestJS의 경우 자동으로 Repository를 사용할 수 있도록 클래스에서 알아서 준비, Data Mapper 패턴을 이용해서 Repository를 테스트하고 simulate 할 수 있음

## 3.5 Mapped Types (12:23)
- entity와 dto를 통합

## 4.1 User Model (07:07)
```
nest g mo users
nest g mo common
```

-------------------------------------------------------
# User structure

## User Model:

- id
- createdAt
- updatedAt

- email
- password
- role(client|owner|delivery)

## User CRUD:

- Create Account
- Log In
- See Profile
- Edit Profile
- Verify Email

## 4.7 Hashing Passwords (09:02)
```
npm i bcrypt
npm i @types/bcrypt --dev-only
```
- 패스워드를 해쉬화
- [참고] https://typeorm.io/#/listeners-and-subscribers

## 5.0 Introduction to Authentication (02:00)

> 토큰 만드는 방법 두가지
- 첫번째, 수작업
- 두번째, http://npmjs.com/package/jsonwebtoken
```
npm install jsonwebtoken
npm i @types/jsonwebtoken --only-dev
```
- https://randomkeygen.com/
- nestjs/passports를 적용시킨 후 passport-jwt과 nestjs/jws를 활용하는 방법

## 5.2 JWT and Modules (06:05)
- 토큰의 내용이 무엇인지 확인하는 사이트
- https://jwt.io/
```
nest g mo jwt
nest g s jwt
```

## 5.9 AuthGuard (08:22)
- [참고] http://docs.netjs.com/guards
```
nest g mo auth
```

##5.11 Recap (07:35)

- [authentication 작동 원리]
    - header의 token 보내기(http) > middleware(헤더를 통해 jwtService.verify() 사용, 인증) > id를 통해 user를 서치 > userService는 typeOrm의 findOne를 이용해 user 검색 > user를 request object를 통해 전송

- [middleware 작동 원리]
    - apollo server의 context를 통해 user를 서치 > authorization guard > resolver > decorator(conext를 graphql conext로 바꿈)


## 6.0 Verification Entity (06:54)
```
npm i uuid
```

## 6.5 Mailgun Setup (07:12)
- https://www.mailgun.com/
- 3개월에 5000건씩 무료
- 계정명 : youksimhyun@naver.com
- [참고] fake sms : receive=smss.com

## 6.6 Mail Module Setup (08:34)
- nestjs mailer 대체 가능
- (추후 사용자 많아질 시 변경 여부 확인)
```
nest g mo mail
```


## 6.7 Mailgun API (13:25)
```
npm i got
```
- [설명] request
```
npm i form-data
```
- [설명] form 만들기

## 7.0 Setting Up Tests (08:26)
- 테스트 목적으로 소스 변경 시 자동 적용
```
npm run test:watch
```

## 8.0 JWT Service Test Setup (05:20)
```
npm run test:e2e
```

-------------------------------------------------------
Restaurant Model

- name
- category
- address
- coverImage

- Edit Restaurant
- Delete Restaurant
- See Categories
- See Restaurants by Category (pagination)
- See Restaurants (pagination)
- See Restaurant
- Create Dish
- Edit Dish
- Delete Dish

## 10.11 Delete Restaurant (07:10)
