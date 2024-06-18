# TT-image-model

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

|   |original |10|50|100|150|
|---|---------|---|---|---|---|
|compression ratio|1|0.052|0.260|0.521|0.781|
|eval_loss|0.773|0.619|0.643|0.642|0.861|
|eval_acc|86.0|84.75|86.0|85.25|83.5|

