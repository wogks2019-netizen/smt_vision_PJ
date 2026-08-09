# SMT Vision & Sensor Project

SMT 공정의 6종 불량을 이미지와 센서 데이터로 분석하고, 최종적으로 멀티모달 결과를 활용해 검사 우선순위/의사결정을 최적화하는 프로젝트입니다.

## Project Pipeline

1. **Image defect detection**
   - YOLO
   - Faster R-CNN
2. **Sensor defect prediction**
   - Stage 1: 정상(0) / 불량(1) 이진분류
   - Stage 2: 6개 불량 라벨 예측
3. **Late Fusion**
   - 이미지 모델과 센서 모델의 예측 결과 결합
4. **Optimization**
   - 예측 위험도와 운영 기준을 활용한 검사 우선순위 최적화

## Current Sensor Baseline

불량 6개 컬럼 중 하나라도 1이면 `defect=1`, 모두 0이면 `normal=0`으로 통합하여 정상/불량 이진분류를 수행했습니다.

| Model | Result |
|---|---:|
| Logistic Regression | Accuracy 74.46% |
| Random Forest | Validation Accuracy 96.53% |
| Random Forest | Test Accuracy 97.16% |

현재 센서 이진분류 baseline은 **Random Forest**이며, 다음 단계는 Precision, Recall, F1, ROC-AUC, PR-AUC, FP/FN을 함께 검증한 뒤 6개 불량 라벨 예측으로 확장하는 것입니다.

> 데이터에는 복수 불량 조합이 존재하므로 Stage 2는 단일 6-class 분류보다 **6-label multi-label prediction** 구조를 우선 검토합니다.

## Repository Structure

```text
smt_vision_PJ/
├── image/
│   ├── yolo/
│   └── faster_rcnn/
├── sensor/
│   ├── binary/
│   ├── multilabel/
│   ├── feature_engineering/
│   └── results/
├── fusion/
├── optimization/
├── docs/
├── requirements.txt
└── .gitignore
```

## Data Management

대용량 원본 데이터와 모델 가중치는 GitHub에 업로드하지 않습니다.

- GitHub: 코드, notebook, config, 소규모 결과 CSV/JSON, 문서
- Google Drive: train/validation/test 데이터, ZIP, 모델 weight, checkpoint

## Git Workflow

`main`에 직접 작업하지 않고 기능별 branch에서 작업한 뒤 Pull Request로 병합합니다.

예시:

```text
feature/yolo
feature/faster-rcnn
feature/sensor-binary
feature/sensor-multilabel
feature/fusion
feature/optimization
```

자세한 협업 규칙은 `docs/team_workflow.md`를 참고하세요.
