# MLDL_study
### 월간 데이콘 신용카드 사기 거래 탐지 AI 경진대회
https://dacon.io/competitions/official/235930/overview/description

## 분석 문제 정의

- 신용 카드 사기 거래 탐지 모델 개발
- 사기 거래가 무엇인지 정의 필요! ⇒ **이상치 정의가 중요**
- 사기 거래가 뭘까?
    - 일정한 패턴을 벗어난 거래
    - ex.단시간 많은 거래, 과도하게 큰 금액의 결제

**valid data는 학습에 사용 불가능 / 통계적인 검정으로만 사용 가능**

- 레이블이 없는 이상치를 어떻게 정의할 수 있을까?

-클러스터링으로 이상치 레이블 붙이기 (차원 축소 문제 존재) → 레이블을 train에 붙여주기

-valid의 이상치 비율을 그대로 따오기 → 레이블을 train에 붙여주기

-오토인코더로 레이블없이 학습 진행 (train으로만 훈련, valid로 평가) → 레이블 붙이기 X

## 프로젝트 개요

### **주제**

신용카드 거래 데이터에서 이상치를 탐지하는 분석 모델 개발

### **프로젝트 기간**

2023.03.05 ~ 2023.03.19

### 추진 배경 및 목적

- 데이콘 프로젝트 참여 및 포트폴리오 만들기
- 이상치 탐지 관련 흥미

### 프로젝트 정의

- 사기 거래를 감지하는 ai 솔루션 개발
- 주어진 데이터를 통해 이상 거래를 탐지하는 분석 모델 개발

## 분석 과정 및 결과

1. 데이터 탐색
2. EDA - feature 개수 / 이상치, 정상 데이터 각 feature 분포
3. feature engineering : feature 선택 / 전체 feature / PCA 비교
4. 모델 개발 - 이상치 탐지 모델 공부 및 비교
    - VAE
    - PCA + kernel PCA
    - AE + GAN
    - GANomaly
    - KNN
    - elliptic envelope
    - isolation forest
    - miss forest
    - DAGMM (Deep Autoencoder Gaussian Mixture Model)
    - LOF
5. 최종 모델 선정 : elliptic envelope 모델 선정
6. f1 score - public : 0.9284 / 192위!! 

**최종 모델 코드**

[Google Colaboratory](https://colab.research.google.com/drive/1ZDJL-SKoV8s2Xb-7GYa9vZWFtqaPv1MT#scrollTo=zvfSS0Obi3ea)
