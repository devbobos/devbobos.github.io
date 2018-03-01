---
title: Google App Excellence 17/09
layout: post
comments: true
tags:
- Android
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>

2017년 8월 22일에 Android O가 공개되었고, 그에 따라 9월 세미나는 Android O의 업데이트된 기능과 버전 업에 따른 조치 사항에 대한 내용이 주를 이뤘다. 그리고 특히나 가장 충격적이었던 점은 이번 세미나에서 Google이 **Android OS는 쓰면 쓸수록 느려진다** 라는 점을 공식적으로 언급한것이다. 더불어 해당 문제점을 해결하기 위해 Background Process에 제한사항을 엄청 추가했다고 하는데, TargetSDK가 Android O가 아님에도 사용자에 의해서 제한을 걸 수 있다고 하니 필히 눈여겨 봐야할 부분이다.

<img src="{{ 'assets/images/stickers/surprise.gif' | relative_url }}" alt="sticker" class="image centered"><br>
폰이 잠금상태에서도 작동해야할 알람앱 같은 경우는 .. 자세한 설명은 생략

## Android O에 추가된 기능

### Notification dot
- 알림이 있을 경우 dot 벳지가 표시
- Long press 하면 상세 내용 표시
- 채널에 따라 표시 정보 변경 가능하다
- 우선순위 적용 가능

### Autofill Framework
- 자동완성 지원
- target SDK 올리지 않아도 적용 가능

### Text
- XML로 정리
- Font를 XML에 바로 적용가능 (프로퍼티로 제공)
- 다운로드 Font 사용가능
- Autosize Text 제공

### System
- 캐시 커스텀 가능
    - 이전 OS에서는 캐시 불필요 판단되면 해당 앱의 모든 캐시 삭제했음
    - Android O에서는 프레임워크 API를 사용하여 앱의 캐시 용량을 설정 가능하도록 변경

### Sytem Health (Android Vital)
- Google Console 기능
- App이 제대로 정상적으로 동작하는지 확인 가능
- 베터리 체크 세분화

## Android 백그라운드 실행 및 위치제한 소개

### 베터리 최적화를 위한 제한 사항 추가
- Doze 모드 추가 : 스크린 OFF되고 5분 경과시 혹은 앱 자주 활용 하지 않을시 베터리 Saving Mode로 강제 전환
- Broadcast removal :  앱의 불필요한 Broadcast 사용 강제적 중지
- 위치 정보 가져오기 : 쓰로틀링 적용
- RAM 사용량 줄이기 권장사항 : MMC 메모리 접근 자제, Wake lock 잡고있지 말것 -> **사항 위반시 강제적 제한 걸릴수있음**

### 기존 Android OS가 느렸던 이유
- Android OS는 사용하면 사용할 수록 퍼포먼스가 내려간다는 통계가 있음
- 시간이 갈수록 OS가 느려졌던 이유
    - 앱을 활성화 시키기 위해 불필요한 broadcast receiver가 각각의 앱에 들어있었으며 앱이 늘어날수록 OS가 처리하는 업무가 늘어나는 현상이 발생
    - Android O에서는 이 부분을 개선하기 위해 Background 프로세스에 대한 제재를 확대했음

### 제한사항
- 앱의 TargetSDK를 Android O로 해야 해당 사항이 적용
- 앱의 TargetSDK가 Android O가 아니라도 Android O 사용자가 커스텀으로 제한 설정 가능
- 앱 사용 1분정도 시간이 흐르면 강제 Stop -> Doze 모드에서 WhiteList에 등록하면 예외 (단, WhiteList는 제한 기간이 있음)
- 해당되는 API : Wifi Scanning,  Location, Broadcast Receiver, Background Service
- 대처방법
  - 기존의 백그라운드 API를 Alaram manager, Job Scheduler Job Intent Service, Sync Adapter, FCN Message, Job dispatcher로 대체할것
  - API에 없는 것들은 Foreground 서비스를 쓸수 밖에 없음 API에 제공되지 않은것은 나머지는 허용되지 않음
  - 특히 Locaton은 앱의 target SDK에 상관없이 전부 영향 받음
  - 권장 Background Location API
    - Background Location API :  30분에 한번 정도 데이터 가져옴
    - Batched Location : 중간 중간 Tracking 정보를 같이 가져옴
    - Geofencing Location : 2 - 3분 업데이트 가능

### Improving Health with data
- 픽셀 or 넥서스에 한해 데이터를 가져와 분석
- 다른 기기의 경우 Vital 정보 사용할수 없음 (제조사에서 지원해야 함)
- 앱의 상태 System Health 정보 지원

## 추가로 나왔던 질문사항들
Q) Background로 판단되는 기준이 무엇인지<br>
A) 화면이 보일때는 Foreground로 판단된다. Content Provider, Service 가동 중에도 마찬가지로 Foreground로 판단된다, Activity 생명주기로 말하자면 onStart부터 OnPause까지 Foreground이며 나머지는 Background 이다.<br>
Q) 잠금 상태일때 Background Process를 사용하기 위해선 어떻게 해야하나<br>
A) 반드시 액티비티를 사용해야 하며, **락스크린에 이제 뭔가 띄우는건 불가능하다**<br>

## 참고자료
Font in XML [#](https://developer.android.com/guide/topics/ui/look-and-feel/fonts-in-xml.html)<br>
Autofill [#](https://developer.android.com/reference/android/view/autofill/package-summary.html)<br>
Migrating to Android O [#](https://developer.android.com/about/versions/oreo/android-8.0-migration.html)<br>
{% include comments.html %}
