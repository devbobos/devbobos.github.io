---
title: Unity 최적화 Tips
layout: post
comments: true
tags:
- Unity
---
<img src="{{ 'assets/images/2018-03-05/0.jpg' | relative_url }}" alt="unity" style="width:100%;"><br>
2월 26일에는 구글 캠퍼스에서 진행된 Unity 워크샵의 두번째 세션인 Unity를 최적화 하기 위한 팁들이다. 발표 내용은 굉장히 짧게 느껴졌지만 내용들은 쓸모있는 것들만 가득 차있어서 받아적는데 정신이 없을 지경이었다. 간단한 방법부터 시작해서 기존 프로젝트를 아예 새로 만드는게 나을 정도로 프로젝트 내에 긴밀하게 연결되어 있는 부분부터 여러가지 최적화 방법이 있으니 가장 빨리 할 수 있는 것부터 차근차근 진행하는게 올바른 방법이다.

## 최적화 단계
가장 기본적인 개념, 병목 제거를 완료하면 다시 프로파일링 단계로 돌아가서 최적화를 해야한다.<br>
1. 프로파일링
2. 병목 탐지
3. 병목 제거


## 객체 지향 프로그래밍 최적화
<p><span class="image left"><img src="{{ 'assets/images/2018-03-06/1.png' | relative_url }}" alt="oop"/></span>Unity는 C# 프레임워크인 Mono에 기반해서 작성되었으므로 엔진 자체가 객체 지향 기반으로 작성되어 있다. 그말인 즉슨, Unity에서 사용되는 기능 객체는 부모 객체에 상속되어 동작한다는 것인데 여기서 문제는 동작이 변경되었다는 메시지를 보낼때 객체에 <strong>상속되어 있는 부모 객체까지 전부 Broadcast 메시징</strong> 을 한다는 점이다. 가장 대표적으로 onTransformChanged 이벤트는 형태가 변경될때 메시지를 보내게 되는데 부모 객체까지 전부 보내게 되므로 생각보다 훨씬 많은 Cost를 필요로 한다. 특히 발표자는 부모 객체가 변경 될 경우 딸려있는 자식 객체도 전부 Broadcasting을 해야하여 자식 객체가 변경되는 것보다 더 많은 메시징을 한다는 점을 강조하였다. 이를 해결하기 위한 해결책과 특히 신경써야할 객체는 다음과 같다.</p>

### 신경써야할 객체
쉽게 생각해서 신경써야할 객체는 자주 쓰이며 상속 구조가 복잡하여 Cost가 많이 드는 객체라고 하면 되겠다.<br>
1. Physics
  - Position
  - Rotation
  - Scene
2. Renderers
  - Bounding box update
3. UnityUI
4. Particle System
  - Bounding box update


### 해결방법
1. Optimize Game Object 옵션을 사용하기
  - inspector / import settings / big에 위치
  - 애니메이션 데이터를 멀티스레딩으로 동작하도록 해주는 기능이다
2. 모델 트랜스폼 Hierarchy의 extra transform 옵션을 제거하기
  - 상속 구조를 간략화하는 기능(?)
3. 이동 정보는 임시 변수를 사용하여 한군데서 처리할것
  - MVC 패턴 등을 응용하면 좋을것같다
4. setPositionAndRotation 메소드를 사용할것
  - 기존의 transform.position()에 비해 적은 메시징으로 동작을 처리 할 수 있다
  - Unity 5.6 버젼에서 추가되어 구버전에서는 사용할 수 없다
<div class="table-wrapper">
  <table border="1">
  <thead>
    <tr>
      <th>기존</th>
    </tr>
  </thead>
    <tbody>
      <tr>
        <td>
        {% highlight csharp %}
        public class ExampleClass : MonoBehaviour {
            void Example() {
                transform.position = new Vector3(0, 0, 0);
                print(transform.position.x);
            }
        }
        {% endhighlight %}
        </td>
      </tr>
    </tbody>
  </table>
</div>
<div class="table-wrapper">
  <table border="1">
  <thead>
    <tr>
      <th>권장</th>
    </tr>
  </thead>
    <tbody>
      <tr>
        <td>
        {% highlight csharp %}
        public class ExampleClass : MonoBehaviour {
            void Example() {
              transform.SetPositionAndRotation
              (
                  new Vector3( 1, 1, 1 ),
                  Quaternion.Euler( 0, 180, 0 )
              );
            }
        }
        {% endhighlight %}
        </td>
      </tr>
    </tbody>
  </table>
</div>

