# Sensor Results

센서 모델 결과 파일을 저장하는 영역입니다.

권장 파일 예시:

```text
binary_model_comparison.csv
binary_test_metrics.csv
multilabel_class_metrics.csv
thresholds.json
feature_importance.csv
```

결과 표에는 최소한 아래 항목을 포함합니다.

```text
model, split, threshold, accuracy, precision, recall, f1, roc_auc, pr_auc, TP, FP, FN, TN
```

Multi-label 결과는 클래스별 TP/FP/FN/Precision/Recall/F1과 Macro-F1을 별도로 기록합니다.
