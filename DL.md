# Deep Learning

* Long Tail Distribution  
= Class imabalance, 많은 양의 sample로 overfitting되어 적은 양의 class는 성능이 낮게 나오는 problem.

* Seesaw Loss  
long tail (class imbalance) 문제 해결 방안, loss에 2가지 factor 적용.  
Mitigation Factor: instance number of classs의 비율 만큼 weight 적용.  
Compensation Factor: 많이 틀린 부분에 대해서 weight 적용.
