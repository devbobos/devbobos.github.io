---
title: Google App Excellence 17/03
layout: post
comments: true
tags:
- Android
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>
3월 세미나는 그 당시 트렌드였던 모바일 빅 데이터에 관한 내용을 다루었다. 저번 달엔 기반 지식없이도 실천할 수 있는 전략에 대해서 다루었다면 이번 세미나는 이론적인 내용과 함께 실질적으로 적용할 수 있는 운영 방법을 알려줘서 설령 전문 지식이 없더라도 바로 도입할 수 있게끔 세션이 진행되었다.

##모바일 빅데이터 분석의 개념
###빅데이터 분석의 종류
- 기술통계학
- 추론통계학

###모바일 데이터 분석의 기본 모델
- Acquisition 사용자 획득 : 데이터 접근성이 좋아야 함 (항시 편하게 볼 수 있어야 함을 의미)
- Retention 사용자 유지 : 데이터의 꾸준한 수집을 위해 사용자가 많게 유지되야함
- Engagement 사용자 활동 : 가장 올리기 힘든 부분, 리뷰 답변을 적극적으로 할 경우 활동이 올라감 (쉽게 말해 유저 피드백)

###분석방법
- 코호트 분석
- 퍼넬 분석
- 데드존 분석
- 히트맵 분석

###구현전략
- 정보모델 : 사용자 지정된 4~5개 되는 핵심지표, 종종 바꾸어야할 필요가 있음
- 구현방식 설계 : 초기엔 무료 솔루션을 위주로 시작(Firebase, GA, Flurry, Fabric), 중기부턴 자체 솔루션과 함께 병행
- 공통 중요사항 : 데이터 분석을 시작하는것이 중요하며 도중에 중단해선 안된다

###빅데이터 분석 아키텍쳐 종류
- 람다 아케틱쳐 : 어제까지 데이터는 밤에 돌리고 오늘꺼는 실시간으로 돌려 리소스를 절약하는 방법
- 구글 클라우드 아키텍쳐 (BigQuery) : 데이터 분석만 하고, 유지보수는 Cloud에서 작업, RAW 데이터로 저장 가능

###Firebase Analytics
- 로그 수집 및 분석 플랫폼
- 커스텀 이벤트를 앱에 삽입하여 원하는 데이터를 따로 분석 가능
- 커스텀 이벤트 : onClickEvent 등 사용자가 원하는 부분에 코드를 삽입하여 데이터를 수집하여 분석할 수 있다
- 연령별 결제별 데모 그래픽 정보가 표시된다
- Push Configuration을 사용해서 특정 타게층에게 Push 알림이 오도록 할 수 있다

###리포팅 툴
1. Datastudio
- 구글에서 제공하는 리포팅 툴
- BigQuery와 연동된다
- 저장된 DB를 사용하여 차트등 기획서를 만들 수 있다
2. Redash
- 오픈소스 리포팅 툴
3. Fluentd
- 서버에 있는 정보도 함께 사용하여 차트 작성 가능
- Firebase 데이터와 조인 가능

###데이터 처리가능 솔루션
1. Apache airflow
- 오픈소스 분산 데이터 처리가능 솔루션
2. 하도비
- 고전 데이터 분석 솔루션
3. 카프카
- 고전 데이터 분석 솔루션

##개발자가 마케터에게 알려주는 Firebase Marketing 활용 방법
###마케팅의 중요 순서
- CPI < ROI < LTV
- Google Analytics는 웹기반 고전 솔루션이므로 Firebase Analytics로 갈아탈것
- Firebase Analytics는 기본적으로 16개의 이벤트를 제공, 추가할 수 있음
- 기존 사람이 하던 분석보단 머신러닝을 통해 얻은 분석을 신뢰하자
- Firebase Event UAC 켐페인 최적화 종류 (전략목표) : 앱설치 극대화, 앱내활동 극대화, 매출 극대화

##Firebase 실제로 사용하기
###Firebase의 장점
- Firebase는 Backend를 클라우드 서비스로 제공
- Realtime Database Full Text 검색 기능 제공

###Firebase 기능 맛보기
- Remote Config, Crash Report, CloudMessaging 등 무료 기능을 활용해보자
- Cloud Functions를 이용한 작은 사이드 프로젝트 시작해보기
- Filter Report : Report를 Filter에 따라 정리하여 볼 수 있음
- Target Notifications : Target에 한하여 Push 알림을 날릴 수 있음
- Target Remote Config : Target에 한하여 앱 업데이트 없이 코드 변경이 가능!

###유의할 점
- 커스텀 이벤트를 수집할때 커스텀 Parameter를 날려도 Dashboard에 반영되지 않음!
- Audience Event는 한정적으로 사용 가능
- VALUE 파라미터 사용시 누적값으로 사용가능
- Predefined Event 파라미터를 우선적으로 사용할것
- Custom User Property는 한 앱당 25개로 제한되어 있으며, 일단 생성된 값은 변경이 불가!
- 한번 유저에게 Audience를 적용시킬 경우 변경이 불가함

###추가로 나왔던 질문사항들
Q) 현재 GA를 사용중인데 해당 데이터를 파이어베이스로 마이그레이션 하고 싶은데 어떻게 해야하나<br>
A) Google Analytics의 데이터를 Firebase에 연동시킬수 없다<br>
Q) Raw 데이터 뽑는것 어떻게 되나<br>
A) 빅쿼리를 사용, 5TB까진 무료로 출력 가능<br>
Q) 화면 이동 이벤트 어떻게 잡나 GA는 가능했는데 FA는 되지 않는다<br>
A) GA는 스크린으로 이벤트를 잡을수 있고 FA는 커스텀 이벤트로 잡으면 된다<br>
Q) 서비스 스크립션 지원이 되는지<br>
A) 현재 지원안되고 추후 지원 예정이다<br>

<h2>참고자료</h2>
구글 Meterial 아이콘 [#](https://github.com/google/material-design-icons>)<br>
구글 Meterial 가이드라인 [#](https://material.io/guidelines/)<br>
구글 PlayConsole [#](https://play.google.com/store/apps/details?id=com.google.android.apps.playconsole)<br>
{% include comments.html %}
