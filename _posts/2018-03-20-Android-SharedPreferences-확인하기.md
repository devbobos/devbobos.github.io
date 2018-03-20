---
title: Android SharedPreferences 확인하기
layout: post
comments: true
tags:
- Android
---
Android는 환경설정 등의 영구적으로 보관할 데이터들을 SharedPreferences를 사용해 저장한다. SharedPreferences는 Key-Value 형태로 값을 넣어주면 알아서 저장되기 때문에 사용하기는 쉽지만 어디에 저장되는지도 모르고 한번에 전체 데이터를 조회할 수 있는 Method도 없어서 데이터 파악이 힘들다는 점이 있다.

<div class="row">
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-20/1.png' | relative_url }}" alt="android studio device file explorer" style="width:100%;"></a>
<header>
<h3>SharedPreferences의 경로</h3>
</header>
</div>
</div>
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-20/1.png' | relative_url }}" alt="SharedPreferences" style="width:100%;"></a>
<header>
<h3>패키지 네임 폴더안에 저장된 파일들</h3>
</header>
</div>
</div>
</div>
SharedPreferences는 디바이스의 루트 경로에 저장되는데 자세한 경로는 이와 같다 <br>
<code>/data/data/{packageName}/shared_prefs/</code><br>
디바이스를 컴퓨터에 연결하고 난 뒤 Android Studio의 DeviceFileExplorer를 사용하면 손쉽게 해당 경로를 찾을수 있으며 xml 형식으로 저장된 SharedPreferences 데이터를 확인할 수 있다.

{% highlight xml %}
//SharedPreferences
<?xml version='1.0' encoding='utf-8' standalone='yes' ?>
<map>
<string name="homeMenuPosition">2</string>
<string name="userName">devbobos</string>
</map>
{% endhighlight %}
