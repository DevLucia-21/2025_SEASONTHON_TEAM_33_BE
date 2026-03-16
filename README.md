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

**essaily**는 **Essay + Easily**의 합성어로,   
자기소개서를 보다 **쉽게 작성·관리할 수 있도록 돕는 서비스**라는 의미를 담고 있습니다.

채용 공고 데이터를 기반으로   
맞춤형 자기소개서를 작성하고 관리할 수 있도록 지원하는 웹 서비스입니다.

사용자는 채용 공고를 탐색한 뒤 서비스에서 제공하는 자기소개서 문항을 확인하고 답변을 작성할 수 있으며    
작성한 자기소개서를 저장하고 아카이브 형태로 관리할 수 있습니다.

이 프로젝트는 **kakao × goorm이 주최한 9oormthonUNIV 4기 SEASONTHON 해커톤**에서   
**"청년 세대의 경제적, 사회적 어려움을 해결하기 위한 솔루션"** 이라는 주제를 바탕으로 팀 단위로 기획 및 개발된 서비스입니다.

---

## Problem

청년 세대는 취업 준비 과정에서   
높은 경쟁률과 반복적인 지원 과정으로 인해 큰 부담을 느끼고 있습니다.

특히 지원 기업과 공고에 따라 준비해야 할 자기소개서 내용이 달라지기 때문에   
지원할 때마다 새로운 자기소개서를 작성해야 하는 문제가 발생합니다.

또한 이전에 작성한 자기소개서를 체계적으로 관리하거나   
비슷한 경험과 답변을 다시 활용하기도 쉽지 않습니다.

채용 공고는 지속적으로 업데이트되기 때문에   
청년 구직자는 **공고마다 새로운 자기소개서를 반복적으로 작성해야 하는 비효율적인 과정**을 겪게 됩니다.

---

## Solution

**essaily**는 채용 공고 데이터를 기반으로  
자기소개서를 효율적으로 작성할 수 있도록 지원하는 서비스입니다.

사용자는 채용 공고를 탐색한 뒤
서비스에서 제공하는 자기소개서 문항을 확인하고 답변을 작성할 수 있습니다.

또한 이전에 작성한 자기소개서를 **아카이브 형태로 관리하고**  
비슷한 경험이나 답변을 **재활용하여 새로운 자기소개서 작성에 활용할 수 있습니다.**

이를 통해 반복적인 자기소개서 작성 과정의 부담을 줄이고  
보다 효율적으로 취업 준비를 할 수 있도록 돕습니다.

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

### 1. 자기소개서 작성

사용자는 채용 공고를 확인한 뒤 서비스에서 제공하는 자기소개서 문항에 대해 답변을 작성할 수 있습니다.    
채용 공고 내용을 참고하여 자기소개서를 작성할 수 있도록 지원합니다.

### 2. 기존 답변 추천

사용자가 작성하려는 자기소개서 문항과 유사한 문항을 분석하여   
기존에 작성했던 자기소개서 답변을 추천합니다.

이를 통해 사용자는 이전 답변을 참고하거나 재활용하여   
보다 효율적으로 새로운 자기소개서를 작성할 수 있습니다.

### 3. 자기소개서 피드백

작성한 자기소개서 답변에 대해
잘한 점, 부족한 점, 개선 방향을 분석하여 피드백을 제공합니다.

사용자는 피드백을 기반으로 자신의 답변을 개선할 수 있습니다.

### 4. 자기소개서 아카이브

사용자가 작성한 자기소개서를 저장하고 관리할 수 있는 아카이브 기능을 제공합니다.   
기존에 작성한 자기소개서를 다시 확인하거나 재활용할 수 있도록 지원합니다.

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
   ├ Archive
   │    작성된 자기소개서 조회 및 관리
   │
   ├ External API
   │    Worknet Open API
   │
   ▼
MySQL Database
```

---

## Domain Structure

프로젝트는 다음 도메인 구조를 중심으로 설계되었습니다.

```
User
Recruitment
Question
Essay
UserRecruitment
RecruitmentFetchLog
```

---

### User

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

### Recruitment

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

### Question

채용 공고별 자기소개서 문항을 관리합니다.

* content
* minLength
* maxLength
* required

---

### Essay

사용자가 작성한 자기소개서 답변을 저장합니다.

* content
* good
* bad
* suggestion

---

### UserRecruitment

사용자와 채용 공고의 관계를 관리합니다.

User ↔ Recruitment 관계를 직접 연결하지 않고
`UserRecruitment` 엔티티를 통해 관리합니다.

이를 통해

* 사용자별 지원 공고 관리
* 공고별 자기소개서 작성 관리

를 수행합니다.

---

### RecruitmentFetchLog

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
           └ Question
                └ Essay
```

