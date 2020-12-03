# mitbih-arrhythmia dataset을 이용한 비트(Superclass), 리듬 타입 정리(Deep Learning 활용)


	2020 산학협력 "MIT-BIH ArrhyThmia Dataset을 활용한 심장질환 분류모델"

## 2) 4가지 Rhythm Type Classifier 개발

분석 모델 : RandomForest & Decision Tree in Python using Colab

### 2-1) N, A, V, /, L, R 대상 1 - 02_Rhythm_Type_Classifier_ML.ipynb

목적 :  4가지 Rhythm Type 증상에 대한 특성 분석 + 특성에 맞는 feature 추출, 분류에 적합한 모델 적용 및 개발

ML 적용 이유 : 각 리듭 타입별 존재하는 샘플 갯수가 1개에서 530개까지 존재하며, DL을 적용시키기엔 각 리듬별 패턴 파악을 위한 샘플 갯수가 충분하지 않다고 판단

#### preprocessing)

* 원 데이터로부터, 각 리듬별 'count'(=한 리듬타입 안에 찍힌 심박수 값의 총 개수), 'R_count', 'R_mean', 'R_count_per_beat'(=R_cnt/beat개수), 'R_count_per_sig'(=R_cnt/count)에 대한 추가 정보와 각 리듬타입이 존재하는 비율('N', 'R', '[', ... etc)에 대한 데이터 생성

/* (시행착오)

* 해석 용이성을 위해 변수 차원을 줄이기 위한 PCA, t-SNE 적용 ==> 새로운 변수들에 대한 설명력들이 부족 ==> 적용 X

*/

* Random Forest Model 1 )


* Result) Mean Accuracy = 97.1%, Mean F1 score = 97.1%, 
	Confusion matrix = 
	- [[ 51   4   0   0]  - (B
	-  [  0 133   0   0]  - (N
	-  [  0   1   5   1]  - (SVTA
	-  [  0   0   0  15]] - (VT



* Decision Tree 2 )


* Result) Mean Accuracy = 94.8%, Mean F1 score = 94.9%, 
	Confusion matrix = 
	- [[ 48   7   0   0]  - (B
	-  [  1 132   0   0]  - (N
	-  [  0   2   5   0]  - (SVTA
	-  [  0   1   0  14]] - (VT
 
 
 
 
## 2-2) 4가지 리듬별 특성 정리 - ML_feature.pdf

* (B
	- 'V' beat 비율 mid
	- 'N' beat 비율 low
	- '+' beat 비율 very low
* (N
	- 'N' beat 비율 high
* (SVTA
	- 'A' beat 비율 high
	- '+' beat 비율 mid
* (VT
	- 'V' beat 비율 high


