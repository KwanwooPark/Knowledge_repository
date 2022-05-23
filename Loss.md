## Focal Loss  Focal Loss  
![FocalLoss](./images/FocalLoss.png)  
* loss에 predict probability 기반 weight.  
* easy sample 영향 낮추고 hard sample 고려하도록  
> "Focal Loss for Dense Object Detection," ICCV 2017.  

-------------------------------------------------------
<br/>

## Class Balanced Loss
![ClassBalancedLoss](./images/ClassBalancedLoss.png)  
* 데이터 간의 유의미한 정보가 중복, 이를 고려하여 class 별 유의미한 양의 역수를 weight로 사용.  
  * Effective Number(전체 양(N) 대비 몇장(n)을 뽑았을 때 유효한 장 수의 기대치)의 역수를 weight로 사용.  
  * 각 클래스별 Effective Number는 클래스 set이 가질 수 있는 유효한 정보량이며 이는 샘플 수에 해당. 
   
   
* *결과론적으로, 클래스 샘플 수에 반비례한 weight를 주는데, 일정 비율 이상일때 너무 낮은 weight를 주지않기 위해서인듯.*  
> "Class-Balanced Loss Based on Effective Number of Samples," CVPR 2019.  

-------------------------------------------------------
<br/>

## Seesaw Loss
![SeesawLoss](./images/SeesawLoss.png)  
* long tail (class imbalance) 문제 해결 방안, loss에 2가지 factor 적용.  
  * Mitigation Factor: instance number of classs의 비율 만큼 weight 적용.  
  * Compensation Factor: 많이 틀린 부분에 대해서 weight 적용.  
* 두 factor를 곱하여 weight로 사용하며, loss 보단 gradient에 직접적인 영향.  


* *Compensation Factor가 항상 샘플 많은 class에 유리한가? 그래야 보상개념인디, 아니면 Focal이랑 비슷한디*
> "Seesaw Loss for Long-Tailed Instance Segmentation," CVPR 2021.  

-------------------------------------------------------
<br/>

## PolyLoss
* CrossEntropy 혹은 Focal loss를 테일러 급수로 표현.
* 그럼, c * (1-p) 의 거듭제곱 합으로 표현 가능. 즉, label과 pred의 distance의 거듭제곱과 그 가중치.
* 이때 이 가중치 (coefficient)의 optimal 값을 찾는 것이 목표.
* 첫번째 term에만 coefficient 두는게 간단하며, 효과적. 이 coefficient는 실험적으로 찾는 듯.
* DropLoss라고 테일러 급수 뒤에 term들을 버리는 loss도 있음. (근데 이 논문은 뒤에 텀들도 중요하다고 함)

> POLYLOSS: A POLYNOMIAL EXPANSION PERSPECTIVE OF CLASSIFICATION LOSS FUNCTIONS, ICLR 2022.  

-------------------------------------------------------
<br/>

