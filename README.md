# Ground-Surface-Temperature-Prediction-using-CatBoost.md

🏆 **2022 기상청 빅데이터 콘테스트 지면/지상 산출기술 부문 최우수상 수상**

본 프로젝트는 CatBoost 알고리즘을 이용하여 기상청 데이터를 기반으로 지면 및 지상 온도를 예측하는 머신러닝 모델입니다. 이 모델은 환경 모니터링 및 기상 관측의 정확도를 향상시키기 위해 개발되었습니다.

## Project Overview

- **Data Source**: 기상청 제공 데이터셋 (2020년, 2021년의 여름, 가을 8개월 데이터)
- **Key Features**: 타임스탬프, 기상 지수 (LST, 여러 Band 데이터), 태양 및 위성 각도, 온도, 습도, 토양 수분 등
- **Preprocessing Techniques**: 결측치 처리, 상관분석 기반 피처 선택, 선형 보간법
- **Modeling Approach**:
  - **Algorithm**: CatBoost Regressor 사용 (범주형 데이터 처리에 강점)
  - **Hyperparameter Optimization**: Optuna로 RMSE 기준 최적 파라미터 탐색

## Methodology

1. **Data Exploration**:
   - **Correlation Analysis**: 타겟 변수(지면 및 지상 온도)와 높은 상관을 가지는 피처 선별
   - **Missing Value Handling**: 결측 비율에 따라 다른 방법 적용 (선형 보간 및 회귀 임퓨테이션)

2. **Model Development**:
   - **CatBoost Regressor**: 범주형 데이터를 효과적으로 처리하고 GPU 사용 가능
   - **Hyperparameter Tuning**: Optuna로 주요 파라미터(깊이, 반복 횟수, 학습률 등) 최적화

3. **Model Evaluation**:
   - **RMSE**를 기준으로 모델 성능 평가. CatBoost 모델이 **1.239**의 RMSE를 기록, KNN 및 신경망 모델보다 우수함.

4. **Conclusion**:
   - CatBoost 모델은 낮은 예측 오류로 우수한 성능을 발휘함. 학습 시간 단축 및 하이퍼파라미터 최적화를 통해 추가 성능 개선 가능.


