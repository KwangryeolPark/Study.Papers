> [!PDF|답변] [[How Can Time Series Analysis Benefit From Multiple Modalities A Survey and Outlook.pdf#page=5&selection=222,0,223,48&color=의문점|How Can Time Series Analysis Benefit From Multiple Modalities A Survey and Outlook, p.5]]
> > Task instructions help models, especially LLMs, perform forecasting tasks better.
> 
> Q. Task Instruction이 어떻게 forecasting tasks를 더 잘 할 수 있게 한다는 거지?
> A. Text와 같은 외생 변수의 경우 모델로 하여금 사고의 전환을 유발시킨다. 예를 들어, 같은 시계열 데이터라도 static text에 "Current data is electricity dataset collected from Mon. to Sat."이라고 주어지면 모델은 electricity dataset에 대한 지식을 활성화 한다. 같은 맥락으로, "현 연준이 금리를 0.5%p 인하했다."라는 dynamic text가 들어오면 모델은 현 데이터가 일반적인 데이터가 아닌, 단기적인 변화라고 인식하고 그에 맞춰 "금리 0.5%p 인하"와 관련된 추론을 시작한다.
> > [!PDF|의문점] [[How Can Time Series Analysis Benefit From Multiple Modalities A Survey and Outlook.pdf#page=6&selection=218,22,226,3&color=답변|How Can Time Series Analysis Benefit From Multiple Modalities A Survey and Outlook, p.6]]
> > Additional factors, such as policies and social sentiment, typically represented in textual form, can significantly influence financial data and its dynamics [ 101, 197]. 
> 
> 
> Q. Text의 의의는 알겠으나, 실질적으로 모델이 Text를 잘 활용한다는 지표는? 단순히 성능이 아닌, 해석 가능성. #의문점 


> [!PDF|의문점] [[How Can Time Series Analysis Benefit From Multiple Modalities A Survey and Outlook.pdf#page=6&selection=226,3,228,66&color=의문점|How Can Time Series Analysis Benefit From Multiple Modalities A Survey and Outlook, p.6]]
> > Existing studies have demonstrated the benefit of effectively leveraging this textual information for better financial analysis with the numerical data.
> 
> Q. 주식 데이터의 경우, 완충이라는 개념이 존재한다. 처음 새로운 경험(관세 등)을 했을 때는 시장의 반응이 뜨겁지만, 유사한 event가 다시 발현(관세 등)한다면 사람들은 이미 과거의 경험을 통해 미리 대응을 할 것이다. 즉, 같은 event라도 나중에 발현된 event는 영향이 적은데 이것을 text만으로 처리할 수 있는가? #의문점 

> [!PDF|노트] [[How Can Time Series Analysis Benefit From Multiple Modalities A Survey and Outlook.pdf#page=8&selection=30,4,32,19&color=노트|How Can Time Series Analysis Benefit From Multiple Modalities A Survey and Outlook, p.8]]
> > Local retrieval, also known as feature understanding, focuses on detecting whether the feature type specified in the query exists in the time series.
> 
> 일종의 Segmentation with text query. Text를 입력으로 주면, 그에 맞는 형태를 time series에서 찾아내는 것. 예를 들어 "상승장은 어디지?"라고 하면 그에 맞는 부분을 알려줌.