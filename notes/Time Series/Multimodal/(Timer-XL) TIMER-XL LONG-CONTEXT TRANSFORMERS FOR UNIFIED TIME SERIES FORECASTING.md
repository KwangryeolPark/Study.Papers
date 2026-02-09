> [!PDF|yellow] [[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=3&selection=4,87,5,24&color=yellow|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.3]]
> > Among them, decoder-only Transformer
> 
> Encoder only와 Decoder only의 차이는 정보를 처리하는 방식과 예측 방식에 있다.
> * Encoder 기반: #encoder
> 	* 양방향으로 데이터를 처리하는 경향 존재(즉, Attention 모듈에서 모든 토큰을 한 번에 계산).
> 	* 입력된 전체 시퀀스를 한 번에 보고, 모든 토큰이 서로를 참조한다.
> 	* 입력 윈도우를 받아 한 번에 고정된 길이의 미래를 예측.
> 	* 전체 문맥을 파악하여 특징을 추출하는 데 강점이 있다.
> * Decoder 기반: #decoder
> 	* 단방향이며 인과적으로 데이터를 처리.
> 	* 현재 시점의 토큰은 오직 과거의 토큰들만 참조할 수 있다. 즉, 인과적으로 데이터를 처리하며, Masked Attention 방식.
> 	* 다음 토큰을 하나씩 순차적으로 예측하는 Autoregressive 방식을 사용한다.
> 	* 다양한 길이의 유연한 입력과 출력을 처리할 수 있으며, 생성형 모델에 적합.
> 	#모델구조
> 

> [!PDF|의문점] [[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=3&selection=150,0,151,1&color=의문점|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.3]]
> > $TP$
> 
> Q: 여기서 TP는 $T\times P$를 의미하는 건가.? #의문점
> A: 
> 
> Thinking: $i$가 sequence index가 아니라 patch index이고, $P$가 patch length라면?

> [!PDF|답변] [[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=4&selection=96,0,159,3|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.4]]
> > $P (X) = NY m=1 TY i=1 p(xm,i+1|x:,≤i) = NY m=1 TY i=1 p(xm,i+1|x1,≤i, . . . , xN,≤i)$. 
> 
> Q. 여기서 모든 variables을 독립적으로 처리하는 것인가 아니면 수식적으로 동시에 처리하는 것인가. 
> A. 
> > [!PDF|] [[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=4&selection=169,78,170,52&color=답변|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.4]]
> > while incorporating exogenous variable correlations from other sequences
> > * 모든 변수 간의 상관관계를 활용하여 토큰을 예측하는 형식 
> > * 첫 항의 조건부 항을 보면 $\mathbf{x}_{:, \le i}$ 형식으로 돼 있다. 즉, $m$번째 variate를 구하기 위해서 모든 variates($:$)가 동원되는 방식.
> 



> > [!PDF|research gap] [[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=4&selection=221,0,223,70&color=research gap|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.4]]
> > Position embedding has not been sufficiently explored in time-series Transformers. To avoid inherent permutation-invariance of self-attention, positional embedding is required to reflect the chronological order of tokens on the temporal dimension
> 
> #research-gap 
> 시계열에서 Multivariate을 고려한 position embedding은 충분히 연구되지 않았.



> > ([[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=4&selection=225,57,225,79&color=용어 정리|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.4]])
> permutation-equivalent
> Permutation Equivalent는 입력 데이터의 순서를 바꾸면 출력 데이터의 순서도 바뀌는 것을 의미.
> $$f(\pi(x))=\pi(f(x))$$ 

> [!PDF|research gap] [[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=4&selection=231,0,285,1&color=research gap|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.4]]
> > Amn,ij = h⊤ m,iWq Rθ,i−j W⊤ k hn,j + u · 1(m = n) + v · 1(m̸ = n),
> 
> #research-gap RoPE는 1D 데이터의 상대적 위치를 나타내는 건데, 이걸 2D로 바꿀 수는 없나?
> 변수들을 learnable parameters ($u, v$)만으로 분리하는 것이 가능한가? 이게 permutation equivalent인가?

> ([[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=4&selection=362,44,380,1&color=의문점|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.4]])
> To predict its next token, its representation h should be exactly dependent on the tokens-{1, 2, 4, 5}.
> Q. 왜 1, 2, 4, 5지?
> A. 이 문장에서는 그림 2의 `Time Series A`뿐만 아니라 `Time Series B`까지 얘기하는 것으로 추측. 즉, `Time Series A`에서 다음 토큰 (3)를 예측하기 위해서는 $h$가 (1, 2) 토큰에 대한 정보를 가지고 있어야 하고, 이는 `Time Series B`에서도 마찬가지로 동작.


> ([[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=5&selection=194,0,194,8&color=노트|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.5]])
> Figure 2
> * 중앙 (Multivariate) 해석: A라는 변수와 B라는 변수가 서로 간의 의존성이 있을 때의 $\mathcal{C}$의 형태를 보여준다.
> * 오른쪽 (with Covariate B) 해석: B라는 변수가 A라는 변수에 단방향으로 영향을 줄 때를 보여준다. 
> 	* 그림을 보면, 우측 상단 초록색에서 
> 		* Token 1은 Token 4에 영향을 받는다.
> 		* Token 2는 Token 4, 5에 영향을 받는다.
> 		* Token 3은 Token 4, 5, 6에 영향을 받는다.
> 	* 하지만 좌측 하단 검정색에서
> 		* Token 4 ~ 6은 A의 어떠한 Tokens에서도 영향을 받지 않는다.
> 	* 예를 들어, B가 날씨고 A가 전량인 상황.
> * Time XL에서는 이러한 의존성을 나타내는 $\mathcal{C}$ matrix를 사용자 정의에 맡긴다.
> > ([[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=5&selection=233,35,243,55&color=노트|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.5]])
> 1) formulate the customized variable dependency as C and (2) optimize the model using the supervision of target variables. An example (target-A-covariate-B) of TimeAttention is illustrated on the right of Figure 2. 


> [!PDF|노트] [[(Timer-XL) TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING.pdf#page=1&selection=2,0,22,10&color=노트|TIMER-XL LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING, p.1]]
> > TIMER-XL: LONG-CONTEXT TRANSFORMERS FOR UNIFIED TIME SERIES FORECASTING
> 
> 
> Time Attention 부분이 독창적이었으나 크게 다가오는 것은 없음.



#timeseries
#multimodal
