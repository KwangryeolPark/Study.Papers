> [!PDF|답변] [[(Time-VLM) Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting.pdf#page=1&selection=31,39,36,27&color=의문점|Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting, p.1]]
> > While text provides contextual understanding, it often lacks fine-grained temporal details. Conversely, vision captures intricate temporal patterns but lacks semantic context, limiting the complementary potential of these modalities
> 
> 이 주장에 의하면 Text와 Vision에는 서로 다른 장점이 존재한다.
> * Text: 문맥적인 정보를 이해하는데 도움이 되지만, 세밀한 정보를 표현하지는 못한다.
> * Vision: Text와 반대.
> Q. 시계열 데이터 특성 자체에는 저런 장점들이 없나?
> A. >
> [!PDF|의문점] [[(Time-VLM) Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting.pdf#page=2&selection=65,0,89,51&color=답변|Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting, p.2]]
> > (1) a Retrieval-Augmented Learner that processes raw time series data through patch-based feature extraction and memory bank interactions to generate enriched temporal representations, capturing both local and global dependencies; (2) a Vision-Augmented Learner that adaptively transforms time series into images using multi-scale convolution, frequency encoding, and periodic encoding, preserving both fine-grained details and high-level structures; and (3) a TextAugmented Learner that generates rich textual context (e.g., statistics and dataset descriptions) to complement the visual representations. These modules collaborate with VLMs to integrate temporal, visual, and textual modalities, producing accurate forecasts through a fine-tuned predictor.
> 
> 

> [!PDF|답변] [[(Time-VLM) Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting.pdf#page=1&selection=52,0,53,13&color=의문점|Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting, p.1]]
> > These components collaborate with frozen pretrained VLMs 
> 
> 앞서 세 개의 Learner인 Retrieval-Augmented, Vision-Augmented, Text-Augmented Learners를 소개했는데,
> Q. 이 frozen pre-trained VLMs는 Learner가 아닌 또 다른 모델인가?
> A.
> > [!PDF|의문점] [[(Time-VLM) Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting.pdf#page=3&selection=480,0,499,47&color=답변|Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting, p.3]]
> > • Vision-Augmented Learner (VAL): Transforms time series into informative three-channel images through multiscale convolutions, frequency and periodic encoding. The images are processed by a frozen VLM vision encoder to extract hierarchical visual features, capturing both finegrained details and high-level temporal patterns. • Text-Augmented Learner (TAL): Generates contextual textual prompts for input time series, including statistical features (e.g., mean, variance, trends), domain-specific context (e.g., electricity consumption patterns), and image descriptions. These prompts are encoded by a frozen VLM text encoder to produce textual embeddings.
> 

> [!PDF|의문점] [[(Time-VLM) Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting.pdf#page=3&selection=565,0,573,1&color=의문점|Time-VLM Exploring Multimodal Vision-Language Models for Augmented Time Series Forecasting, p.3]]
> > RB×Np×dmodel
> 
> A. $D$ 차원이 $d_{model}$ 차원으로 변한 건가.? 이러면 채널 정보를 섞는 것으로 이해할 수 있는데. 아니면 $E_p$는 단채널 데이터를 표현한 것일 수도. #의문점 


#timeseries
#multimodal
