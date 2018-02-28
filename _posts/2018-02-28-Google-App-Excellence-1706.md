---
title: Google App Excellence 17/06
layout: post
comments: true
tags:
- Android
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>
그 시기에 2017년 Google I/O Recap이 진행됐고 Google의 새로운 API 및 Android O에 대한 내용이 다수 다뤄졌는데, 이번 세미나에서는 Recap에서 진행된 내용 중 유익한 내용을 추려내어 진행하는 방향으로 결정되었다. 업데이트에 따라 개발 툴인 Android Studio 사용 방법의 달라진 부분도 다수 있으니 확인해보고 적용해보면 좋을 듯하다.

## Android Instant App
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

## What's new in Android

### PIP
- Picture in Picture 기능
- Android O에 한정하여 사용 가능하다
- 사용방법 : xml에 프로퍼티에 추가, Activity에 옵션하나 추가

### 호환성 라이브러리 v26 기능 정리
- xml로 **폰트** 사용 가능
- 다운 가능한 폰트 지정
- **자동크기변환** Textview
- EmojiCompat 기능 제공
- 물리 애니메이션 추가 com.android.support:support-dynamic-animation:26.0.0-beta2 를 사용할것
- 아키텍쳐 컴포넌트 추가
  - LiveData : 각 Activity 생명주기와 관련된 코드를 모아둘수 있음
  - ViewModel : 앱이 죽을때까지 살아있는 UI와 관련된 데이터를 담고있게 된다
  - Loom Annotation Query 지원 : Dao를 만들때 사용한다

### 그외 추가 기능
- 멀티 디스플레이 지원
- 버퍼링 제어 향상
- 탐색모드 추가
- 볼륨 컨트롤 세분화 추가
- findViewById ->  <T extends object> findViewById 변경 ~~야호!~~
- 반응형 아이콘 추가 -> 클릭할때 배경이랑 별개로 움직일수 있다!
- 숏컷 핀 꽃기 추가 (아이콘 형태도 가능하다고 한다)
- 채널 추가 (앱의 노티피케이션을 종류 별로 묶고 관리하는 기능) 채널 별로 설정가능
- 미디어 파일 접근 용이해짐 -> 탐색가능한 파일 디스크립터 제공
- 구글 플레이 프로텍트 업데이트 -> 하드웨어 분실 방지, 앱 보안
- **코틀린 언어 공식화**
- 자바 버젼 업데이트

## What's new in firebase

### Crash Reporting Tool 업데이트
- Fabric 지원
- Crashlytics 지원
- DIGITS 지원

### Performance Monitoring 기능 업데이트
- 2017년 기준 Beta로 제공되는 기능이다
- 상세 설명
  - Traces 포인트를 지정하여 시간 별로 데이터를 수집한다
  - Network Requests 네트워크 트래킹 기능 지원
  - Tracking 항목
    - App version
    - Device
    - Country
    - OS Level
    - Carrier
    - Radio
  - Test Lab : 다양한 화면 및 기종 테스트를 클라우드로 지원한다!
  - Google Analytics for Firebase

## 참고자료
Android O 변경사항 [#](https://developer.android.com/about/versions/oreo/index.html?hl=ko)<br>
Android 빠른 실행 앱 [#](https://developer.android.com/topic/instant-apps/index.html?hl=ko)<br>
Fabric [#](https://fabric.io)<br>
Crashlytics [#](https://try.crashlytics.com)<br>
Digits for xamarin [#](https://xamarindev.blog/2017/02/09/digits-for-xamarin/)<br>
{% include comments.html %}
