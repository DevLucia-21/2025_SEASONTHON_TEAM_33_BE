# essaily - AI Cover Letter Assistant

![Java](https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/SpringBoot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/SpringSecurity-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/JPA-6DB33F?style=flat-square&logo=spring&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![OAuth2](https://img.shields.io/badge/OAuth2-4285F4?style=flat-square&logo=google&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

> 채용 공고 데이터를 기반으로 자기소개서 작성을 지원하는 웹 서비스

<br>

**essaily**는 채용 공고 데이터를 기반으로   
맞춤형 자기소개서를 작성하고 관리할 수 있도록 지원하는 웹 서비스입니다.

사용자는 채용 공고를 탐색하고 기업별 자기소개서 문항을 확인한 뒤 답변을 작성할 수 있으며   
작성한 자기소개서를 저장하고 아카이브 형태로 관리할 수 있습니다.

이 프로젝트는 **kakao × goorm이 주최한    
9oormthonUNIV 4기 해커톤 SEASONTHON**에서 팀 단위로 기획 및 개발된 서비스입니다.

---

## Problem

취업 준비 과정에서 많은 구직자들이   
채용 공고마다 새로운 자기소개서를 작성해야 하는 부담을 느낍니다.

또한 기업이 요구하는 역량을 파악하기 어렵고   
기존에 작성한 자기소개서를 다시 활용하기도 쉽지 않습니다.

채용 공고는 지속적으로 업데이트되기 때문에   
구직자는 **공고별 맞춤 자기소개서를 반복적으로 작성해야 하는 문제**를 겪습니다.

---

## Solution

**essaily**는 채용 공고 데이터를 기반으로   
공고별 맞춤 자기소개서를 효율적으로 작성할 수 있도록 지원하는 서비스입니다.

사용자는 채용 공고를 탐색하고   
공고별 자기소개서 문항을 확인한 뒤 답변을 작성할 수 있으며   
작성한 자기소개서를 **아카이브 형태로 관리하고 재활용**할 수 있습니다.

---

## User Flow

```
Login
 ↓
User Profile 입력
 ↓
채용 공고 탐색
 ↓
공고 선택
 ↓
자기소개서 문항 확인
 ↓
자기소개서 작성
 ↓
AI 도움 / 기존 답변 참고
 ↓
자기소개서 저장
 ↓
Archive에서 이전 답변 조회
```

사용자는 이전에 작성한 자기소개서를 **아카이브에서 검색하고 재활용**할 수 있습니다.

---

## Core Features

### Recruitment

채용 공고 정보를 조회하고 공고별 자기소개서 문항을 제공합니다.

* 채용 공고 목록 조회
* 채용 공고 상세 조회
* 자기소개서 문항 조회
* 채용 공고 수집 실행
* 채용 공고 수집 상태 조회

채용 공고 데이터는 **Worknet Open API 기반으로 수집**됩니다.

---

### Resume

사용자가 작성한 자기소개서를 관리합니다.

* 자기소개서 목록 조회
* 자기소개서 조회
* 자기소개서 수정

---

### Archive

작성 완료된 자기소개서를 아카이브 형태로 조회합니다.

* 아카이브 목록 조회
* 자기소개서 상세 조회
* 자기소개서 피드백 조회

---

## Tech Stack

### Backend

* Java 17
* Spring Boot
* Spring Security
* Spring Data JPA
* JWT Authentication
* OAuth2 Login

### Database

* MySQL

### External API

* Worknet Open API (채용 공고 데이터)

---

## System Architecture

```
Client
   │
   ▼
Spring Boot Backend
   │
   ├ Auth
   │    OAuth2 로그인 및 사용자 정보 관리
   │
   ├ Recruitment
   │    채용 공고 조회 및 관리
   │
   ├ Resume
   │    자기소개서 작성 및 관리
   │
   └ Archive
        작성된 자기소개서 조회 및 관리
   │
   ▼
MySQL Database
```

---

## Domain Structure

프로젝트는 다음 도메인 구조를 중심으로 설계되었습니다.

```
Users
Recruitments
Questions
Essays
UserRecruitments
RecruitmentFetchLogs
```

---

### Users

OAuth 기반 로그인 사용자의 정보를 관리합니다.

주요 정보

* oauthProvider
* oauthId
* email
* role
* contact
* education
* major
* interests
* resume 파일 정보
* portfolio 파일 정보
* refreshToken

---

### Recruitments

채용 공고 정보를 저장합니다.

주요 정보

* externalId
* companyName
* title
* location
* category
* experienceLevel
* employmentType
* description
* requirements
* deadline
* url

채용 공고 데이터는 **Worknet Open API 기반으로 수집됩니다.**

---

### Questions

채용 공고별 자기소개서 문항을 관리합니다.

* content
* minLength
* maxLength
* required

---

### Essays

사용자가 작성한 자기소개서 답변을 저장합니다.

* content
* good
* bad
* suggestion

---

### UserRecruitments

사용자와 채용 공고의 관계를 관리합니다.

User ↔ Recruitment 관계를 직접 연결하지 않고
`UserRecruitment` 엔티티를 통해 관리합니다.

이를 통해

* 사용자별 지원 공고 관리
* 공고별 자기소개서 작성 관리

를 수행합니다.

---

### RecruitmentFetchLogs

채용 공고 수집 작업 로그를 저장합니다.

* status
* executedAt
* newCount
* updatedCount
* failedCount
* message

---

## Database Schema

```
User
 └ UserRecruitment
      └ Recruitment
           └ Questions
                └ Essays
```

채용 공고 수집 작업은
`RecruitmentFetchLogs` 엔티티를 통해 관리됩니다.

---

## API Endpoints

## Recruitment API

```
GET  /api/v1/recruitments
GET  /api/v1/recruitments/{recruitmentId}
GET  /api/v1/recruitments/{recruitmentId}/write
POST /api/v1/recruitments/{recruitmentId}/write
POST /api/v1/recruitments/fetch
GET  /api/v1/recruitments/status
```

---

### Resume API

```
GET  /api/v1/user-recruitments
GET  /api/v1/user-recruitments/{userRecruitmentId}
PUT  /api/v1/user-recruitments/{userRecruitmentId}
```

---

### Archive API

```
GET /api/v1/archives
GET /api/v1/archives/{essayId}
GET /api/v1/archives/{essayId}/feedbacks
```

---

## My Contribution

본 프로젝트에서 **Backend Developer**로 참여하여    
채용 공고 관리, 자기소개서 작성 시스템, 아카이브 기능과 관련된 핵심 백엔드 API를 설계하고 구현했습니다.

### Recruitment Module

채용 공고 데이터를 기반으로 사용자가 기업 공고를 탐색하고 자기소개서 문항을 확인할 수 있도록 하는 기능을 구현했습니다.

* Worknet Open API 기반 **채용 공고 수집 및 저장 기능 구현**
* 채용 공고 **목록 조회 및 상세 조회 API 구현**
* 채용 공고별 **자기소개서 문항 조회 API 설계 및 구현**
* 채용 공고 수집 작업을 수행하는 **수집 실행 API 구현**
* 채용 공고 수집 결과를 확인할 수 있는 **수집 상태 조회 API 구현**

### Resume Module

사용자가 작성한 자기소개서를 관리할 수 있도록 자기소개서 조회 및 수정 기능을 구현했습니다.

* 사용자 기준 **자기소개서 목록 조회 API 구현**
* 특정 공고에 대한 **자기소개서 상세 조회 API 구현**
* 기존에 작성한 자기소개서를 수정할 수 있는 **수정 API 구현**

### Archive Module

작성 완료된 자기소개서를 아카이브 형태로 조회하고 AI 피드백을 확인할 수 있는 기능을 구현했습니다.

* 작성 완료된 자기소개서를 관리하는 **아카이브 목록 조회 API 구현**
* 저장된 자기소개서를 확인하는 **아카이브 상세 조회 API 구현**
* 자기소개서에 대한 **AI 피드백 조회 API 구현**

---

## Repository

이 저장소는
**2025 SEASONTHON TEAM 33 프로젝트의 개인 fork 저장소**입니다.

Original Repository
https://github.com/9oormthon-univ/2025_SEASONTHON_TEAM_33_BE

Frontend Repository
https://github.com/right-path-ptj/groom-hackathon-essily

---

## Author

Yeeun Park

GitHub: [DevLucia-21](https://github.com/DevLucia-21)
