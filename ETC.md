## Long Tail Distribution  
* sample이 많은 class에 overfitting, 적은 class는 학습 잘안댐.  
  * Class imabalance problem  
> "Range Loss for Deep Face Recognition with Long-tail," ICCV 2017.  

-------------------------------------------------------
<br/>

## Classficiation Measure  
* True/False =  맞음/틀림 ---- Positive/Negative = 예측치  
* precision = 얼마나 안 틀림 ---- Recall = 얼마나 잘 찾음
> https://www.analyticsvidhya.com/blog  

-------------------------------------------------------
<br/>

## Linear Algebra  

* Eigen Value Decomposition
* Singular Value Decomposition
* PCA
* Covariance Matrix
* Jordan normal form
* FFT

-------------------------------------------------------
<br/>


## AutoML
* Nueral Architecture Searching
  * 학습과정에서 아키텍쳐를 선정하는 AutoML.
  * NAS with RL: 강화학습 기반으로 초기 많이 풀었었는데, 모델 성능을 보상, 서칭할 space (3x3 conv, skip, pool 등) 선정
  * AmeobaNet: 진화알고리즘 기반으로도 여러 모델 학습, 그중 최고 모델 선정, 비슷하게들 다시생성 (weight copy) 다시 학습
  * DARTS: 하나의 아키텍쳐에서 한 패스에 여러 연산 놓고 연산별 가중치 두고 학습하면서 가중치 높은 애들로만 구성하는 형식.
* Auto Augmentation
  * NAS랑 비슷한 역사로 흘러가는 듯.
  * 목적은 [데이터셋 - 아키텍처]에 적합한 arugmentation policy를 찾겠다.
  * AA: 강화학습으로 Policy 찾기.
  * PBT: PBT 알고리즘 기반, AmeobaNet이랑 비슷한 접근
  * Fast AA: 학습 모델 대상 valiate 과정에서 aug 적용해서 policy들 찾고 많은 policy들을 Baysian 최적화로 policy 구성
  * Rand Aug: Aug 연산 몇개를 얼마나 할지를 random하게 하는 것 기존 AA와 성능 차이 없음.


-------------------------------------------------------
<br/>

