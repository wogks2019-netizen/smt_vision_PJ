# Faster R-CNN

SMT 6종 불량 검출을 위한 Faster R-CNN 실험 영역입니다.

권장 하위 구조:

```text
image/faster_rcnn/
├── notebooks/
├── configs/
├── src/
└── results/
```

YOLO와 동일한 train/validation/test 기준을 사용하고, 최종 비교 시 클래스별 TP/FP/FN, Precision, Recall, F1, mAP@0.5, mAP@0.5:0.95를 기록합니다.
