# ML_honey_tip

## 교차검증
- 이진분류학습에서 레이블의 분포가 크게 치우친 경우, k-폴드 교차검증을 사용하는 것은 위험. 타겟 변수에 다른 변수가 들어갈 수 있기 때문. How to solve? 계층별 k-폴드 교차검증 사용

- 홀드아웃 : 시계열 데이터를 다룰 때 자주 사용

- LOO(leave-one-out) 검증 : 데이터 크기가 아주 작은 경우, 검증에 많은 샘플을 할당하게 되면 학습에 사용할 데이터 부족하게 될때 사용
- Sturge rule : 통계 데이터 집합을 그래픽으로 표현하는 데 필요한 클래스 또는 간격의 수를 결정하는 데 사용되는 기준

``` python3
data.loc[:, "bins"] = pd.cut(
    data["target"], bins = num_bins, labels = False
)
```