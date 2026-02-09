> [!PDF|의문점] [[(TimeXL) TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop.pdf#page=1&selection=38,71,39,5&color=의문점|TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop, p.1]]
> > prototypebased
> 
> Q. 여기서 말하는 Prototype based란? 
> A. :
> [!PDF|용어 정리] [[(TimeXL) TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop.pdf#page=4&selection=298,0,361,69&color=용어 정리|TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop, p.4]]
> > P (c) time ∈ Rk×h, P (c) text ∈ Rk′×h′ so that each prototype p(c) i ∈ Rh (time series) or p′(c) i ∈ Rh′ (text) resides in the same feature space as the relevant encoder outputs. For an input sequence, we measure the similarity between each prototype and the most relevant segment in the corresponding modality
> 
> 

> [!PDF|의문점] [[(TimeXL) TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop.pdf#page=1&selection=39,18,39,26&color=의문점|TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop, p.1]]
> > encoder 
> 
> Q. 왜 Encoder를 사용한 거지? #모델구조 #encoder #의문점 

> [!PDF|의문점] [[(TimeXL) TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop.pdf#page=1&selection=40,41,40,66&color=의문점|TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop, p.1]]
> > interpretable explanations
> 
> Q. 어떻게 해석 가능성을 제공하는 거지? #의문점 

> [!PDF|용어 정리] [[(TimeXL) TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop.pdf#page=1&selection=42,41,42,62&color=용어 정리|TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop, p.1]]
> > case-based rationales 
> 설명 가능성 기능을 제공하는데 있어, 텍스트 데이터에서 추론의 근거(사례)를 제공하는 것을 의미.

> [!PDF|] [[(TimeXL) TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop.pdf#page=1&selection=89,64,89,80|TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop, p.1]]
> > temporal factors
> 
> 갑작스럽거나 일시적인 현상들을 의미

> [!PDF|용어 정리] [[(TimeXL) TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop.pdf#page=1&selection=129,48,129,60&color=용어 정리|TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop, p.1]]
> > high-stakes 
> 
> 막대한 금전적 손실이나 생명에 심각한 영향을 미칠 수 있는 중대한 분야.
> ex) 금융, 의료

> [!PDF|용어 정리] [[(TimeXL) TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop.pdf#page=2&selection=193,30,193,37&color=용어 정리|TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop, p.2]]
> > prowess
> 
> 높은 전문성 있는. 매우 강력하고 우수한

> [!PDF|노트] [[(TimeXL) TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop.pdf#page=1&selection=0,0,1,31&color=노트|TimeXL Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop, p.1]]
> > TimeXL: Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop
> 
> 이 논문은 뛰어난 성능에도 불구하고 ICML 2025에서 Reject되었다. 주된 이유는, 각각의 모델들의 성능 기여도에 대한 분석이 없다는 것. 리뷰어들은 누가 진짜 성능에 기여했는지를 궁금해 했으며, 단순히 Encoder의 성능이 강력해서 성능이 좋아진 것 아니냐는 의문을 남겼다.
> 또한 LLM 세 개를 사용했음에도, regression 성능 (RMSE)이 `4.198` -> `4.161`로 겨우 `0.9%p`정도의 성능 향상만이 있었다.
>


#timeseries
#multimodal
