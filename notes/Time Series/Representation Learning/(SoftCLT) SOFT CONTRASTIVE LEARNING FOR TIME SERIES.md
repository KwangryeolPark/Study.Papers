> [!PDF|노트] [[(SoftCLT) SOFT CONTRASTIVE LEARNING FOR TIME SERIES.pdf#page=1&selection=30,33,32,84&color=노트|(SoftCLT) SOFT CONTRASTIVE LEARNING FOR TIME SERIES, p.1]]
> > However, contrasting similar time series instances or values from adjacent timestamps within a time series leads to ignore their inherent correlations, which results in deteriorating the quality of learned representations.
> 
> oo

> [!PDF|research gap] [[(SoftCLT) SOFT CONTRASTIVE LEARNING FOR TIME SERIES.pdf#page=4&selection=228,0,252,1&color=research gap|(SoftCLT) SOFT CONTRASTIVE LEARNING FOR TIME SERIES, p.4]]
> > i,t) I = − log pI ((i, i + N ), t)
> 
> SoftCLT의 단점은, 증강된 서로 다른 view는 같은 것으로 취급하는 것. 즉, 여전히 시차가 존재해도 같은 데이터로 취급. -> Hard Positive #research-gap 
>

> [!PDF|research gap] [[(SoftCLT) SOFT CONTRASTIVE LEARNING FOR TIME SERIES.pdf#page=4&selection=357,0,383,1&color=research gap|(SoftCLT) SOFT CONTRASTIVE LEARNING FOR TIME SERIES, p.4]]
> > wT (t, t′) = 2 · σ (−τT · |t − t′|)
> 
> 여기서도 마찬가지. #research-gap 

> [!PDF|노트] [[(SoftCLT) SOFT CONTRASTIVE LEARNING FOR TIME SERIES.pdf#page=1&selection=2,0,15,5&color=노트|(SoftCLT) SOFT CONTRASTIVE LEARNING FOR TIME SERIES, p.1]]
> > SOFT CONTRASTIVE LEARNING FOR TIME SERIES
> 
> 이 논문은 Contrastive Learning의 Hard Negative 방식을 지적하며 negative pair를 단순히 멀게하는 것이 아닌, 적당한 거리로 벌리는 것을 수행한다.
> 이를 위해 instance wise loss와 temporal loss를 제시한다. instance wise loss에서 사용되는 거리란 모든 데이터 간의 pair의 DTW의 min-max normalized를 의미. 반면 temporal loss에서 사용되는 거리란 단순히 time index를 사용한다.
> 이 방법론은 Hard Negative 방식을 해소하는데는 효과적이었지만, 여전히 Hard Positive를 다루고 있다.

#timeseries #contrastive-learning #model-agnostic #representation-learning 