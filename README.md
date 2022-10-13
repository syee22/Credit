# Credit
<img width="477" alt="credit12" src="https://user-images.githubusercontent.com/108845232/195582715-82b6a511-a4ae-40ad-bb86-54839d3720da.png">
## 신용카드 사용자의 신용등급을 분류 예측하는 알고리즘<br>
raw data 의 변수
<img width="682" alt="화면 캡처 2022-09-21 163816" src="https://user-images.githubusercontent.com/108845232/195587372-302615b0-817b-47fe-be66-a23724fce613.png">
** Target 변수 : Credit (0,1,2) 0 : 신용도 좋음 1 : 보통 2: 신용도 나쁨 <br><br>
# 파생변수 생성
<img width="680" alt="파생변수1" src="https://user-images.githubusercontent.com/108845232/195587646-1cc24994-5782-49ac-99bc-f29bac97b954.png">
<img width="677" alt="파생변수2" src="https://user-images.githubusercontent.com/108845232/195587657-0da7e19d-21f2-4067-9060-f990c9dc8b15.png">


# 알고리즘 별로 변수들의 전처리를 다양하게 적용하여 성능을 비교한 결과<br>
# GBM
<img width="513" alt="GBM" src="https://user-images.githubusercontent.com/108845232/195584078-c42edc49-691f-4416-856f-9960969c69b4.png">
# RandomForest
<img width="544" alt="RF" src="https://user-images.githubusercontent.com/108845232/195584172-c8396432-3756-4019-8dd7-6313d7be34ca.png">
# DecisonTree
<img width="538" alt="DT" src="https://user-images.githubusercontent.com/108845232/195584200-14c978fd-0758-468b-b85a-51b72fde36a3.png">
# XGBClassifier
<img width="510" alt="XGB" src="https://user-images.githubusercontent.com/108845232/195584236-9e85283b-91aa-41b4-be05-598951b56303.png">
# LGBMClassifier
<img width="507" alt="LGBM" src="https://user-images.githubusercontent.com/108845232/195584270-58eef2dc-6960-4067-ac58-91b6027ff961.png">
# Soft Voting
<img width="424" alt="softVoting" src="https://user-images.githubusercontent.com/108845232/195584311-a4826981-04f4-4052-9bfe-9ddd640c6951.png">
<br>
<해석><br>
보통 분류예측에서는 모델의 정확도로 성능을 평가하지만 logloss를 이용하여 어느정도의 확신을 가지고 분류예측을 수행했는지를 함께 분석하여 얼마나 잘 예측되었는지를 평가할 수 있다.
이때 정확도 기준으로 아래와 같은 모델이 최고성능을 보였다고 할 수 있다.<br>
<img width="415" alt="정확도기준" src="https://user-images.githubusercontent.com/108845232/195586203-412714f3-2d70-4dbe-ae83-7ab84ecfec6d.png"><br>

logloss 기준으로는 아래와 같은 모델이 선정되었으며 수치형데이터이지만 Income_total 즉 소득을 나타내는 변수를 로그변환을 해주었고, 나머지 수치형 변수 (income_total 관련 변수 제외)에 대해
StandardScaler를 이용하여 수치형변수를 정규화하였으며 범주형 변수에서는 LabelEncoding 을 이용해 전처리를 수행했을때 XGboost 의 최적하이퍼파라미터를 이용한 StratifiedKFold의
성능이 가장 좋았다.<br>
<img width="475" alt="로그로스기준" src="https://user-images.githubusercontent.com/108845232/195586287-f0e9c548-a145-45b5-9b72-539db75f17af.png"><br>
