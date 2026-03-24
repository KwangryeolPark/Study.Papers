> [!PDF|] [[A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification.pdf#page=4&selection=133,0,133,1|A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification, p.4]]
> > n
> 
> 여기서 $n$은 Calibration Dataset의 개수

> [!PDF|] [[A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification.pdf#page=4&selection=110,0,120,1|A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification, p.4]]
> > $1-\alpha\le\mathbb{P}(Y_{test}\in\mathcal{C}(X_{test}))$
> 이 수식의 진정한 의미를 이해하기 위해, 다음과 같은 사고의 흐름을 따라가 보자.
> ### 1. Conformal Prediction (CP)은 Classifier를 재학습시키는 것인가?
> > **아니다.** CP에서 추구하는 것은 모델 자체의 가중치를 튜닝하는 것이 아니다. 더불어 근본적으로 Test 상황에서는 실제 정답이 없으므로 학습 자체가 불가능한다. CP는 철저히 모델의 출력 결과를 다루는 후처리 작업이다.
> 
> ### 2. 문제 상황의 인식 (수동적 정확도 vs. 능동적 오차 제어)
> * 주어진 인공지능 분류기 $\hat{f}$의 정확도가 이미 학습 과정 중에 80%로 고정되었다고 가정해 보자. 즉, 이 정확도는 과거 데이터로 측정된 수동적인 값이며 불변값이다.
> * 이 상황에서 Test 단계를 생각해 보자. 모델은 정답을 모르는 임의의 새로운 이미지 $X_{test}$를 받는다. 그리고 일반적으로는 확률이 가장 높은 단일 예측 label $Y_{pred}$ 하나만을 만들어낸다. 당연히 이 예측이 우리가 모르는 실제 정답 $Y_{test}$일 확률은 모델 정확도에 따라 80%가되며, 반대로 말하면 오차율은 20%가 된다.
> * 하지만 우리는 사용자가 직접 설정한 목표 오차율 $\alpha$에 맞춰 이 오차를 능동적으로 줄이고 싶다.
> * 모델을 튜닝시킬 수는 없는 이 상황에서 우리가 할 수 있는 유일한 해결책은, 모델의 예측 확률 중 적당히 높은 상위 후보들을 하나가 아니라 여러개 (Top-K개) 묶어서 출력하고 '이 Top-K안에 정답이 있을 확률은 $1-\alpha$입니다'.라고 하는 것이다.
> * 즉, 1등 예측인 $Y_{pred}$를 포함하여 그 다음으로 높은 $Y_{pred-2}, \cdots, Y_{pred-K}$등을 묶어내고, 이 예측 집합을 $\hat{\mathcal{C}}(X_{test})$라고 부르자. 마치 Classification 문제에서 말하는 Top-K 성능이 정답률을 높이는 것과 비슷한 뉘앙스다.) 이렇게 묶음으로 예측을 내놓으면, 실제 정답 $Y_{test}$가 $\hat{\mathcal{C}}_{test}$ 안에 들어갈 확률은 단일 예측일 때보다 당연히 높아질 것이다.
>   
> ### 3. CP의 도입: 기준선 ( $\hat{q}$ )찾기
> * 여기서 발생하는 가장 중요한 문제는 "**우리가 원하는 목표 오차율 $\alpha$를 맞추려면, 이 K를 도대체 어떤 기준으로, 어떻게 계산하여 늘리거나 줄일 것이가?**"이다. (CP는 K를 고정하지 않고 난이도에 따라 유동적으로 조절한다. 구체적으로는 일반적으로 고정된 $\hat{q}$로 K를 결정한다.)
> * 이를 수학적으로 엄밀하게 계산하는 후처리 작업이 바로 Conformal Prediction이다.
> * 그 기준이라는 것은 모델이 학습 시 본 적 없는 별도의 Calibration Dataset으로 계산된 정답과 예측 간의 오차에서 나오며, 이 오차들은 분위수 연산을 통해 절대적인 커트라인을 구하게 된다.
> 
>### 4. Calibration 단계
>* 주어진 Calibration Data $X_i,\,i\in[n]$에 대한 실제 정답을 $Y_i$라고 하자. ($n$은 calibration dataset 크기)
>* 모델이 이 정답 $Y_i$와 얼마나 다르게 예측했는지 그 불일치 정도에 대한 정량적인 오차 값을 $s_i$라고 하자. 이를 비순응도 점수(Nonconformity score)라고 부르며, 일반적으로 "$1 - \mathbb{P}(Y_i=\hat{f}(X_i))$"로 계산된다. 즉, 모델이 정답을 헷갈려 할수록 $s_i$ 값을 커진다.
>* 모든 $n$개의 Calibration Dataset에 대해 이 오차 점수 $s_1, \ldots, s_n$을 전부 계산하고 오름차순으로 정렬해 보자.
>$$s_1, \ldots, s_n$$
>* 이 길이 $n$짜리 데이터에서 하위 $1 - \alpha$ 지점에 대한 $s_i$ 값을 threshold $\hat{q}$라고 하자.
>* 이때 수식적으로는 유한한 데이터 $n$개와 미래의 테스트 데이터 1개가 이루는 통계적 틈(모분산 추정 시의 베셀의 보정과 유사한 맥락)을 보완하기 위해, 단순한 $1-\alpha$가 아닌 약간의 보정 계수가 추가되어 다음과 같이 계산된다.
>$$\hat{q}=Quantile(s_1,\ldots, s_n; \dfrac{(n+1)(1-\alpha)}{n})$$
>* 그리고 이렇게 구한 $\hat{q}$를 앞으로 절대 변하지 않은 Threshold로 잡는다. (단 이 불변성은 distribution이 변하지 않는다는 가정 하에 성립된다.)
>
>### 5. Test 단계
>* 이제 우리는 Threahold인 $\hat{q}$를 가지고 있다. 앞서 말한 새로운 이미지 $X_{test}$가 들어왔을 때, 모델이 예측할 수 있는 가능한 모든 후보 label ($Y_{pred-1}, \ldots, Y_{pred-L}$, $L$은 class 개수)을 임시 정답이라고 가정하고, 그에 대한 가상의 오차 점수 $s_{pred-1},\ldots,s_{pred-L}$를 전부 계산해 본다.
>* 여기서 우리가 Calibration Dataset에서 얻은 Threshold $\hat{q}$보다 작거나 같은 오차 점수를 통과한 예측 labels만 싹 다 모아 하나의 예측 집합 $\mathbb{C}(X_{test})$를 구성한다.
>### [최종 결론]
>* 이러면, Calibration 데이터와 Test 데이터의 분포가 같다는 전제(i.i.d.) 하에, 우리가 모르는 실제 정답 $Y_{test}$가 최종 예측 집합 ($\mathbb{C}(X_{test}))$ 안에 무사히 들어갈 확률이 최소 "$1-\alpha$"이상임이 수학적으로 보장된다.
>### [예시]
>* 모델의 예측 값이 "강아지"일 때, 이게 진짜 강아지일 확률이 80% (O)
>* 모델의 예측 값을 ["강아지", "늑대"]일 때, 이 안에 정답이 있을 확률이 $1-\alpha$. (X. 이렇게 해석하면 안 됨)
>* 모델이 새로운 이미지를 받고, 위의 규칙에 따라 $\mathcal{C}(X_{test})을 만들어내든, 그 집합들 안에 정답이 있을 확률은 $1-\alpha$에 수렴한다. (O) 즉, 부분집합에서는 틀리고 모집합으로 보면 맞다.


> [!PDF|] [[A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification.pdf#page=4&selection=249,0,277,1|A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification, p.4]]
> > $$ \mathcal{C}(X_{test}) = \{y : \hat{f} (X_{test})_y\ge 1 − \hat{q}\}$$
> 모든 가능한 label($y$)중, 해당 부등식을 만족하는 label들을 집합 $\mathcal{C}$라고 정의.

> [!PDF|] [[A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification.pdf#page=5&selection=49,0,81,61|A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification, p.5]]
> > With an eye towards generalization, let us review in detail what happened in our classification problem. To begin, we were handed a model that had an inbuilt, but heuristic, notion of uncertainty: softmax outputs. The softmax outputs attempted to measure the conditional probability of each class; in other words, the jth entry of the softmax vector estimated P(Y = j | X = x), the probability of class j conditionally on an input image x. However, we had no guarantee that the softmax outputs were any good; they may have been arbitrarily overfit or otherwise untrustworthy. Therefore, instead of taking the softmax outputs at face value, we used the holdout set to adjust for their deficiencie
> 
> Face value 즉, 모델이 출력한 Softmax가 overfitting인지 underfitting인지 모르기에 그대로 믿는 것은 위험이 따른다. 따라서, "학습에 전혀 관려하지 않은 새로운 데이터 즉, Calibration dataset"이 반드시 필요한다.