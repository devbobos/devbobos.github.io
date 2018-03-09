---
title: 개발자가 마케터에게 알려주는 Firebase Marketing 활용 방법
layout: post
comments: true
tags:
- GoogleAppExcellence
---
{%- include banner_android.html -%}
Google App Excellence 3월 세미나의 두번째 섹션 내용이다. Firebase Marketing 활용에 대한 전반적인 내용을 다루었다.

### 마케팅의 중요 순서
- CPI < ROI < LTV

### 권장사항
- Google Analytics는 웹기반 고전 솔루션이므로 Firebase Analytics로 갈아탈것
- Firebase Analytics는 기본적으로 16개의 이벤트를 제공, 추가할 수 있음
- 기존 사람이 하던 분석보단 머신러닝을 통해 얻은 분석을 신뢰하자
- Firebase Event UAC 켐페인 최적화 종류 (전략목표) : 앱설치 극대화, 앱내활동 극대화, 매출 극대화

## Firebase 실제로 사용하기
### Firebase의 장점
- Firebase는 Backend를 클라우드 서비스로 제공
- Realtime Database Full Text 검색 기능 제공

### Firebase 기능 맛보기
- Remote Config, Crash Report, CloudMessaging 등 무료 기능을 활용해보자
- Cloud Functions를 이용한 작은 사이드 프로젝트 시작해보기
- Filter Report : Report를 Filter에 따라 정리하여 볼 수 있음
- Target Notifications : Target에 한하여 Push 알림을 날릴 수 있음
- Target Remote Config : Target에 한하여 앱 업데이트 없이 코드 변경이 가능!

### 유의할 점
- 커스텀 이벤트를 수집할때 커스텀 Parameter를 날려도 Dashboard에 반영되지 않음!
- Audience Event는 한정적으로 사용 가능
- VALUE 파라미터 사용시 누적값으로 사용가능
- Predefined Event 파라미터를 우선적으로 사용할것
- Custom User Property는 한 앱당 25개로 제한되어 있으며, 일단 생성된 값은 변경이 불가!
- 한번 유저에게 Audience를 적용시킬 경우 변경이 불가함

### 추가로 나왔던 질문사항들
Q) 현재 GA를 사용중인데 해당 데이터를 파이어베이스로 마이그레이션 하고 싶은데 어떻게 해야하나<br>
A) Google Analytics의 데이터를 Firebase에 연동시킬수 없다<br>
Q) Raw 데이터 뽑는것 어떻게 되나<br>
A) 빅쿼리를 사용, 5TB까진 무료로 출력 가능<br>
Q) 화면 이동 이벤트 어떻게 잡나 GA는 가능했는데 FA는 되지 않는다<br>
A) GA는 스크린으로 이벤트를 잡을수 있고 FA는 커스텀 이벤트로 잡으면 된다<br>
Q) 서비스 스크립션 지원이 되는지<br>
A) 현재 지원안되고 추후 지원 예정이다<br>

## 참고자료
Firebase Analytics [#](https://firebase.google.com/docs/analytics/?hl=ko)<br>
Google Analytics [#](https://www.google.com/analytics/)<br>
