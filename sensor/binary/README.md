# Sensor Binary Classification

## Objective

정상(0) / 불량(1) 이진분류 baseline을 관리합니다.

불량 6개 컬럼 중 하나라도 1이면 `label=1`, 모두 0이면 `label=0`입니다.

## Current Results

| Model | Split | Accuracy |
|---|---|---:|
| Logistic Regression | Validation | 74.46% |
| Random Forest | Validation | 96.53% |
| Random Forest | Test | 97.16% |

## Required Final Metrics

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- PR-AUC
- TP / FP / FN / TN

## File Naming

기존 `untitled1.py` 같은 이름 대신 아래 형식을 권장합니다.

```text
01_sensor_binary_logistic.ipynb
02_sensor_binary_random_forest.ipynb
sensor_binary_random_forest.py
```
