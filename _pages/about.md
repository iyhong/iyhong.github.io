---
title: "Who am I?"
permalink: /about/
layout: single
toc: true
toc_sticky: true
---

## Inyong Hong

### 2017.12 ~ 현재 삼성SDS Professional
#### 삼성전자 반도체 시스템 운영&개발
 - 기술스택 : c#(wcf, wpf), oracle, unix
 - 주요업무 : 
	. 운영 및 유지보수(sr 및 voc 처리)
	. Partition table space 관리
	. 화면+서버 개발
	. TIBCO Rendezvous Message 통신으로 설비 제어 개발
	. crontab 관리
	. 쉘프로그래밍 개발 및 관리

 - 사내 알고리즘 자격 : Professional(18.01 취득)
 - 사내 DataScientist : level 1(19.06 취득)
 - 사내 교육이수 :
	. 실무에서 바로쓰는 SQL튜닝
	. 사내 플랫폼을 활용한 MSA 구현(Springboot, vuejs, docker, kubernates)


### 2019.12 Springboot & aws 로 구현한 게시판 (toy project)
 - 기술스택 : springboot2.1.7, JPA, gradle, mustache, mariadb, OAuth2.0, aws(ec2, s3, CodeDeploy), Travis CI
 - Travis CI와 CodeDeploy 를 활용해 무중단 배포시스템 구축
 - OAuth2.0 을 활용해 google, naver 로그인 구현
 - [GitHub](https://github.com/loverman85/spring-boot-gradle-test)


### 2019.09 스냅사진 매칭 서비스 (toy project)
 - serverside(springboot, JPA, h2-db)
 - email 인증으로 회원가입까지 구현
 - [Github](https://github.com/loverman85/snap)


### 2019.01 Chrome_extension (toy project)
 - 네이버 검색어 결과를 기반으로 현재날씨, 미세먼지수치를 보여주는 확장프로그램 개발
 - javascript
 - [Github](https://github.com/loverman85/chrome_extension_current_weather.git)


### 2017.03 국비지원교육 Project
 - Leader, 설계 및 개발
 - 주제 : 개인 의료기록 데이터를 중앙 정부에서 관리하며 각각의 병원 시스템에서 API를 통해 데이터를 받아 진료시 참고하는 시스템
 - 기술스택 : SpringFramework4.3.5, mybatis, mysql, jsp, bootstrap, html5
 - 구조 : API sever(정부) <-> 병원시스템 간 http 통신을 구현
	1)병원 -＞ 정부 : Scheduler를 활용하여 일정시점마다 정부로 전송하지 않은 데이터를 병원 단위로 일괄 전송.
	2)정부 -＞ 병원 : Open API 방식으로 부여한 key를 확인하고 일치하면 DATA를 제공.
Github:  
 [병원 시스템](https://github.com/loverman85/bigtower-project.git)  
 [정부 시스템](https://github.com/loverman85/bigbang-project.git)


---

### 보유자격 :
 - 정보처리기사(17.08 취득)
 - ADsP(19.05 취득)

### 관심도서 :
 - 스프링 부트와 AWS로 혼자 구현하는 웹 서비스(이동욱)
 - 객체지향의 사실과 오해(조영호)
 - 리팩토링(마틴파울러)
