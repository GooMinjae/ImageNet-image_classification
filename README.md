# ImageNet-image_classification

ImageNet 이미지를 사용하여 분류모델을 만드는 Kaggle Competition 프로젝트입니다.

최종 제출 Score: 68.4 %

---

### 🔍 사용한 모델 및 기법

* Base Model: **ResNet-34**

* Regularization: **EarlyStopping, EMA (Exponential Moving Average)**

* Augmentation: **Albumentation**

* Learning Rate Scheduler: **OneCycleLR**

* Inference Trick: **TTA (Test-Time Augmentation)**

---

### ⚙️ 학습 과정 중 겪은 이슈 및 해결 경험

* 모델 학습 시간 문제

    ImageNet 기반의 대규모 데이터셋 특성상 학습 시간이 매우 오래 걸렸습니다.

    이에 따라, Albumentations 라이브러리를 활용해 빠르고 효율적인 데이터 증강을 적용하여 학습 속도를 개선하고 일반화 성능도 향상시킬 수 있었습니다.

* 클래스 구성의 어려움

    일부 클래스에는 사람이 포함된 이미지가 많은 경우가 있었고, 이로 인해 모델이 배경이나 인물에 의존적으로 학습하는 경향이 나타났습니다.

    이를 극복하기 위해, 불필요한 시각적 특징을 줄이도록 증강 기법을 조정하거나 클래스 간 분포를 재검토하는 등의 추가적인 작업이 필요했습니다.