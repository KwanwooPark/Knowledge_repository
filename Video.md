## A review of action recognition based on Convolutional Neural Network 
 * Video 대상으로 많은 task가 있지만 Action Recogintion = Image Classification.
 * Transformer를 제외하고 보편적으로 크게 다음과 같이 나눌 수 있음.  
   * Single-channel CNN
     * 3D CNN = 2d cnn + channl에 temporal 추가 된것.
     * C3D    = 2d cnn + kernel에 temporal 추가 된것 = 흔히 3D conv.
   * Dual-channel CNN
     * Two-stream = 보통 image stream과 video stream (주로 optical flow)를 입력으로 two path 처리.
     * CNN + LSTM = CNN 으로 feature 출력, LSTM같은 연속 데이터용 네트워크 사용 (RNN이든, GRU든)
   * Fusion of multiple methods
     * Combine Deep Learning Method = temporal 처리용 무언가의 연산 추가 (TSM, transformer도 이쪽일 듯)
     * Traditional Method = application과 접목하여 사용. (Skeleton 찾아서 인지한다든지)


-------------------------------------------------------
<br/>