## Physics 최적화
<p><span class="image right"><img src="{{ 'assets/images/2018-03-06/13.png' | relative_url }}" alt="physics"/></span> Physics 최적화의 방법은 간단하면서도 어려운 부분이 많다. Unity의 Physics 알고리즘은 개발자가 건드릴 수 있는 부분이 아니거니와 게임이 복잡해질수록 Cost가 드는 것이 당연한데 쾌적한 Performance도 포기할 수 없는 중요한 요소이기 때문이다. 발표에서는 개발자 입장에서 할 수있는 몇가지 방법을 제안하였다.</p>

### 해결방법
1. Scene의 복잡도를 줄이자
  - 당연하게도 Scene에 객체가 많거나 복잡해지면 Cost가 올라간다. 타협이 필요한 부분이라고 할 수 있겠다.
2. Mesh Collider 사용을 줄이자
  - Collider 자체가 Cost가 높은데 Mesh는 독보적으로 많은 Cost를 소비한다
  - Box, Sphere, Capsule Collider 사용을 권장
<div class="table-wrapper">
  <table border="1">
  <thead>
    <tr>
      <th>Box, Sphere, Capsule Colider</th>
      <th>Mesh Collider</th>
    </tr>
  </thead>
    <tbody>
      <tr>
        <td>
        <img src="{{ 'assets/images/2018-03-06/2.png' | relative_url }}" alt="image" style="width:100%;"/>
        </td>
        <td>
        <img src="{{ 'assets/images/2018-03-06/3.jpg' | relative_url }}" alt="image" style="width:100%;"/>
        </td>
      </tr>
    </tbody>
  </table>
</div>
3. Physics time-step 줄이기
  - 대부분의 경우 time-step 값은 0.04 ~ 0.08 정도면 충분하다고 한다
  - inspector에 가서 Fixed timestep 값을 줄일것
4. RigidBody 수동 조작 줄이기
  - RigidBody는 Physics에 따라 자동으로 움직이게 되는데 수동으로 스크립트를 넣어 움직이게 되면 중첩 메시징이 된다고 한다
  - RigidBody를 적용한 객체는 되도록이면 수동으로 조작하지 말것

## Memory 최적화
사실 Memory 부분에 대해선 이렇다할 해결방법이 없고, 개발자가 알아서 잘 관리하는 수 밖에 없는 듯하다. 이 세션에서는 해결방법 대신 프로파일링 툴을 제시해주었다.

### Unity Memory Profiler 사용하기
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-06/4.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>Unity Memory Profiler</h3>
</header>
</div>
</div>
</div>
- C# 객체 및 Native 객체의 메모리 사용을 확인 가능하다
- Memory Snapshot을 사용하여 메모리를 많이 차지하는 영역을 파악해 줄여 나가야한다
- 모바일 게임을 개발하는 경우 고해상도가 그렇게 필요하지 않음을 염두하고 타협해야한다

## Texture 최적화
간단히 말해서 영상 처리 압축 기법을 적용하는 것이라고 볼 수 있겠다. 이미 시중에 여러가지 방법이 나와있고 Asset으로도 여러가지 방법이 있어서 개발자가 판단하여 적용하면 될듯하다. 여기서 유의할 점은 svg 확장자를 가진 벡터 이미지가 Disk Memory 상에선 가장 적은 메모리를 가지지만 프로젝트를 실행할때는 오히려 png나 jpg 확장자를 가진 이미지 보다 훨씬 많은 메모리를 차지하는 것처럼 Disk Memory와 GPU Memory 할당은 전혀 다르다는 사실을 염두해야 할것같다.

### Texture 압축의 중요 요소
- GPU Memory 할당량
- Random Access 속도
- 디코딩 속도

### Unity에 Texture 압축 적용하기
- inspector에서 Format을 적용하면 된다

### 압축 방법
1. 가변 비율 인코딩
- 간단한 압축 방식이다
- 복잡도에 따라서 오히려 용량이 늘어날 수도 있다
<div class="table-wrapper">
  <table border="1">
  <thead>
    <tr>
      <th>압축 전</th>
      <th>압축 후</th>
    </tr>
  </thead>
    <tbody>
      <tr>
        <td>
        AAAAABBBBCCCD
        </td>
        <td>
        A5B4C3D1
        </td>
      </tr>
      <tr>
        <td>
        AABCCDFG
        </td>
        <td>
        A2B1C2D1F1G1
        </td>
      </tr>
    </tbody>
  </table>
