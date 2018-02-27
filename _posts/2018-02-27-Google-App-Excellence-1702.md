---
title: Google App Excellence 17/02
layout: post
comments: true
tags:
- Android
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
작년 2월부터 구글캠퍼스 서울에서 진행한 Google App Excellence Program 에 가서 들었던 내용을 정리하려고 한다. 그 당시 별일이 없었을 경우에 한해 꼬박꼬박 참석하였고 당장 필요하다기 보다는 시간을 들여 하나하나 해봐야하는 내용이었기에 이렇게 정리해놓는것이 도움이 될듯하다.
강의는 대게 3개 정도의 섹션으로 나뉘어져 보통 각자 다른 사람이 발표를 하고 모든 섹션이 끝난 뒤에는 각자 미처 물어보지 못한 질문을 개인적으로 물어보거나 혹은 개발자들끼리 모여서 자기소개를 해가며 Networking 시간을 보내는 것으로 진행되었다. 덤으로 섹션 중간중간 쉬는 시간에는 간혹 커피와 쿠키들이 제공되기도 하고 Networking 시간에는 무조건으로 명성높은 구글의 간식들이 제공된다. 참고로 2월 세미나에서는 참치 까나페와 스낵, 피자, 맥주 등이 제공 되었다.<br><br>
<img src="{{ 'assets/images/stickers/cheers.gif' | relative_url }}" alt="sticker"  align="middle"><br>
(맥주는 어메이징 브루잉 컴패니라고 처음 보는 곳이었는데 맛있었다 맥주 맛좀 아는 구글 성님)

이하 내용은 세미나에서 진행한 내용이다

<h2>차이를 만드는 App Excellence Program</h2>
<p>민경환</p>
차이의 정의가 뭘까?
<h3>시작점</h3>
<ul>
<li>유저가 현재 느끼는 앱 경험</li>
<li>유저가 현재 앱을 찾고 다운로드 하는 경험</li>
<li>개발자가 현재 알고있는 유저에 대한 정보</li>
<li>개발자가 현재 운영 / 개발에 소요되는 리소스</li>
</ul>
<h3>목표점</h3>
<ul>
<li>유저가 바라는 앱 경험</li>
<li>유저가 더욱 효율적으로 앱을 찾고 다운로드하는 경험</li>
<li>개발자가 알아야하는 유저에 대한 인사이트</li>
<li>개발자가 더욱 효율적으로 운영 개발할수 있도록하는 리소스 최적화</li>
</ul>
<h3>결론</h3>
<ul>
<li>디자인</li>
<li>개발</li>
<li>배포</li>
</ul>
<p>이 목록을 신경쓸것!</p>
<h2>안드로이드 앱의 시작 - 개발자 콘솔</h2>
<p>임형준, 양찬석</p>
<ul>
<li>Managed Release : 최근 업데이트된 콘솔로 갈 경우 APK 탭에서 릴리즈 했던 것들이 Managed Release로 이동하여 플랫폼 버전 별 대응이 가능함</li>
<li>펀드 이슈 : Subscription을 최대한 활용할것</li>
<li>Crash Reporting : 신용하지 말것! 다른 Crash Report 툴과 병용할것</li>
<li>App Security : Document에 리스트가 있으므로 대조하며 개선해나갈것</li>
<li>Fragment Injection</li>
</ul>
<h3>결론</h3>
<ul>
<li>StoreListingExperiments 알아볼것</li>
<li>GooglePlay Developer Console APK를 다운해서 리뷰 확인할것</li>
<li>Crash Report 적용할것</li>
<li>App Security 대처할것</li>
</ul>
<h2>우수 사례를 통해 바라본 고품질의 안드로이드 앱, 게임</h2>
<p>임성혁</p>
<ul>
<li>평점은 다운로드 수와 직결한다</li>
<li>메테리얼 디자인을 생활화하자 #</li>
<li>구글에서 제공하는 메테리얼 아이콘 사용 권장</li>
<li>단말기의 다양성을 고려하여 개발할것</li>
<li>Manifest.xml의 supports screen 건들지 말것 -> 스토어에서 검색이 되지 않는다!</li>
<li>Manifest.xml의 use-feature 전화를 활성할 경우 태블릿 기기에서는 스토어에서 검색이 되지 않는다!</li>
<li>use-sdk의 max/min 값을 건들지 말것, 필요시 Target SDK만 수정할것, 덧붙여 최신 SDK 권장</li>
<li>Android wear의 경우 둥근 단말기를 우선으로 UI 설계할 것 -> 다른 장비는 원형에서 Crop하면 된다!</li>
<li>Runtime Permission -> 권한설명, 권한 Dialog, 설정 Intent 이동 순 구현할것 </li>
<li>별점 유도 하거나 별점에 따라 다른 피드백 제공하는 것은 정책 금지 사항!</li>
<li>고해상도 xxxhdpi에 맞춰 앱을 개발할것</li>
<li>일본의 경우 성우를 선호한다</li>
<li>한국 남성의 경우 여자 케릭터를 선호한다</li>
<li>통계적으로 플레이스토어 광고 이미지는 가로 이미지를 선호한다</li>
<li>GooglePlay Console의 Alpha, Beta 테스팅을 단계적으로 사용할것</li>
<li>사용자 리뷰 및 코멘트에 적극적으로 답변할것</li>
<li>현지화 하는 순서 -> 기존의 강세 지역(미국,일본,대한민국,대만)부터 신흥 강대지역 순으로</li>
<li>발전 도상의 신흥 국가 공략법
<ul>
<li>APK 용량 최소화</li>
<li>오프라인 방식 활용</li>
<li>메모리 사용 축소</li>
<li>대상 국가 내 저사양 단말기로 테스트</li>
<li>현지에서 통용되는 제화 사용</li>
</ul>
</li>
<li>
용량 줄이는 법
<ul>
<li>buildType의 minifyenabled 옵션 사용할것 자동으로 코드 용량을 줄여준다!</li>
<li>이미지 리소스의 포맷을 webp로 사용할것</li>
</ul>
</li>
</ul>

<h2>추가로 나왔던 질문사항들</h2>
Q) Runtime Permission 체크가 UX를 해치는데 없어질 가능성은 없는지?
<p>A) 없다. 보안 이슈에 대처하여 오히려 더 강화될 예정이다</p>
Q) 타 업체에서 인스톨하여 다운로드 수를 높이는 것에 대해서 어떻게 대처해야하나?
<p>A) 현재도 구글 내부적으로 조치를 하고 있으며, 높은 확률로 비정상적인 경로로 설치가 될 경우 설치 횟수에서 차감되도록 조치 중이다.
Q) 유사 경쟁 앱에 대해서 어떻게 대처해야하나?
<p>A) 카피캣은 구글에서도 자체적으로 제재를 가하고 있다.</p>

이상 2017년 Google AppExcellence 세미나에 대한 내용이었습니다.
{% include comments.html %}
