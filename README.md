# ML_honey_tip

## 결측치 처리
- dict 형태로 변수 마다 결측치 지정 가능
``` python3
alter_values = {"age":0, "gender":"man"}
df = df.fillna(value = alter_values)
```

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

## 검증 매트릭
- AUC(Area Under ROC Curve) : 편향된 이진분류 학습에서 자주 사용된다.
- AUC = 1 : 완벽한 모델. 검증에 실수가 있었을 가능성이 높다.
- AUC = 0 : 완벽하게 틀린 모델. 실수 체크 필요
- AUC = 0.5 : 랜덤한 모델.
- AUC가 0.85이면 정상 이미지 중 임의로 한 이미지를 선택하고, 기흉 이미지 중 임의로한 이미지를 선택하면, 기흉 이미지에 대한 모델의 예측 값이 정상 이미지에 대한 예측 값보다 높을 확률이 85%임을 의미함.
- MSE : 제곱을 하므로 이상치의 변화에 민감(이상치에 중점을 두고 싶을 때 사용)
- MAE, RMSE : 이상치와 상관 없이 안정된 값

## 시각화
- plt.xticks(rotation = 45) : x축 변수 각도 변화
``` python3
plt.xticks(rotation=45)
```
