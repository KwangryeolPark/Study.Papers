# Study.Papers

연구 논문을 주제별로 정리한 저장소입니다.

## 📚 Time Series

### 🔄 Multimodal

<details>
<summary><b>How Can Time Series Analysis Benefit From Multiple Modalities? A Survey and Outlook</b></summary>

**Links:** [PDF](papers/Time%20Series/Multimodal/How%20Can%20Time%20Series%20Analysis%20Benefit%20From%20Multiple%20Modalities%20A%20Survey%20and%20Outlook.pdf) | [Notes](notes/Time%20Series/Multimodal/How%20Can%20Time%20Series%20Analysis%20Benefit%20From%20Multiple%20Modalities%20A%20Survey%20and%20Outlook.md)

**설명:** 시계열 분석이 텍스트, 이미지, 오디오 등 다양한 모달리티와 결합하여 발전하는 Multiple Modalities For TSA 분야를 체계적으로 정리한 최초의 서베이 논문. TimeAsX (타 모달리티 파운데이션 모델 재사용), Time+X (멀티모달 확장), Time2X & X2Time (교차 모달리티 상호작용) 세 가지 핵심 접근 방식을 제시하며, 텍스트의 역할(Static/Dynamic Text)과 도메인별 특성, 그리고 이질적 모달리티 조합 처리의 한계를 다룬다.

**Tags:** `#timeseries` `#multimodal` `#survey`

</details>

<details>
<summary><b>TIMER-XL: LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING</b></summary>

**Links:** [PDF]((Timer-XL)%20TIMER-XL%20LONG-CONTEXT%20TRANSFORMERS%20FOR%20UNIFIED%20TIME%20SERIES%20FORECASTING.pdf) | [Notes]((Timer-XL)%20TIMER-XL%20LONG-CONTEXT%20TRANSFORMERS%20FOR%20UNIFIED%20TIME%20SERIES%20FORECASTING.md)

**설명:** Decoder-only Transformer 기반의 시계열 예측 모델로, 다변량 시계열 데이터에서 변수 간 의존성을 처리하기 위한 Time Attention 메커니즘을 제안. 사용자 정의 가능한 변수 의존성 행렬(C matrix)을 활용하여 covariate와 target 간의 관계를 명시적으로 모델링하며, 시계열에서 충분히 연구되지 않은 position embedding 문제를 다룬다.

**Tags:** `#timeseries` `#multimodal` `#transformer`

</details>

<details>
<summary><b>Time-VLM: Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting</b></summary>

**Links:** [PDF]((Time-VLM)%20Time-VLM%20Exploring%20Multimodal%20Vision-Language%20Models%20for%20Augmented%20Time%20Series%20Forecasting.pdf) | [Notes]((Time-VLM)%20Time-VLM%20Exploring%20Multimodal%20Vision-Language%20Models%20for%20Augmented%20Time%20Series%20Forecasting.md)

**설명:** Vision-Language Model을 시계열 예측에 활용하는 멀티모달 프레임워크. Retrieval-Augmented Learner(시계열 데이터 처리), Vision-Augmented Learner(시계열을 이미지로 변환), Text-Augmented Learner(통계적 특성과 도메인 정보를 텍스트로 생성)의 세 가지 모듈이 협력하여 시간적, 시각적, 텍스트 모달리티를 통합한다. Text는 문맥 이해에, Vision은 세밀한 temporal pattern 포착에 강점을 가진다.

**Tags:** `#timeseries` `#multimodal` `#vision-language-model`

</details>

<details>
<summary><b>TimeXL: Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop</b></summary>

**Links:** [PDF]((TimeXL)%20TimeXL%20Explainable%20Multi-modal%20Time%20Series%20Prediction%20with%20LLM-in-the-Loop.pdf) | [Notes]((TimeXL)%20TimeXL%20Explainable%20Multi-modal%20Time%20Series%20Prediction%20with%20LLM-in-the-Loop.md)

**설명:** Prototype 기반 encoder와 LLM을 활용하여 해석 가능한 멀티모달 시계열 예측을 제공하는 모델. Case-based rationales를 통해 예측에 대한 설명 가능성을 제공하며, 금융이나 의료 같은 high-stakes 분야에서 중요한 해석 가능성을 강조한다. ICML 2025에서 reject되었으며, 주된 피드백은 각 컴포넌트의 성능 기여도 분석 부족과 LLM 사용 대비 미미한 성능 향상(0.9%p)이었다.

