---
title: Google App Excellence 17/04
layout: post
comments: true
tags:
- Android
---
<img src="{{ 'assets/images/2018-02-27/google.png' | relative_url }}" alt="google" style="width:100%;">
<br>
4월 세미나는 머신 러닝 이론에 대해서 다루었다. 발표하시는 분은 친절하게도 쉽게 쉽게 설명해주신 것 같지만.. 무지무지 어려웠다! 프로그래밍 분야에서 연구하는 사람, 실전에서 사용하는 사람이 따로 있는 것처럼 머신 러닝도 이론과 실제에 대한 괴리가 커보였다. 하지만 실무자라도 알아두고 있으면 이해하는데 큰 도움이 될지도?

## 머신 러닝 이론 기초

### 머신 러닝은 뭐지?
- 인공지능 -> 머신러닝 -> 딥러닝 순으로 작은 개념

### 다양한 머신러닝 기법
1. Supervised Learning
- 특정 주제의 사진들(Labeled Data)들을 주고 이를 기반으로 분석한다
- COST를 최소화하는 것이 목적이다
- 하위 항목
  - Linear Regression (Gradient Descent) : 추정 값과 실제 값의 차이를 가장 작게 만드는 ax+b 값을 구하는 방법(Cost function), 미분을 사용한다
  - Logistic Regression
  - Softmax Regression

2. Unsupervised Learning
- 특정할 수 없는 사진들 (Unlabeled Data)을 사용하여 분석한다

3. Reinforcement Learning
- 특정 환경을 조성하여, 액션을 채우고 Reward 최대화를 목적으로 분석한다
- 예를 들면 스타크래프트 게임이라는 환경을 만들어 유저들이 어떤 전략을 쓰는지 분석한다던가..

4. Deep Neural Network & Back Propagation
- 두뇌 뉴런과 유사하게 동작함
- 비선형적 패턴 해석할때 유용하다
- 딥러닝 분석의 경우 이 이론에 다른 세부항목이 추가된 이론이다
- 데이터의 품질이 좋지 않으면 좋은 결과를 얻을 수 없다
- 데이터를 Validation 할 필요성이 있다
- 오류 사례
  - Underfitting : 데이터에 너무 관계되지 않은 결과
  - Overfitting : 데이터에 너무 의존된 결과

### Google에서 제공하는 Data
- Youtube Video Data를 사용하여 분석할 수 있도록 제공

### 딥러닝 배우기 Reference
- 페이스북 그룹 TensorFlow Korea User Group에 가입하여 공부할것
- 페이스북 그룹 arXiv Papers KR에 가입하여 공부할것 ~~잘못 적은건지 그룹이 존재하지 않는다~~
- 모두를 위한 머신러닝 / 딥러닝 책을 구입하여 공부할것! 기본을 쉽게 설명해주는 좋은 교재라 한다

## Google 클라우드 머신러닝과 응용

### Google에서 쓰이는 머신러닝
- Search : Search Ranking, Speech Recognation
- Android : 키워드 자동 제안, Speech Recognation
- Goole Play : 검색 제안
- Gmail : Spam Filtering
- Google Drive
- Google Photo : 어떠한 Context의 이미지인지 분석한다
- Inbox : 메일 송신시 내용을 분석하여 적절한 답변을 제안한다 (Smart Reply)
- Google Translation

### Custom 모델을 사용한 머신러닝
- TensorFlow를 사용할것
- TensorFlow는 Google Cloud 데이터를 토대로 이동성, 유연성을 가진 서비스를 제공한다
- TensorFlow in mobile을 사용하여 모바일 기기에 머신러닝을 도입할 수 있다!
- GPU 가속화는 Nvidia 그래픽카드만 지원하므로 Nvidia 그래픽카드를 사서 쓸것 (..)

### TensorFlow에서 제공해주는 Pre-Trained ML Model
- Cloud Vision API : 이미지, Face detection, OCR, 음란물, 장소 감지
- Cloud Speech API : 고객 응대 텍스트 녹음, 텍스트 번역 (예시 HyperConnect App)
- Cloud Video Intelligence API : 동영상 Labeling 감지, 언제 Scene이 바뀌었는지, 얼굴 감지, 재미감지

## 참고자료
TensorFlow [#](https://www.tensorflow.org)<br>
TensorFlow Korea User Group [#](https://www.facebook.com/groups/TensorFlowKR/about/)<br>
arXiv [#](https://arxiv.org)<br>
{% include comments.html %}
