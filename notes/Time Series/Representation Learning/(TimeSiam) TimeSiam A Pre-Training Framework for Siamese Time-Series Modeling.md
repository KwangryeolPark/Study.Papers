#timeseries #representation-learning #model-agnostic 

> [!PDF|노트] [[(TimeSiam) TimeSiam A Pre-Training Framework for Siamese Time-Series Modeling.pdf#page=1&selection=0,0,0,67&color=노트|(TimeSiam) TimeSiam A Pre-Training Framework for Siamese Time-Series Modeling, p.1]]
> > TimeSiam: A Pre-Training Framework for Siamese Time-Series Modeling
> 
> ### 요약
> 1. Pre-training 매커니즘: 기존의 마스킹 기법과 달리, 시계열의 시간적 상관관계를 학습하기 위해 Siamese 네트워크 구조를 투입.
> 	* 입력: 과거 데이터 ($x_{past}$)와 마스킹된 현재 데이터($\tilde{x}_{curr}$)을 동일한 backbone encoder에 투입.
> 	* 복원 과정: Backbone을 통과한 출력값 중, 과거 시점의 잠재 표현을 Decoder의 Key와 Value로, 현재 시점의 잠재 표현을 Query로 사용하여 Cross-Attention을 수행. 그 결과 값과 마스킹 안 된 현재 데이터 간의 거리 좁히는 방식.
> 	* 목표: 이를 통해 과거 정보를 참조하여 현재의 마스킹된 부분을 복원하며 학습.
> 2. Model-Agnostic 여부에 대한 비판: 논문은 다양한 모델에 적용 가능하다고 주장하나, 구현 관점에서는 완전한 Model-Agnostic이라고 보기 어려움.
> 	* 이유: TimeSiam의 핵심인 Lineage Embedding을 적용하기 위해서는 Backbone 모델의 Embedding Layer와 Encoder Layer 사이에 개입하여 벡터 덧셈 연산을 수행해야 함.
> 	* 한계: 따라서 Backbone 모델을 black-box처럼 호출하여 사용할 수 없으며, 모델 내부 구조를 수정해야 함.
> 3. Inference 및 Fine-tuning 시 연산향 이류: Fine-tuning 및 inference 단계에서 성능 극대화를 위해 Fixed-Input-Multiple-Lineages 전략을 사용하기에 연산 비용이 증가.
> 	* 작동: 하나의 입력 데이터에 대해 $N$개의 서로 다른 Lineage Embedding을 각각 적용하여 인코딩한 후, 그 결과들을 Average(Ensemble)하여 최종 예측값을 도출.
> 	* 비용: 이 과정은 단일 모델 대비 메모리 사용량과 연산량을 정확히 $N$배 증가시키기에, 실시간성이 중요한 환경에서는 상당한 overheadd가 발생.
