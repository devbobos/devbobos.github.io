---
title: What's new in Android
layout: post
comments: true
tags:
- GoogleAppExcellence
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>
Google App Excellence 6월 세미나 내용 중 두번째 섹션인 What's new in Android이다.

### PIP
- Picture in Picture 기능
- Android O에 한정하여 사용 가능하다
- 사용방법 : xml에 프로퍼티에 추가, Activity에 옵션하나 추가
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-02-28/3.jpg' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>PIP</h3>
</header>
</div>
</div>
</div>

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
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-02-28/4.gif' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>AutoSizing TextView</h3>
</header>
</div>
</div>
</div>

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

<div class="row">
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-02-28/5.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>Kotlin</h3>
</header>
</div>
</div>
</div>

## 참고자료
Android O 변경사항 [#](https://developer.android.com/about/versions/oreo/index.html?hl=ko)<br>
Kotlin and Android [#](https://developer.android.com/kotlin/index.html)<br>
