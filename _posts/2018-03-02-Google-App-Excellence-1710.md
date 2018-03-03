---
title: Google App Excellence 17/10
layout: post
comments: true
tags:
- Android
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>
10월 세미나는 지금까지 발표되었던 세미나 내용을 실전에 적용한 상용 앱들과 적용하는 과정에서 겪었던 어려운점 그리고 성과에 관한 내용이 주가 되었다. 총 3개의 개발사가 나와서 발표하였고 각자 여러가지 관점에서 기술을 도입하여 괄목할만한 성장을 이룬듯하다.

## Machine Learning & Material Design 적용 / Mathpresso
<img src="{{ 'assets/images/2018-03-02/1.png' | relative_url }}" alt="Mathpresso" class="image centered">
- Mathpresso는 수학 문제를 데이터 베이스화 하여 풀이를 검색하는 앱을 서비스 (최근에 QANDA로 이름을 바꿨음)
- 문제 풀이 검색 서비스 + 질문 답변 서비스를 제공
  - 문제 풀이 검색 서비스 : OCR, 이미지 처리 등을 통해 수학문제 사진을 분석하여 데이터베이스에서 검색하는 기능
  - 질문 답변 서비스 : 풀이검색을 실패하거나 1:1로 묻고싶을때 쓰이는 서비스

### OCR의 적용
- 자체 OCR 기술과 Tensor Flow를 조합하여 구현
- Attention 기능 활용 : 이미지에 표시를 하여 표시 부근을 집중적으로 분석할수 있게 함, 일종의 ROI (Filter region of interest)

### Material Design 적용
- 목표 : "사용자에게 확신을 주자"
- 소요기간 : 1달
- 투입된 인력 : 3명 (개발자 1명 디자이너 1명 운영팀 1명)
- 프로덕트 아이콘
  - 보다 뚜렷한 형태와 색을 사용하여 안드로이드 향 아이콘을 제작
  - 둥근 모서리는 안드로이드 사용자를 위한 디자인이 아니니 피한다.
- Bottom Navigation
  - 사용자에게 혼란을 줄여주는 네비 제작
  - 4개 혹은 5개의 기능이 있을때, 비활성화 기능은 아이콘만 보여줌
- Card Design 
  - 내용물 계층 구조
  - 가장 중요한 정보에 사용자의 주의를 집중하기 위해서 계층구조를 사용
  - 메인 정보와 서브정보, 버튼의 계층을 구분함
- Text Field
  - 올바른 피드백 제공
  - 회원 가입 시 오류 피드백을 제공하여 사용자의 올바른 행동 유도
- 진행 과정에서 발견된 개선 요소들
  - 타 플랫폼과의 혼용 요소
    - 라운드 스퀘어 탭 (iOS)
    - 뒤로가기 (iOS)
    - 플레이 스토어 앱 소개 영상에 비 안드로이드 스마트폰 사용
- 적용 결과 (적용 후 1달간 데이터 기준)
  - 다운로드수 31% 향상
  - 가입률 10% 향상
  - 서비스 이용률 7% 향상

## ColorFil 글로벌 마켓 시장 도전기 / Yea Studio
<img src="{{ 'assets/images/2018-03-02/2.png' | relative_url }}" alt="ColorFil" class="image centered">
- 색칠공부 기능을 제공해주는 앱 "ColorFil" 서비스

### Meterial Design 적용의 장점
- 디바이스 사이즈 별 최적화 UI/UX
- 디바이스 별 이슈 최소화
- 기획 디자인 개발 모든 시간을 절약할 수 있다

### 파일 용량 최소화
- 각 나라별로 인터넷 환경 및 단말기에 따른 이슈가 있음
- 앱 설치 파일 용량이 무조건 적을수록 좋더라, ColorFil의 경우 사이즈가 20MB 미만이다
- 고객들의 평점에서 영향을 미친다
- 서버를 사용할 경우 용량을 줄일 수 있다

### 오프라인 모드 지원
- 고객 리뷰에서 오프라인 모드를 지원해달라는 제일 많은 피드백을 받았었다
- 나라별 다른 이슈, 인터넷 환경에 따른 이슈가 있어 오프라인 모드를 지원해야 한다
- 모든 기능이 오프라인일 필요는 없다, 최소한의 기능을 오프라인으로 제공하면 될것
- 고객들의 평점에서 영향을 미친다

### CS 고객 컴플레인 관리
- 별점이 낮은 것 부터 공략하자
- 리뷰 관련 이슈별로 답변을 정리하자. ColorFil의 경우 50여개의 상황별 답변을 작성하였다
- 리뷰에 주목하자
- 업데이트 이슈 Q&A 프로젝트 별 관리 문서화하자
- 버그 리포터 월간 리뷰 및 디바이스 별 모니터링이 필요하다

### Google Console Alpha/Beta 테스트 기능 활용
- 앱 아이콘 A/B 테스트
- 스크린샷 A/B 테스트
- 배포 관리 알파 베타 정식 런칭
- 데이터 기반 앱 최적화

### 기타 사항
- 과거 복잡하고 지저분하다는 평을 많이 받았는데 Meterial Design을 적용한 뒤 디자인 관련 평이 좋아졌다
- iOS의 디자인은 굳이 똑같이 만들지 않았다. 몇가지 버튼을 달리 구성하였고 iOS와 Android의 사용 패턴이 다르다는 것을 인식하고 디자인 해야한다
- 다른 대형 어플들의 벤치마킹을 많이 하였다. 모든 화면에 대해 스크린샷을 찍어 로드맵을 만들었다

## Store Listing Experiment / Delight Room
<img src="{{ 'assets/images/2018-03-02/3.png' | relative_url }}" alt="ColorFil" class="image centered">
- 사진을 찍어야 해제되는 알람 앱 "알라미"

### Remote Config를 사용한 실험
- 그래픽 이미지 변화 : 최상단 제품 설명 이미지를 변경해보면서 다운로드 수 테스트 -> 그렇게 큰 변화를 얻어내지 못함
- 간단한 설명 변화 : 제품을 간단히 설명하는 80자를 변경해보면서 다운로드 수 테스트 -> 대상 고객의 범위를 축소시켜 문구를 설정하니 좋은 성과가 나왔음
- 자세한 설명 변화 : 강조하고싶은 기능에 대해서 첫 줄에 소개하였더니 다운로드 수를 증가하였음
- 캡쳐 화면 변화 : 스크린샷의 문구를 한 줄로 변경하였더니 다운로드 수가 증가하였음

### 플레이 스토어 리뷰 관리
- 최상단의 1점 리뷰에 대해서 성심성의껏 피드백을 줬더니 5점으로 바뀌는 경우가 있음
- 리뷰에 답글을 달았을 경우 평점 평균 1.4점이 오름, 안달았을 경우 0.25점이 떨어짐

### 기타사항
- 나라별 프로모션 노하우 : 해당 국가 사용자에게 제품 코드를 제공하고 직접 제작한 문구를 어플 설명으로 사용하겠다고 공지하여 사용자의 참여를 이끌어내었다
- 좋은 가설을 세우고, 꾸준한 Alpha/Beta 테스팅을 하는 과정이 필요하다

## 참고자료
콴다 [#](https://qanda.co.kr)<br>
ColorFil [#](https://play.google.com/store/apps/details?id=net.yeastudio.colorfil&hl=ko)<br>
알라미 [#](https://play.google.com/store/apps/details?id=droom.sleepIfUCan&hl=ko)<br>
{% include comments.html %}