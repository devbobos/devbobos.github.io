---
title: Telegram Instant View 지원하기
layout: post
comments: true
tags:
- Web
---
Instant View는 사실 제작년에 나온 Telegram 신기능인데, 블로그도 열었을겸 한번 해보고 싶었다. 이게 무엇이냐 간단히 얘기를 하자면 페이지를 저장해놓고 빨리 불러오는 기능이라고 보면 되겠다.

<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'https://instantview.telegram.org/file/811140915/2/bVBQHilQshY.84355/0ead38bc9a0136a38e' | absolute_url }}" alt="telegram instant view"></a>
<header>
<h3>Telegram Instant View</h3>
</header>
</div>
</div>
</div>
여느 메신저와 같이 Telegram은 웹사이트 주소를 메시지로 전송하면 해당 웹페이지의 메타데이터를 가져와 보여주는데. Instant View 기능을 구현하면 위와 같이 아래에 **INSTANT VIEW** 버튼이 생기고 해당 버튼을 눌러 페이지를 볼 수 있는 기능이 생긴다. 이 방법을 사용해서 웹페이지를 보게 되면 레이아웃이 변경되며 로딩이 겁나 빨리 되는 변화가 생긴다. 처음에는 Safari나 Firefox의 읽기도구 비슷한 기능인줄 알았는데, 웹사이트 데이터가 Telegram 서버에 캐시되어 로딩시간이 엄청나게 줄어드므로 Telegram 내에서 웹사이트를 조회하는 사용자의 편의성을 한층 더 증가시키는 한가지 방법이라고 볼 수 있겠다.

<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'https://instantview.telegram.org/file/811140020/2/8E3vmEN_Jlw.185118/f36256f7768563cf37' | absolute_url }}" alt="telegram instant view"></a>
<header>
<h3>Telegram Instant View Editor</h3>
</header>
</div>
</div>
</div>
게다가 특이한 장점이 있는데, 웹사이트를 수정하지 않아도 Instant View를 쓸수있다는거다. Telegram 측에서 제공하는 **Instant View Editor** 를 사용해서 Instant View에서 보여질 화면에 대한 내용을 작성하여 바로바로 어떻게 적용되는지 확인할 수 있다. 작성방법은 살짝 Jquery랑 비슷한데, 웹 컴포넌트들을 [미리 지정되어있는 인자](https://instantview.telegram.org/docs)를 사용하거나 혹은 id, class를 사용해서 조회하여 삭제하거나 수정하면 된다. sibling을 이용하는거 보면 CSS 사용법과도 유사하다고 볼 수 있겠다. 작성 순서는 다음과 같다.

1. Instant View의 섹션 요소 설정하기 : header나 body를 정의한다, 특이하게 Instant View는 cover도 정의할 수 있다.
2. Instant View의 주요 요소 설정하기 : title이나 author, date등을 설정한다. 보통 InstantView의 subTitle 부분에 작성하는듯 하다.
3. 쓸데없는 요소들 삭제하기 : 읽기도구를 생각하면 편한데, 가독성을 높이기 위해 쓸모없는 요소들은 다 쳐버리는 것이다. Footer 등을 예시로 들 수 있겠다.

필자가 작성해본 Instant View 작성본은 다음과 같다.
{% highlight css %}
?path: /.+
# basic initialize
$header: //header
body:    //article

# initialize sections
title:          $body//h2
subtitle: $header//p
author:         $header//address/a[@rel="author"]
author_url:     $author/@href
published_date: $header//address/time/@datetime

# some stylish contents
<span>:  //blockquote[has-class("graf--pullquote")]//strong
<aside>: //blockquote[has-class("graf--pullquote")]
@combine(<br>,<br>): $body//pre/next-sibling::pre
@combine(<br>,<br>): $body//blockquote/next-sibling::blockquote

# remove all useless
@remove: //header
@remove: //footer
@remove: //div[@class="pagination"]
@remove: //div[@id="tag-image"]
@remove: //div[@id="disqus_thread"]
@remove: //noscript
{% endhighlight %}

이렇게 작성하고 나면 **View in Telegram** 버튼을 눌러 링크를 생성하여 공유할 수 있고, 공유하기에 표시되는 웹사이트 정보에 Instant View 버튼이 생기며 버튼을 누르면 Instant View를 사용하여 웹페이지를 볼 수 있게 된다. [생성된 링크](https://t.me/iv?url=https%3A%2F%2Fdevbobos.github.io%2F2018%2F03%2F23%2FGoogle-Assistant-%25EC%2595%25B1-%25EB%25A7%258C%25EB%2593%25A4%25EA%25B8%25B0.html&rhash=6b5e470a5d4f26)

<div class="row">
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-04-04/1.jpg' | relative_url }}" alt="공유한 모습"></a>
<header>
<h3>공유한 모습</h3>
</header>
</div>
</div>
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-04-04/2.jpg' | relative_url }}" alt="instant view로 보기"></a>
<header>
<h3>instant view로 보기</h3>
</header>
</div>
</div>
</div>
