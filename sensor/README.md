# Sensor Modeling

센서 파트는 정상/불량 탐지와 불량 유형 예측을 단계적으로 수행합니다.

## 1. Previous Experiments

6개 불량 라벨을 각각 직접 예측하는 Binary Relevance 접근에서 CatBoost, LightGBM, EasyEnsemble, 파생변수 및 KS 기반 Feature Selection 등을 실험했습니다. 그러나 Precision이 충분히 개선되지 않아 센서 데이터만으로 6개 불량 라벨을 바로 분리하는 데 한계가 있음을 확인했습니다.

## 2. Current Baseline: Binary Classification

6개 불량 컬럼 중 하나라도 1이면 `label=1`, 모두 0이면 `label=0`으로 정의합니다.

| Model | Accuracy |
|---|---:|
| Logistic Regression | 74.46% |
| Random Forest | Validation 96.53% |
| Random Forest | Test 97.16% |

현재 이진분류 baseline은 Random Forest입니다.

다음 검증에서는 Accuracy 외에 Precision, Recall, F1, ROC-AUC, PR-AUC, TP, FP, FN, TN을 함께 기록합니다.

## 3. Next Step: Multi-label Prediction

데이터에는 두 개 이상의 불량이 동시에 존재하는 조합이 있으므로, Stage 2는 단일 6-class multiclass보다 6개 불량 라벨을 각각 예측하는 multi-label 구조를 우선 사용합니다.

예시:

```text
[0, 0, 1, 0, 0, 1]
→ solder_short + formation_defect
```

추천 baseline:

1. Random Forest + MultiOutputClassifier
2. Classifier Chain + Random Forest/LightGBM
3. 이미지 결과와 센서 확률을 결합한 Late Fusion

## Structure

```text
sensor/
├── binary/
├── multilabel/
├── feature_engineering/
└── results/
```
