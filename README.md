"# image_binary_10" 
1. 깔끔한방 vs 지저분항방 분류 - AlexNet
- Pretrained Model 사용 - 성능 매우 우수하게 나옴옴
- 데이터 증강
2. 




4. 커스텀 모델 정의하고 사전 학습된 모델의 가중치 복사하기
- 사전 학습된 모델의 features부분에서 가중치 추출
- 새로 정의한 모델 인스턴스 생성
- 사전 학습된 모델의 features부분에서 가중치 복사
- 복사된 가중치 확인
- BCEWithLogitsLoss 손실함수에는 softmax함수가 이미 포함되어 있어서 모델 내부에서 softmax함수를 적용할 필요가 없음


