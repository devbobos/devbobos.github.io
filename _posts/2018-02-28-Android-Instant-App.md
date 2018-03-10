---
title: Android Instant App
layout: post
comments: true
tags:
- GoogleAppExcellence
---
6월 GoogleAppExcellence 세미나가 진행되었던 시기에 2017년 Google I/O Recap이 진행됐고 Google의 새로운 API 및 Android O에 대한 내용이 다수 다뤄졌는데, 이번 세미나에서는 Recap에서 진행된 내용 중 유익한 내용을 추려내어 진행하는 방향으로 결정되었다. 업데이트에 따라 개발 툴인 Android Studio 사용 방법의 달라진 부분도 다수 있으니 확인해보고 적용해보면 좋을 듯하다. 첫번째 섹션은 Android Instant App에 관한 내용이다.

- 근래 앱 설치 자체를 기피하는 사용자가 증가하고 있으며 그에 따른 대안으로 Instant App을 만들었다
- Instant App은 URL로 실행되는 Native App으로 기존 앱과 거의 동일한 경험을 줄 수 있다
- Runtime Permission은 필수이다
- Device ID를 읽을 수 없다
- Broadcast Receiver 사용 할 수 없다
- Android Studio 3.0, Android 6.0 이상 필요
- 앱 크기가 4MB 미만으로 제한되며 적은 용량을 위해 기능 별로 쪼개서 유저에게 제공함을 권장한다
- Feature Module : 기능 별로 쪼개어 빌드하는 기능, Modulization은 필수, 모듈마다 링크 할당이 필요하다
- 성인 인증이 들어가는 모듈은 검증 모듈 용량이 너무 커서 Instant App을 사용할 수 없다
- 주의사항
  - 모듈 별 4MB 용량 제한
  - Android 기본 API는 제공된다
  - 외부 Library의 경우 Google 측에서 검증한 Library에 한하여 동작 가능하다
  - 백그라운드 서비스, 특정 퍼미션에 사용 제한이 걸려있다
  - 로그인 하려면 필수적으로 Smart Lock을 지원해야 한다
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-02-28/2.jpg' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>Android Instant App</h3>
</header>
</div>
</div>
</div>

## 참고자료
Android 빠른 실행 앱 [#](https://developer.android.com/topic/instant-apps/index.html?hl=ko)<br>
