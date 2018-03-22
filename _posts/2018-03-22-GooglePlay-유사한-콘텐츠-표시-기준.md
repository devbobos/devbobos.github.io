---
title: GooglePlay 유사한 콘텐츠 표시 기준
layout: post
comments: true
tags:
- GoogleAppExcellence
---
3월 22일에 진행된 GoogleAppExcellence 세미나에서는 짤막하게 새로 개정된 정책에 대해서 발표하는 시간을 가졌다. 구체적으로는 Android Vitals에 관한 내용이었는데 GooglePlay 유사한 콘텐츠에 관련된 내용인터라 따로 정리한다.

## 유사한 콘텐츠란?
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-22/4.png' | relative_url }}" alt="googleplay"></a>
<header>
<h3>GooglePlay 유사한 콘텐츠</h3>
</header>
</div>
</div>
</div>
먼저 유사한 콘텐츠란 GooglePlay 스토어 앱에서 상세보기를 했을때 하단에 나오는 유사한 앱을 말한다.

### 유사한 콘텐츠 표시 기준
1. 카테고리
2. Android Vitals 점수
3. 평점
4. 퍼포먼스

### Android Vital
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-22/5.png' | relative_url }}" alt="android vitals"></a>
<header>
<h3>Android Vitals Overview</h3>
</header>
</div>
</div>
</div>
언급했던 내용 중에서 가장 중요하게 다뤄졌던 항목이다. 간단히 말하자면 앱의 안정도 평가지수라고 할 수 있겠다. 앱이 비정상 종료를 하면 할 수록 점수가 내려가고 안정적일 수록 점수가 올라가며 이는 [Google Play Console](https://developer.android.com/distribute/console/index.html?hl=ko)의 Android Vitals 항목에서 확인가능하다. Google 측은 퍼포먼스나 평점도 중요하지만 **유사한 앱의 반영 지수에 Android Vital에 대한 지분을 높였다** 고 직접 언급했으며 유사한 콘텐츠에 자신의 앱이 반영되고 싶을 경우 Android Vitals의 점수를 올리면 된다고 하였다. 특히 CrashRate가 높아져서 Android Vitals 항목이 **붉게** 표시가 된다면 안좋은 수치를 받았다는 의미이며 유사한 콘텐츠 반영에 상당한 불이익을 받을 수 있다고 한다. 점수를 높이기 위한 구체적인 방법은 이 [도큐먼트](https://developer.android.com/topic/performance/vitals/index.html)를 참고해보자.
