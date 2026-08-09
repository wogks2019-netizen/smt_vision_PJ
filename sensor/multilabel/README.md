# Sensor Multi-label Classification

정상/불량 이진분류 이후, 불량으로 판단된 샘플의 6개 불량 라벨을 예측하는 Stage 2 영역입니다.

## Target Labels

- has_missing_solder
- has_insufficient_solder
- has_solder_short
- has_solder_ball
- has_position_shift
- has_formation_defect

복수 라벨이 동시에 1일 수 있으므로 단일 6-class softmax 문제가 아니라 multi-label 문제로 관리합니다.

## Baseline Order

1. Random Forest + MultiOutputClassifier
2. Classifier Chain
3. LightGBM/XGBoost label-wise comparison
4. Validation threshold optimization

## Metrics

라벨별 Precision / Recall / F1 / TP / FP / FN과 Macro-F1을 기록합니다.
