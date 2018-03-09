---
title: SafetyNet으로 보안 위협으로부터 보호하기
layout: post
comments: true
tags:
- GoogleAppExcellence
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>
7월 세미나는 진행되지 않았고 2일에 Google I/O Extended in Seoul이 진행되었으므로 8월에 진행된 세미나 내용을 정리하려고 한다. 8월에는 쉽게 접할수 없는 Android 보안에 관한 내용이 다뤄졌다. 기본으로 고려해야 될 사항임에도 불구하고 보안 쪽은 적용하기가 까다로운 부분이니 도움이 될만한 자료가 될것 같다.

### 보안 신경쓸것들
- 신뢰할 수 있는 API인지 알아보고 사용할것
- Android OS가 디바이스 마다 커스텀되므로 호환성을 체크할것

### SafetyNet 증명제시를 사용하여 Server-Side 검증하기
- SafetyNet : Device tampering, Bad URLs, 위험성을 내폰한 앱 혹은 가짜 유저등의 보안 위협에서 대처하는 방법을 제공해준다
- 사용법
  1. API KEY 할당받기
  2. 기기 동작 확인하기
  3. 서버에 데이터를 보내어 검증받기
  4. SSL 인증을 헤더에서 확인하기
  5. attest.android.com에서 Sign 검증받기
  6. SSL 사인 인증받기
  7. 기기 상태를 채킹하기 전 timestamp, package name, hash 값 확인하기

<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-01/1.jpg' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>Secure Flow with SafetyNet</h3>
</header>
</div>
</div>
</div>

## 참고자료
Protecting Against Security Threats with SafetyNet[#](https://developer.android.com/training/safetynet/index.html)<br>
