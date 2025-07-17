# kaggle
kaggle ml,dl,llm,...

07.17 spaceship-titanic-reg1.ipynb - 전통적 ml을 통해 작성.  
데이터 출처 : https://www.kaggle.com/competitions/spaceship-titanic  
기술스택 : sklearn  
목적 : 'Transported' 예측  
요약 : 처음엔 모든 연속형 데이터를 bin, 범주형 데이터를 one-hotencoding 진행. -> logistic,xgb,lgb,logistic+xgb+lgb의 평균 블렌딩 --> 4개 모델 전부 결과가 비슷했음.  
따라서 다양한 비선형 피처를 생성해 추가 --> logistic에는 성능이 미세하게 감소했지만, xgb, lgb의 비선형 모델의 경우 피처가 미세하게 증가. --> 데이터가 비선형 패턴이 있는걸 학습.  
따라서 비선형 피처를 대거 추가, 공선성을 유발하는 피처들 제거, PCA로 차원 축소 진행 --> 역시 로지스틱의 경우엔 0.75에서 0.70으로 급격한 감소 but 비선형 모델의 경우엔 성능의 변화가 없었음.  
  결론 : 피처의 비선형성 반영은 충분히 했음. 추가적인 전략이 필요해 보임.  
