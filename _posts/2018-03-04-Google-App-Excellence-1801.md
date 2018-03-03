---
title: Google App Excellence 18/01
layout: post
comments: true
tags:
- Android
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;"><br>
17년도 Google App Excellence 세미나가 마무리 되는 도중 18년에도 진행한다는 말이 없었고 세미나 자체도 이벤트성에 가깝다고 생각하여 18년에는 진행하지 않을 줄 알았으나, 18년도 세미나 진행에 대한 공지가 내려왔다. 사정이 있어 1월 세미나엔 참석을 하지 못했지만 대충 아젠다를 보니 스터디 팀을 재정비하고 앞으로 세미나 진행에 대한 브리핑을 한 모양이다. 직접 듣지는 못했지만 발표자료를 토대로 포스팅을 진행해보려고 한다.

## Best Practice on Android Instant Apps / 지도현 wanted
- 빠른실행 앱을 사용하여 실제 앱과 동일한 경험을 주며 접근성을 향상시킬 수 있다
- 빠른실행 앱은 링크 클릭만으로 동작하지만 웹앱이 아니다!

### 개발자로써 해야할일
- Android Studio 3.0 필요
- Instant Apps SDK 필요
- 프로젝트 구조 변경 필요
- 라이브러리 호환성 체크

### 개발 준비물

<div class="row">
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/1.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>Android Studio 3.0 버전 이상</h3>
</header>
</div>
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/2.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>Android Instant App SDK</h3>
</header>
</div>
</div>
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/3.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>URL 핸들링을 지원하는 App Link</h3>
</header>
</div>
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/12.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>App Link를 지원하는 테스트 디바이스</h3>
</header>
</div>
</div>
</div>

### 프로젝트 구조 변경

<div class="row">
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/4.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>Google 권장</h3>
</header>
</div>
</div>
<div class="6u 12u$(mobile)">
<div class="item">
<header>
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/5.png' | relative_url }}" alt="image" style="width:100%;"></a>
<h3>원티드의 경우</h3>
</header>
</div>
</div>
</div>

### 프로젝트 세팅

<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/6.png' | relative_url }}" alt="image"></a>
<header>
<h3>wanted-feature-base #1 : com.android.library 대신 com.android.feature이 쓰인다</h3>
</header>
</div>
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/7.png' | relative_url }}" alt="image"></a>
<header>
<h3>wanted-feature-base #2 : Base Feature는 필수적인 것만 사용한다</h3>
</header>
</div>
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/8.png' | relative_url }}" alt="image"></a>
<header>
<h3>wanted-feature-ia</h3>
</header>
</div>
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/9.png' | relative_url }}" alt="image"></a>
<header>
<h3>AndroidManifest.xml : Deep Link 방식과 동일하게 작성한다</h3>
</header>
</div>
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/10.png' | relative_url }}" alt="image"></a>
<header>
<h3>wanted-apk-app</h3>
</header>
</div>
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-04/11.png' | relative_url }}" alt="image"></a>
<header>
<h3>wanted-instant-app</h3>
</header>
</div>
</div>
</div>

## 외부 라이브러리 호환성
- 라이브러리는 최신 버전을 사용해야함
<div class="table-wrapper">
  <table>
			<thead>
				<tr>
					<th>사용 가능한 라이브러리</th>
					<th>사용 불가능 라이브러리</th>
				</tr>
      </thead>
      <tbody>
        <tr>
					<td>FirebaseAnalytics (Core)<br>Kotlin+AndroidExtensions<br>Fabric<br>Glide<br>Retrofit<br>ReactiveX<br>RxBinding<br>Timber<br>JUnit<br>Mockito</td>
					<td>ButterKnife<br>GreenDAO</td>
				</tr>
      </tbody>
    </table>
</div>

## 주의사항
- 최종 결과물의 파일 크기가 4MB를 넘으면 안됨
- base-feature-module은 proguard 적용이 되지 않음
- flavor 구성이 있는 경우 default-URL을 설정해야함

## 참고자료
Android 빠른 실행 앱 [#](https://developer.android.com/topic/instant-apps/index.html?hl=ko)<br>
