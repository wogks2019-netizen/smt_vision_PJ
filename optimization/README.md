# Optimization

이미지/센서 fusion에서 생성된 위험도와 현장 운영 기준을 활용해 검사 우선순위 또는 작업 배치를 최적화하는 영역입니다.

## Baseline Direction

- Decision variable: 어떤 샘플을 우선 재검사할지 여부/순서
- Objective candidates: 미검 비용, 과검 비용, 작업자 재검사 부담, 대기 비용 최소화
- Constraints candidates: 시간당 재검 가능 수량, 작업자/설비 용량, 필수 검사 조건

초기 baseline은 Gurobi 기반 MILP로 구현하고, 이후 데이터가 충분하면 학습 기반 정책과 비교합니다.
