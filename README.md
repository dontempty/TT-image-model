# TT-image-model
### 개 고양이 이미지를 분류하는 문제입니다.  
### CNN 모델을 다양한 종류의 이미지로 훈련시키고 성능을 비교합니다.

데이터 출처: <https://www.kaggle.com/c/dogs-vs-cats/data>  

원래 관련 데이터를 올리려고 했지만 용량이 너무 커서 코드만 업로드 합니다.

TT Decomposition을 이용해서 이미지를 rank를 달리하여 분해합니다.  
rank = 10, 50, 100, 150  
rank 변화에 따른 모델의 성능을 비교합니다.  

학습 loss와 accuracy입니다.
![train loss](https://github.com/dontempty/TT-image-model/assets/155451345/95a9c8ed-6d85-4de0-a62c-440bf53f62e7)
![train accuracies](https://github.com/dontempty/TT-image-model/assets/155451345/88b01db4-9d35-43b3-a007-4c8c91e2fa29)  

compression ratio는 배열의 크기를 측정했습니다.  

$compression ratio = \frac{compressed}{original}$

12500개 데이터 중 train: 9000, validation: 800, test: 200  
test 데이터는 원본 이미지를 사용했습니다.

|   |original |10|50|100|150|
|---|---------|---|---|---|---|
|compression ratio|1|0.052|0.260|0.521|0.781|
|eval_loss|0.773|0.619|0.643|0.642|0.861|
|eval_acc|86.0|84.75|86.0|85.25|83.5|

# 결론
compresion ratio에 따른 성능에는 큰 변화가 없습니다. 
단순한 개 고양이 분류 문제에서는 압축된 이미지를 활용한느 것이 효율적인 것 같습니다.

