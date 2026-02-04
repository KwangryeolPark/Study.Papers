#timeseries #representation-learning #contrastive-learning

> [!PDF|노트] [[(AutoTCL) PARAMETRIC AUGMENTATION FOR TIME SERIES CONTRASTIVE LEARNING.pdf#page=7&selection=201,0,204,86&color=노트|(AutoTCL) PARAMETRIC AUGMENTATION FOR TIME SERIES CONTRASTIVE LEARNING, p.7]]
> > We follow CoST (Woo et al., 2022) network architecture. A multi-layer dilated CNN module is used for the backbone and we remove the seasonal feature disentangler module
> 
> Dilated CNN을 backbone으로 사용했다고는 하지만 이에 종속되는 방법론은 아님.

> [!PDF|노트] [[(AutoTCL) PARAMETRIC AUGMENTATION FOR TIME SERIES CONTRASTIVE LEARNING.pdf#page=7&selection=39,2,75,35&color=노트|(AutoTCL) PARAMETRIC AUGMENTATION FOR TIME SERIES CONTRASTIVE LEARNING, p.7]]
> > Their mask values h(x) a and h(x) p should be similar, compared to another point n that is far away from a, whose mask value is denoted by h(x) n . Formally, we have the following triplet loss.
> 
> $h_a, h_p, h_n$은 문맥 상으로 window가 아니라 하나의 instance 내에 하나의 시점을 가리킨다(scalar).

