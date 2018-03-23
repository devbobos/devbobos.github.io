---
title: Google Assistant 앱 만들기
layout: post
comments: true
tags:
- GoogleAppExcellence
---
<p><span class="image right"><img src="{{ 'assets/images/2018-03-23/4.jpg' | relative_url }}" alt="GoogleAppExcellence" /></span>3월 22일의 GoogleAppExcellence에서는 이제부터 세미나에서 섹션을 교육적인거 하나 협력사 발표 하나 형식으로 바꿔서 체계적으로 세미나가 진행될것이라고 발표하였다. 협력사 발표 섹션은 Snow의 Foodie 성공기가 다뤄졌는데 "대충했는데 운이 좋아서 성공했어요" 라는 전혀 쓸모없는 내용이었기 때문에 따로 포스팅을 하지 않을 생각이고 교육적인 섹션에서 다뤄졌던 <b>Google Assistant</b> 에 대한 내용을 이번 포스팅에 다뤄볼 생각이다.</p>

<div class="row">
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/6.jpg' | relative_url }}" alt="foodie"></a>
<header>
<h3>성의없음의 결정체였던 협력자 섹션</h3>
</header>
</div>
</div>
</div>
~~심지어 수익구조에 관한 질문이 나왔는데 비밀이라며 말해주지도 않더라..~~

## Google Assistant란?
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/7.jpg' | relative_url }}" alt="google Assistant"></a>
<header>
<h3>Google Assistant</h3>
</header>
</div>
</div>
</div>
Apple의 Siri와 같이 비서용 프로그램이다. Google에서는 자연어 분석, 머신러닝, 음성매치등 자사의 최신 기술들이 들어있으며 Android OS가 탑재된 거의 모든 플랫폼에서 동작할 수 있음을 강조하였다. 한국에서는 17년 9월 21일에 출시를 하였으며 Android 6.0 이상의 기기에서 홈버튼을 일정시간동안 누를 경우 사용이 가능하다.

### Google Assistant의 특징
1. 음성매치
음성을 분석하여 사용자를 구분해낼수 있다고 한다. 다시 말하자면 로그인할 필요없이 사용자 음성만으로 개인별 특정 서비스를 활용할 수 있다는거다. "내가 좋아하는 음악 재생해줘"등을 생각해 볼 수 있겠다. 이 사용자 구분은 일종의 UserID로 기기를 사용하지 않을 경우 최대 30일 동안 저장한다고 한다.

2. 대화형 인터페이스
GoogleAssistant는 봇이라고 생각하면 편한데, 사용자의 입력을 받아 결과를 내는 수동적인 대화형 인터페이스라고 생각하면 된다. 물론 미리 정해놓은 흐름에 따라 동작하기 때문에 구현 여부에 따라 마치 능동적으로 동작하는 것처럼 구현할 수도 있다.(특정 입력 값에는 몇 초 뒤에 다시 말을 보내게 한다던가)

3. 다양한 플랫폼 지원
기본적인 모바일 디바이스부터 임베디드 장비까지 거의 모든 장비에 탑재가 가능하고 사용할 수 있는 언어도 무쟈게 많다고 한다.

4. Google Assistant SDK 지원
공개된 개발용 SDK를 사용하여 자신의 기기에 탑재할 수 있다. 이는 즉, 아두이노를 산 다음 탑재해서 개인 비서를 만들 수 있다는 소리다. 하지만 현재는 SDK가 Alpha2 버전이기 때문에 구현할 수 있는 한계가 있어 모바일 디바이스용 앱 개발을 권장한다.

