# Term

* **Long Tail Distribution**  
= Class imabalance, 많은 양의 sample로 overfitting되어 적은 양의 class는 성능이 낮게 나오는 problem.  


# Loss

* **Focal Loss**  
hard/easy sample을 prob 기준 구분하여 loss에 직접 weight를 가해 easy sample 영향 낮추고 hard sample 고려하도록  
https://arxiv.org/pdf/1708.02002.pdf

* **Class Balanced Loss**  
데이터 간의 유의미한 정보가 중복된다라는 개념을 도입, 많은 데이터를 학습에 넣었을 때 중복되는 만큼 적은 weight를 준다는 개념.  
각 클래스 별 Effective Number(전체 양(N) 대비 몇장(n)을 뽑았을 때 유효한 장 수의 기대치)의 역수를 weight로 사용.  
즉, 각 클래스별 Effective Number는 클래스 set이 가질 수 있는 유효한 정보량이며 이는 샘플 수에 해당.  
결과론적으로, 전체 데이터 대비 일정 비율 이상의 클래스들이 너무 낮은 weight를 받지 않기 위해서 인 듯.  

* **Seesaw Loss**  
long tail (class imbalance) 문제 해결 방안, loss에 2가지 factor 적용.  
Mitigation Factor: instance number of classs의 비율 만큼 weight 적용.  
Compensation Factor: 많이 틀린 부분에 대해서 weight 적용.  
두 factor를 곱하여 weight로 사용하며, loss 보단 gradient에 직접적인 영향.  
https://arxiv.org/pdf/2008.10032.pdf  

* 
