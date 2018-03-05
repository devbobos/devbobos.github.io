---
title: Machine Learning Material Design 적용 Mathpresso
layout: post
comments: true
tags:
- GoogleAppExcellence
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>
10월 세미나는 지금까지 발표되었던 세미나 내용을 실전에 적용한 상용 앱들과 적용하는 과정에서 겪었던 어려운점 그리고 성과에 관한 내용이 주가 되었다. 총 3개의 개발사가 나와서 발표하였고 각자 여러가지 관점에서 기술을 도입하여 괄목할만한 성장을 이룬듯하다. MathPresso 회사가 발표한 첫번째 세션이다.

<a href="#" class="image fit"><img src="{{ 'assets/images/2018-03-02/1.png' | relative_url }}" alt="Mathpresso"></a>
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

## 참고자료
콴다 [#](https://qanda.co.kr)<br>
Material Design Icon [#](https://material.io/icons/)<br>
{% include comments.html %}
