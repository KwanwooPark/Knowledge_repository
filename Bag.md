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

##  Quantization
* Uniform, Non-Uniform
  * 균등한 step으로 양자화(uniform), 입력신호에 따라 촘촘하게 양자화 step (non-uniform)
* Affine, Sclae
  * Quantization 방법, Affine = Sclae + transform
  * 연산량 측정해보면, online affine이 scale보다 많이 크며, 성능차이는 그만큼 안남.
* Calibration max 값은 분포의 max, entropy, 99.99% 중 많이 사용.
  * entropy는 quntization시 손실률이 적은, nvidia는 이걸 default로 사용.
* 양자화도 tensor 단위로 할지, channel 단위로 할지 다름.
  * depth-wise, BN 같은 경우 channel 연산이기에 per-tensor 시 성능 하락 큼. 복잡할수록 per-channel.
* Dynamic은 weight만 quantization, 계산시 다시 dequant해서 사용, 속도 향상 미비, 메모리 감소효과 (MLP, LSTM, 등)
  * Static은 weight랑 activation(=입출력신호) 둘다. 보편적으로 이걸 CNN에 사용.
* PTQ보단 QAT가 성능 좋음.
  * PTQ로 찾은 minima는 변동성이 커 조금만 변해도 loss 확 오름. QAT는 local minima라 안그럼.
  * QAT는 pretrain model을 불러서 layer 앞뒤로 quant, dequant 넣어서 학습하는 방식. (fake graph)

 

##  Multi Task Learning
* hard sharing
  * universal feature extractor
  * task-free한 featrue extractor를 거친 후 각 task 별 module을 사용.
  * low 및 mid level의 feature가 task 별로 동일하게 사용.
  * task가 유사할 수 록 성능이 높지만, 대게 soft sharing이 성능 좋음.
  * inference 시 여러 task를 수행하더라도 한번의 backbone만 수행. (선택적 task 가능)
* soft sharing
  * universal parametric family
  * low부터 high까지 task specific feature 출력 가능.
  * inference시 선택적 task 불가.
* 근래 들어 이쪽 연구가 많이 이루어지지 않는 듯... application은 있다만 목표가 MTL은 잘못봄.

-------------------------------------------------------
<br/>