</div>
2. 고정 비율 인코딩
- 손실을 감수하고 4:1, 8:1 비율 등올 픽셀 값을 추출하여 압축하는 방식이다
- PVRTC 방식 : 블럭단위로 대표 컬러를 뽑아서 압축한다, Quality는 Good 정도
- ETC1 : 사람의 눈이 밝기에 더 민감하다는 사실에 기반하여 색상을 저해상도로 제한하고 밝기를 1:1 스케일로 가져온다, Quality는 Better 정도
- ETC2
  - ETC1과 같은 동작을 하나 더 좋은 결과물을 내준다, Quality는 Best 정도
  - OpenGL ES 3.0부터 지원하기 때문에 Android OS 지원 이슈가 있다, Android 4.3 미만은 지원하지 않으므로 해당 기기에서 해당 옵션을 사용할 경우 **압축하지 않고 메모리에 적재** 해버리기에 자칫하면 Out of memory 에러가 날 수도 있다
  - Unity 2017 버전에서는 지원하지 않을 경우의 예외처리가 가능하다 (ETC2 Fallback 기능)
<div class="row">
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-06/5.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>비교1</h3>
</header>
</div>
</div>
<div class="6u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-06/6.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>비교2</h3>
</header>
</div>
</div>
</div>
3. Dither4444
- 커스텀 에셋으로 직접 적용하여 사용한다
- 16bit로 Low Scaling 시 발생하는 경계면들을 Dithering을 통하여 완화시켜준다
<div class="table-wrapper">
  <table border="1">
  <thead>
    <tr>
      <th>압축 전</th>
      <th>압축 후</th>
    </tr>
  </thead>
    <tbody>
      <tr>
        <td>
        <img src="{{ 'assets/images/2018-03-06/7.png' | relative_url }}" alt="image" style="width:100%;"/><br>
        Original (90kb)
        </td>
        <td>
        <img src="{{ 'assets/images/2018-03-06/8.png' | relative_url }}" alt="image" style="width:100%;"/><br>
        16bit Low Scaling (42kb)
        </td>
      </tr>
      <tr>
        <td>
        <img src="{{ 'assets/images/2018-03-06/7.png' | relative_url }}" alt="image" style="width:100%;"/><br>
        Original (90kb)
        </td>
        <td>
        <img src="{{ 'assets/images/2018-03-06/9.png' | relative_url }}" alt="image" style="width:100%;"/><br>
        Dither4444 (84kb)
        </td>
      </tr>
    </tbody>
  </table>
</div>
4. ChromaPack
- 커스텀 에셋으로 직접 적용하여 사용한다
- SubSampling 기법을 사용한다
- 높은 쉐이더 성능을 필요로 한다
- Alpha 채널이 1bit로 제한되어 있다 (투명도의 Opacity가 0%/100%로만 사용 가능)
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-06/10.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>ChromaPack 적용 전후</h3>
</header>
</div>
</div>
</div>

## AssetDependency 최적화
에셋은 개발자가 의존성을 적용시킬 수 있는데, 특히 그룹화 시켜 사용할때 제대로 관리하지 않으면 중복된 리소스를 메모리에 올려 사용하게 될 수 있다. 예를 들어 A와 B가 같은 TextureC 이미지를 사용한다고 할때, A-TextureC, B-TextureC 처럼 이어져야 메모리에 TextureC 하나만 올라간다는 식이다. 하지만 프로젝트가 커지면 커질수록 관리하기가 어려워지고 Legacy 프로젝트를 밑에서 부터 하나하나 살펴볼수도 없다는 문제점이 있으므로 다음과 같은 프로파일링 툴을 사용하여 관리해줘야한다.

### Unity Asset Bundle Browser Tool
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-06/12.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>Unity Asset Bundle Browser Tool</h3>
</header>
</div>
</div>
</div>

### Asset Bundle Graph Tool
<div class="row">
<div class="12u 12u$(mobile)">
<div class="item">
<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-06/11.png' | relative_url }}" alt="image" style="width:100%;"></a>
<header>
<h3>Asset Bundle Graph Tool</h3>
</header>
</div>
</div>
</div>

## 참고자료
Optimizing the Hierarchy [#](https://blogs.unity3d.com/kr/2017/06/29/best-practices-from-the-spotlight-team-optimizing-the-hierarchy/)<br>
MVC 패턴 [#](https://ko.wikipedia.org/wiki/모델-뷰-컨트롤러)<br>
Unity Memory Profiler [#](https://bitbucket.org/Unity-Technologies/memoryprofiler)<br>
Dither4444 [#](https://github.com/keijiro/unity-dither4444)<br>
ChromaPack [#](https://github.com/keijiro/ChromaPack)<br>
Unity 에셋 번들 브라우저 툴 [#](https://docs.unity3d.com/kr/current/Manual/AssetBundles-Browser.html)<br>
AssetBundleGraph Tool [#](https://bitbucket.org/Unity-Technologies/assetbundlegraphtool)<br>