## 자신의 Google Assistant 앱 개발하기
Google은 Google Assistant의 오픈 개발 플랫폼인 [Actions on Google](https://developers.google.com/actions/)을 지원하고 있다. Android의 Google Console처럼 [Actions Console](https://console.actions.google.com/)을 별도로 지원하고 있어서 Android를 마켓에 출시해본 개발자라면 익숙하게 사용할 수 있으며 Actions on Google 사이트에 Sample Code, Document, Community Program을 제공하고 있어 하나 둘씩 읽어보며 자신의 앱을 개발할 수 있다.
<div class="row">
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/14.jpg' | relative_url }}" alt="action on google"></a>
<header>
<h3>Actions on Google</h3>
</header>
</div>
</div>
</div>

### ActionFlow SDK
서버가 사용되지 않는 Bot을 만드는 SDK로써 서버를 거치지 않으므로 속도가 빠르지만 Web에서 정보를 가져올 수 없으므로 앱내 데이터만을 사용해 응답하여야 한다. 위에 언급하였던 PicachuTalk가 이걸로 만든듯 하다. 간단한 앱만들기에는 좋은듯.

### DialogFlow SDK
- 이전 api.ai라는 이름이었다는데 Google이 인수해서 DialogFlow로 이름을 바꿨다고 한다.
- 서버를 연동할 수 있으며 자연어 분석을 커스텀 할수 있어 보다 복잡한 봇을 만들수 있는 SDK이다.
- 서버를 쓰기 때문에 당연히 연동할 Backend 서버가 따로 필요하며 구현해줘야 한다. Google 측에서는 [Firebase CloudFuntion](https://firebase.google.com/docs/functions/?hl=ko) 사용을 추천했다.
- 아직 머신러닝 기능은 사용할 수 없는데 차차 개발할 예정이라고 한다.
<div class="row">
<div class="12u 6u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/15.jpg' | relative_url }}" alt="DialogFlow"></a>
<header>
<h3>DialogFlow</h3>
</header>
</div>
</div>
</div>

### Google Assistant에서 활용할 수 있는 UI
대화형 Flow로 이루어지기 때문에 UI에도 한계가 있는편이다. 구체적으로 사용할수 있는 UI는 다음과 같다.
<div class="row">
  <div class="6u 12u$(mobile)">
    <div class="item">
      <a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/12.png' | relative_url }}" alt="List View" /></a>
      <header>
        <h3>ListView</h3>
      </header>
    </div>
    <div class="item">
      <a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/10.gif' | relative_url }}" alt="carousel" /></a>
      <header>
        <h3>Carousel</h3>
      </header>
    </div>
  </div>
  <div class="6u 12u$(mobile)">
    <div class="item">
      <a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/9.jpg' | relative_url }}" alt="Bubble message" /></a>
      <header>
        <h3>Bubble Message</h3>
      </header>
    </div>
    <div class="item">
      <a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/11.png' | relative_url }}" alt="CardView" /></a>
      <header>
        <h3>CardView</h3>
      </header>
    </div>
  </div>
</div>

### Google Assistant의 입력 방법
음성, 텍스트, 터치가 현재 가능하며 구글 렌즈가 입력장치로 쓰이기 위해 개발 중이라고 한다. 실제로는 거의 음성이 쓰이는 추세다. 텍스트로 칠거면 차라리 구글링을 하지 Google Assistant를 사용할 이유가 없다..

### Google Assistant의 출력 방법
SSML 포멧을 사용하여 미리 지정해놓은 텍스트, 음성, 사운드 이 세가지 방법으로 출력할 수 있다. 포켓몬으로 유명한 GameFreak사는 음성 출력을 사용해 PicachuTalk라는 앱을 냈는데 아주 잘나간다고 한다. 이름 그대로 말을 걸면 피카츄 소리가 나오는 앱이다 (..)
<div class="row">
<div class="12u 6u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/13.jpg' | relative_url }}" alt="PicachuTalk"></a>
<header>
<h3>PicachuTalk</h3>
</header>
</div>
</div>
</div>

## Google Assistant 스토어
Google Assistant SDK를 사용하여 만든 개발자의 앱은 GoogleAssistant 앱만 따로 정리된 스토어에서 확인 가능하며, 스토어는 홈버튼을 일정 시간동안 눌러 GoogleAssistant를 활성화 시킨 후 오른쪽 상단에 있는 파랑색 버튼을 누르면 진입 가능하다. 앱은 고유명사로 해야하며 되도록이면 한 단어로 해야 심사를 쉽게 통과 할수있다 카더라. 뭐 실제 마켓을 보면 꼭 한 단어 이름의 앱만 있는건 아니고 다양한 이름을 갖고 있는데 **앱의 이름은 GoogleAssistant에서 URL처럼 앱을 지칭 및 호출하는 지시어로 동작** 하기 때문에 되도록이면 기억하기 쉽게 짧은 단어를 사용하는 것이 좋다고 하더라. 스토어를 통하지 않고 앱을 노출시키려면 사용자가 *"OK Google, 비트코인 시세 봇 불러줘"* 로 직접 이름을 호출하거나 Google Assistant의 비슷한 앱 추천밖에는 방법이 없다.
<div class="row">
<div class="12u 6u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/8.png' | relative_url }}" alt="google Assistant"></a>
<header>
<h3>Google Assistant 스토어</h3>
</header>
</div>
</div>
<div class="12u 6u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/1.png' | relative_url }}" alt="google Assistant"></a>
<header>
<h3>비트코인 시세 봇</h3>
</header>
</div>
</div>
</div>

## Google Assistant 앱 개발 팁
- 유저는 단순한 정보 검색보다 실제 대화하는것같은 쌍방향 대화를 선호한다
- 유저에게 정보를 효과적으로 전달하기 위한 봇의 Personality 설계를 해야한다
- 다양한 플랫폼에서의 사용을 미리 고려하여 설계하는 것이 좋다
- 작은 순간순간의 Needs를 파악하여 기획하는 것이 좋다

PS. 참고로 여느때처럼 간식으로 쿠키와 피자 치킨이 나왔다 ^q^
<div class="row">
<div class="12u 6u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/5.jpg' | relative_url }}" alt="cookie"></a>
<header>
<h3>Google Cookie</h3>
</header>
</div>
</div>
<div class="12u 6u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-23/3.jpg' | relative_url }}" alt="pizza chicken"></a>
<header>
<h3>Google P&C</h3>
</header>
</div>
</div>
</div>