채용 공고 수집 작업은
`RecruitmentFetchLog` 엔티티를 통해 관리됩니다.

---

## API Endpoints

### Recruitment API

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

## Technical Challenges

### 채용 공고 데이터 수집 방식 결정 (API vs Crawling)

초기에는 다양한 채용 플랫폼의 데이터를 수집하기 위해   
잡코리아, 사람인, 원티드 등의 채용 사이트를 대상으로 **크롤링 기반 데이터 수집 방식**을 고려했습니다.

그러나 일부 채용 사이트는 동적 렌더링 구조로 되어 있어   
Selenium 등 브라우저 기반 크롤러가 필요했고, 사이트별 크롤링 차단 정책 또한 존재했습니다.

또한 해커톤이라는 제한된 개발 시간 내에서   
안정적인 크롤러를 구축하고 유지하는 것이 현실적으로 어렵다고 판단했습니다.

따라서 최종적으로는
**공식적으로 제공되는 채용 공고 API를 우선 활용하는 방식으로 방향을 변경**했습니다.

현재 서비스에서는 **Worknet Open API**를 기반으로
채용 공고 데이터를 수집하도록 구현했습니다.

이를 통해

* 안정적인 데이터 구조 확보
* 크롤링 차단 위험 최소화
* 주기적인 데이터 업데이트 가능

과 같은 장점을 확보할 수 있었습니다.

---

### 채용 공고 데이터 중복 처리 및 갱신 전략

채용 공고 API는 페이지네이션 구조로 데이터를 제공하기 때문에   
대량의 공고 데이터를 안정적으로 수집하기 위한 구조가 필요했습니다.

이를 위해

* API 페이지네이션을 고려한 **페이지 단위 데이터 수집 로직 구현**
* 외부 공고 식별자인 `externalId`를 기준으로 **upsert 방식 데이터 저장**
* 신규 공고 / 업데이트 공고를 구분할 수 있는 **수집 로그 관리 구조 설계**

를 통해 채용 공고 데이터의 **중복 저장 문제를 방지하고 데이터 최신성을 유지**하도록 설계했습니다.

또한 수집 작업의 상태를 관리하기 위해   
`RecruitmentFetchLog` 엔티티를 통해 공고 수집 결과를 기록하도록 구현했습니다.

---

### 사용자–채용 공고 관계 설계

사용자가 여러 채용 공고에 대해 자기소개서를 작성할 수 있기 때문에   
단순한 `User ↔ Recruitment` 관계만으로는 데이터를 관리하기 어려웠습니다.

이를 해결하기 위해
사용자와 채용 공고 사이에 **UserRecruitment 중간 엔티티**를 두어 관계를 관리하도록 설계했습니다.

이 구조를 통해

* 사용자별 지원 공고 관리
* 공고별 자기소개서 작성 관리
* 동일 공고에 대한 사용자별 데이터 분리

와 같은 기능을 안정적으로 처리할 수 있도록 구현했습니다.

---

## My Contribution

본 프로젝트에서 **Backend Developer**로 참여하여    
채용 공고 관리, 자기소개서 작성 시스템, 아카이브 기능과 관련된 핵심 백엔드 API를 설계하고 구현했습니다.

### Recruitment Module

채용 공고 데이터를 기반으로 사용자가 공고를 탐색하고   
서비스에서 제공하는 자기소개서 문항을 확인하여 답변을 작성할 수 있는 기능을 구현했습니다.

* Worknet Open API 기반 **채용 공고 수집 및 저장 기능 구현**
* 채용 공고 **목록 조회 및 상세 조회 API 구현**
* 자기소개서 작성에 활용되는 **문항 조회 API 설계 및 구현**
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
[9oormthon-univ/2025_SEASONTHON_TEAM_33_BE](https://github.com/9oormthon-univ/2025_SEASONTHON_TEAM_33_BE)

---

## Author

Yeeun Park

GitHub: [DevLucia-21](https://github.com/DevLucia-21)