**Tags:** `#timeseries` `#multimodal` `#explainability` `#llm`

</details>

<details>
<summary><b>XForecast: Evaluating Natural Language Explanations for Time Series Forecasting</b></summary>

**Links:** [PDF]((XForecast)%20XForecast%20Evaluating%20Natural%20Language%20Explanations%20for%20Time%20Series%20Forecasting.pdf) | [Notes]((XForecast)%20XForecast%20Evaluating%20Natural%20Language%20Explanations%20for%20Time%20Series%20Forecasting.md)

**설명:** 시계열 예측에서 자연어 설명(Natural Language Explanation)을 평가하는 방법론을 다룬 논문. Saliency maps와 같은 시각적 중요도 표현을 넘어 자연어로 예측 근거를 제공하는 방식을 탐구한다.

**Tags:** `#timeseries` `#multimodal` `#explainability`

*(읽지 않음)*

</details>

### 🎯 Representation Learning

<details>
<summary><b>(TimeSiam) TimeSiam: A Pre-Training Framework for Siamese Time-Series Modeling</b></summary>

**Links:** [PDF](papers/Time%20Series/Representation%20Learning/(TimeSiam)%20TimeSiam%20A%20Pre-Training%20Framework%20for%20Siamese%20Time-Series%20Modeling.pdf) | [Notes](notes/Time%20Series/Representation%20Learning/(TimeSiam)%20TimeSiam%20A%20Pre-Training%20Framework%20for%20Siamese%20Time-Series%20Modeling.md)

**설명:** Siamese 구조를 활용한 시계열 데이터의 사전 학습 프레임워크. Model-agnostic한 접근 방식을 제시한다.

**Tags:** `#timeseries` `#representation-learning` `#model-agnostic`

*(읽지 않음)*

</details>

<details>
<summary><b>(SoftCLT) SOFT CONTRASTIVE LEARNING FOR TIME SERIES</b></summary>

**Links:** [PDF](papers/Time%20Series/Representation%20Learning/(SoftCLT)%20SOFT%20CONTRASTIVE%20LEARNING%20FOR%20TIME%20SERIES.pdf) | [Notes](notes/Time%20Series/Representation%20Learning/(SoftCLT)%20SOFT%20CONTRASTIVE%20LEARNING%20FOR%20TIME%20SERIES.md)

**설명:** Contrastive Learning의 Hard Negative 방식을 개선한 논문. Negative pair를 무조건 멀게 하는 대신 적절한 거리로 분리하는 Soft Contrastive Learning을 제안한다. Instance-wise loss는 DTW(Dynamic Time Warping) 거리의 min-max normalized 값을, Temporal loss는 time index를 사용한다. Hard Negative 문제는 해결했으나 여전히 Hard Positive(증강된 다른 view를 동일하게 취급하는 문제)는 남아있다.

**Tags:** `#timeseries` `#contrastive-learning` `#model-agnostic` `#representation-learning`

</details>

<details>
<summary><b>(AutoTCL) PARAMETRIC AUGMENTATION FOR TIME SERIES CONTRASTIVE LEARNING</b></summary>

**Links:** [PDF](papers/Time%20Series/Representation%20Learning/(AutoTCL)%20PARAMETRIC%20AUGMENTATION%20FOR%20TIME%20SERIES%20CONTRASTIVE%20LEARNING.pdf) | [Notes](notes/Time%20Series/Representation%20Learning/(AutoTCL)%20PARAMETRIC%20AUGMENTATION%20FOR%20TIME%20SERIES%20CONTRASTIVE%20LEARNING.md)

**설명:** 기존의 고정된 augmentation 기법(Jittering, Scaling)이 시계열의 본질적 특성을 반영하지 못한다고 지적하며, 학습 가능한 Augmentation Network를 제안. 이 네트워크는 중요한 정보를 선택하는 마스크(h)와 scaling 변환 함수(g)를 생성하며, Latent Space에서 dropout 방식으로 augmentation을 수행한다. 정보 이론 관점에서 엔트로피가 높은 뷰를 생성하여 정보 이득을 극대화한다. 다만, 많은 loss와 hyper-parameter로 인해 사용이 복잡하다는 단점이 있다.

**Tags:** `#timeseries` `#representation-learning` `#contrastive-learning` `#model-agnostic`

</details>

---

**총 논문 수:** 8편 (읽은 논문: 6편, 읽지 않은 논문: 2편)
