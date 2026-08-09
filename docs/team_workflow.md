# Team Git Workflow

## Rule 1. Do not work directly on `main`

작업 시작 전 항상 최신 main을 받습니다.

```bash
git switch main
git pull
```

기능별 branch를 생성합니다.

```bash
git switch -c feature/작업이름
```

예시:

```text
feature/yolo
feature/faster-rcnn
feature/sensor-binary
feature/sensor-multilabel
feature/fusion
feature/optimization
```

## Rule 2. Commit messages should explain the change

```bash
git add <files>
git commit -m "feat: add sensor binary random forest baseline"
git push -u origin feature/sensor-binary
```

## Rule 3. Merge through Pull Request

GitHub에서 feature branch → `main` Pull Request를 생성하고, 변경 내용을 확인한 뒤 병합합니다.

## Rule 4. Do not push large data

GitHub에는 코드와 실험 결과만 저장합니다.

Google Drive에 보관:

- train/validation/test 원본 데이터
- ZIP 파일
- `.pt`, `.pth`, `.ckpt`, `.onnx`
- checkpoint / 대용량 output

## Rule 5. Experiment record

각 모델 실험 시 최소한 아래 내용을 기록합니다.

- 모델명
- 날짜
- 담당자
- 데이터 split
- 주요 hyperparameter
- threshold
- Validation 지표
- Test 지표
- FP/FN 분석
- 결론 / 다음 실험
