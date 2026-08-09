# Late Fusion

이미지 모델(YOLO / Faster R-CNN)과 센서 모델의 예측 결과를 결합하는 영역입니다.

## Input Candidates

- 이미지: 클래스별 confidence / defect probability
- 센서: binary defect probability + multi-label probabilities

## Baseline

가장 먼저 단순 weighted late fusion을 baseline으로 사용합니다.

```text
final_risk = alpha * image_score + (1 - alpha) * sensor_score
```

`alpha`와 각 threshold는 Validation 데이터에서 결정하고 Test에는 한 번만 적용합니다.
