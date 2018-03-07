---
title: 새로운 Google Play 콘솔 UI
layout: post
comments: true
tags:
- GoogleAppExcellence
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>
Google App Excellence 5월 세미나는 원래 예정에 없었다는데, Google 내 정책이 변경됨에 따라 공지도 할겸 진행되었다고 한다. 그래서 인지 새로운 API 사용법 및 추가로 지켜야할 정책 준수 사항에 대한 내용이 주를 이루었다. 특히 정책 위반의 경우 앱이 스토어에서 제재를 받고 내려가는 경우도 왕왕 있으니 신경써서 봐야할 듯 싶다. 첫번재 섹션은 Google Play Console의 업데이트 내용 및 활용법이 발표되었다.

### GooglePlay 개발자 지원팀에 문의하는 방법
- 도움말 페이지가 업데이트 되었다고 한다
- 전화, 메일 등의 방법으로 문의할 수 있다

### Google Console 업데이트 사항
- 빠른 실행 앱 (Instant APP) 항목 추가
- Google 플레이 앱 서명이 업로드 키를 부여받을 경우 재발급이 가능하다 -> 기존 앱도 마이그레이션이 가능하다, 앱 등록 / 고급에서 업로드 키로 업데이트
- Android Vital 항목 추가
  - 앱의 건강지표, 안정성 렌더링 베터리 지표를 표시한다
  - Crash Report 설정에 Report 일괄 설정이 추가
  - Bad Behavior 항목 분석 가능, 지표 중 하위 25%를 따로 표시 해준다
  - 안정성 항목 추가 : ANR 발생률, 비정상 종료을 표시해준다
  - 렌더링 항목 추가 : 느린 렌더링, 정지된 프레임을 표시해준다
  - 베터리 : 장시간 Wake Lock, 불필요한 Wake Up 등의 지표를 표시해준다
- 기기 카탈로그 : 앱 표시 필터링 역활, RAM 별, OS 별 등 분류하여 표시가 가능하다
- 출시 대시보드 : 최신 Production 버전의 출시 개요를 표시해준다

## 추가로 나왔던 질문사항들
Q) 앱서명 기존 방식대로 쓰고 싶을땐 어떻게 하는건지<br>
A) 등록 안하면 그대로 쓸수있음, 하지만 업로드키를 한번 등록하면 되돌릴수 없다<br>
Q) 사전출시할때 버젼을 계속 올려야 하는게 불편하다<br>
A) 방법이 없다, 계속 버전을 올리는 수밖에 없다<br>

## 참고자료
Google Play Console [#](https://developer.android.com/distribute/console/index.html?hl=ko)<br>
