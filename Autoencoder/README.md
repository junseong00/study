## 🔍 Autoencoder란?
Autoencoder(오토인코더)는 **비지도 학습(Unsupervised Learning)**을 활용하여 데이터의 중요한 특징을 학습하는 **신경망 기반 차원 축소 모델**입니다. 데이터 압축, 노이즈 제거, 특징 학습 등에 널리 사용됩니다.

## 📌 Autoencoder 구조
Autoencoder는 일반적으로 **Encoder-Decoder 구조**로 이루어져 있으며, 입력 데이터를 압축한 후 다시 복원하는 과정에서 데이터의 중요한 특징을 학습합니다.

### 1) 인코더(Encoder)
- 입력 데이터를 더 작은 차원의 **잠재 공간(Latent Space)**으로 변환합니다.
- 차원 축소와 정보 요약을 담당합니다.
- 주로 `Dense`, `Convolutional`, `Recurrent` 레이어를 사용합니다.

### 2) 디코더(Decoder)
- 인코더에서 축소된 데이터를 다시 원래 차원으로 복원합니다.
- 인코더가 학습한 정보만을 기반으로 원본을 재구성합니다.

### 3) 손실 함수(Loss Function)
- Autoencoder의 목표는 입력과 출력 간의 **재구성 오차(Reconstruction Error)**를 최소화하는 것입니다.
- 일반적으로 `MSE(Mean Squared Error)` 또는 `Binary Cross-Entropy` 손실 함수를 사용합니다.

## 📌 Autoencoder의 주요 유형
Autoencoder는 목적에 따라 여러 변형이 존재합니다.

### 1) Sparse Autoencoder (희소 오토인코더)
- 활성 뉴런 수를 제한하여 특정 특징만을 학습하도록 유도합니다.
- `L1` 정규화를 적용하여 특정 뉴런만 활성화되도록 유도합니다.

### 2) Denoising Autoencoder (잡음 제거 오토인코더)
- 입력 데이터에 노이즈를 추가한 후 이를 제거하는 방식으로 학습합니다.
- `Dropout` 또는 `Gaussian Noise` 기법을 사용하여 노이즈를 적용합니다.

### 3) Variational Autoencoder (VAE, 변분 오토인코더)
- 입력 데이터의 분포를 학습하여 샘플링이 가능한 확률 모델을 생성합니다.
- 이미지 생성, 데이터 증강 등에 활용됩니다.

## 📌 Autoencoder의 활용 사례
- **이상 탐지(Anommaly Detection)**: 훈련의 일부로 재구성 오차(Reconstruction error)를 최소화하려 하므로 재구성 손실의 크기를 통하여 이상치를 탐지 가능
- **차원 축소(Dimensionality Reduction)**: PCA(주성분 분석) 대체 가능
- **노이즈 제거(Denoising)**: 이미지 및 음성 신호의 잡음 제거
- **생성 모델(Generative Models)**: 새로운 데이터 샘플 생성
- **추천 시스템(Recommendation Systems)**: 사용자 선호도 분석
