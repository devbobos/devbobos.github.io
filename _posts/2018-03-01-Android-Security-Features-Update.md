---
title: Android Security Features Update
layout: post
comments: true
tags:
- GoogleAppExcellence
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>
Google App Excellence 8월 세미나 내용 중 두번째 섹션인 Android Security Features Update이다.

1. OS Features
- 인증된 부팅 제공
- 파일 기반 암호화 제공
- 직접 부팅 제공
- 향상된 보안 패치 제공
- 앱 서명 제공

2. App Features
- Keystore : 암호키를 사용하여 다른 장비에서 Project 유출을 힘들게함 (Android Studio에서 Signed APK 빌드 할때 하는 겁니다)
- PlayProtect : GooglePlay에서 제공하는 것으로 유출 방지용
- reCAPTCHA 기능 제공

<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-01/2.gif' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>reCAPTCHA</h3>
</header>
</div>
</div>
</div>

3. Android O Features
- 모르는 앱 설치 경고
- 랜섬웨어 방지 기능
- 웹뷰 안전 브라우징 기능 업데이트

4. 사용할 수 있는 검증 방법
- SMS 검증
- 구글 메시지 검증
- OTP 앱 검증
- 보안 키 검증

## 참고자료
Android KeyStore 시스템 [#](https://developer.android.com/training/articles/keystore.html?hl=ko)<br>
Android PlayProtect [#](https://www.android.com/play-protect/)<br>
SefetyNet reCAPTCHA API [#](https://developer.android.com/training/safetynet/recaptcha.html)<br>
{% include comments.html %}
