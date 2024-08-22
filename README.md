# Hybrid_Process_Optimization
# Hybrid_Process_Optimization

**팀:** Octet Innovator  
**대회:** Chemical Engineering Process Design Competition 2024  

---

## 개요
이 저장소는 화학 공정 최적화를 위한 하이브리드 모델링 접근 방식을 구현한 프로젝트입니다. 이 프로젝트는 대규모 시뮬레이션과 머신러닝 모델을 결합하여 반응기와 스크러버 시스템을 최적화하는 데 중점을 둡니다. 복잡한 공정 조건을 체계적이고 자동화된 방식으로 분석하고 최적화하여 경제적으로 가장 유리한 공정 조합을 도출하는 것을 목표로 하고 있습니다.

## 프로젝트 구조

이 저장소는 다음과 같은 구조로 구성되어 있습니다:

- **`/simulation/`**: Aspen과 AVEVA에서 대규모 공정 시뮬레이션을 자동화하는 데 사용된 Python 스크립트 및 설정 파일을 포함합니다.
- **`/data/`**: 머신러닝 학습 및 추론에 사용된 원시 시뮬레이션 데이터, 처리된 데이터셋, 필터링된 데이터를 포함합니다.
- **`/models/`**: 머신러닝 모델과 훈련, 평가, 추론을 위한 스크립트가 포함되어 있습니다.
- **`/results/`**: 대규모 추론 및 최적화 과정의 최종 결과, 경제성 분석 및 세미 파이널 공정 조합이 포함됩니다.
- **`/docs/`**: 프로젝트와 관련된 문서, 각 단계에 대한 자세한 보고서와 설명이 포함되어 있습니다.

## 주요 단계

### 1. 시뮬레이션 데이터 생성
- **소프트웨어**: Aspen과 AVEVA를 사용하여 스크러버 및 반응기 시스템의 다양한 공정 조건을 시뮬레이션했습니다.
- **자동화**: Python 스크립트를 통해 시뮬레이션을 자동화하여 100,000개 이상의 케이스를 생성하고 `/data/` 디렉토리에 저장했습니다.

### 2. 머신러닝 모델 개발
- **훈련**: 시뮬레이션 데이터를 사용하여 스크러버 출력을 예측하고 반응기 조건을 최적화하는 머신러닝 모델을 학습시켰습니다.
- **전처리**: 원시 시뮬레이션 데이터를 클리닝하고, 필터링하고, 전처리(예: 스케일링)한 후 학습, 검증, 테스트 세트로 분할했습니다.
- **모델**: 여러 머신러닝 알고리즘을 테스트한 후, 대규모 추론에 가장 적합한 모델을 선택했습니다.

### 3. 대규모 추론 및 최적화
- **추론**: 훈련된 모델을 사용하여 수백만 개의 잠재적인 공정 조합을 추론하고, 이를 통해 수작업 시뮬레이션보다 시간을 크게 단축했습니다.
- **필터링**: 추론된 조합을 공정 제약 조건과 운영 가능성을 고려하여 필터링했습니다.
- **군집화**: DBSCAN과 같은 데이터 군집화 기법을 적용하여 공정 조합 수를 줄이고, 분석을 위한 최종 데이터를 도출했습니다.


---

**Team:** Octet Innovator  
**Competition:** Chemical Engineering Process Design Competition 2024  

---

## Overview
This repository contains the full implementation of our hybrid modeling approach for chemical process optimization. Our project focuses on integrating large-scale simulations with machine learning models to optimize reactor and scrubber systems efficiently. The primary goal is to analyze and optimize complex process conditions in a systematic and automated manner, leading to the identification of the most economically favorable process combinations.

## Project Structure

The repository is structured as follows:

- **`/simulation/`**: Contains the Python scripts and configuration files used to automate large-scale process simulations in Aspen and AVEVA.
- **`/data/`**: Includes the raw simulation data, processed datasets, and filtered data used for machine learning training and inference.
- **`/models/`**: Houses the machine learning models, along with scripts for training, evaluation, and inference.
- **`/results/`**: Contains the final results of the large-scale inference and optimization processes, including the economic analysis and semi-final process combinations.
- **`/docs/`**: Documentation related to the project, including detailed reports and explanations of each step.

## Key Steps

### 1. Simulation Data Generation
- **Software**: Aspen and AVEVA were used to simulate a wide range of process conditions in the scrubber and reactor systems.
- **Automation**: Python scripts were developed to automate the simulation process, resulting in over 100,000 cases being generated and stored in the `/data/` directory.

### 2. Machine Learning Model Development
- **Training**: The simulation data was used to train machine learning models capable of predicting scrubber outputs and optimizing reactor conditions.
- **Preprocessing**: The raw simulation data was cleaned, filtered, and preprocessed (e.g., scaling and normalization) before being split into training, validation, and test sets.
- **Model**: Multiple machine learning algorithms were tested, and the best-performing model was selected for large-scale inference.

### 3. Large-scale Inference and Optimization
- **Inference**: The trained model was used to infer millions of potential process combinations, significantly reducing the time required for manual simulations.
- **Filtering**: The predicted combinations were filtered to ensure they met process constraints and operational feasibility.
- **Clustering**: Data clustering techniques, such as DBSCAN, were applied to reduce the number of process combinations to a manageable level for further analysis.

### 4. Economic Analysis
- **Cost Estimation**: Equipment costs, operating expenses, and potential revenue were calculated for each optimized process combination.
- **Net Profit Calculation**: A detailed economic analysis was performed, considering factors such as inflation and operational longevity, to identify the most profitable process combinations.

## Requirements

To run the simulations, train the machine learning models, and perform inference, the following dependencies are required:

- Python 3.x
- `pandas`
- `numpy`
- `scikit-learn`
- `tensorflow` or `pytorch` (depending on the chosen ML framework)
- `matplotlib`
- Aspen (for process simulations)
- AVEVA (for process simulations)

You can install the necessary Python libraries using the following command:

```bash
pip install -r requirements.txt
