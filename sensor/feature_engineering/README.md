# Sensor Feature Engineering

기존 센서 실험의 피처 생성 및 선택 과정을 보존하는 영역입니다.

## Experiments to Preserve

- 기본 통계: mean, std, min, max, range
- 고급 통계: median, IQR, skewness, kurtosis, CV, delta
- 순간 변화: adjacent diff max/mean, total delta
- 센서 상호작용: vibration/acceleration, noise/vibration, temperature×humidity
- KS-test 기반 top-k feature selection
- CatBoost / LightGBM / EasyEnsemble 비교

실험마다 사용 피처, 모델 파라미터, Validation threshold, Test 결과를 함께 기록합니다.
