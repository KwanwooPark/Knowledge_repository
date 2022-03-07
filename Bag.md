## Data Argumentation  
* Photometric Distortions  
* Geometric Distortions  
* Cutout  
* Random Erase
* Mixup
* CutMix
* Mosaic
* GAN (Data Generation)

-------------------------------------------------------
<br/>

## Label Smoothing  
* Logit vector를 softmax 해서 1이 되려면 logit이 굉장히 크도록 학습 -> 문제다.
* label smoothing으로 negative class에 대한 정보도 고려됨으로 class 간의 clustering이 잘 이루어짐.  
* KD에서는 역효과, Teacher의 label은 그 상대적인 크기또한 정보이기에..  

-------------------------------------------------------
<br/>

