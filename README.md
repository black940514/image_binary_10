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

5. imgaug 활용
- 학습 이미지를 변형시켜 새로운 학습 샘플 생성
- Imgaug 라이브러리 활용 
- Custom Augmentation 정의
- Custom Dataset 정의


6. resnet 커스텀 모델 활용
- resnet을 커스텀 모델로 활용
- 사전 학습된 resnet 모델 불러오기
- 커스텀 모델 정의
- 커스텀 모델 인스턴스 생성
- 사전 학습된 resnet 모델의 features 부분에서 가중치 추출
- 커스텀 모델의 features 부분에 가중치 복사


7. loss function에 대한 이해
- BCELoss
모델 출력층 : output node = 1
sigmoid function 을 넣어야함 : BCEloss 내부에 sigmoid function 이 포함X
학습 : lossfunction 을 진행하지 않음
추론 : model output에 sigmoid function 적용되어 있기 때문에 0~1 값이 나오므로 0.5 임계값으로 binary classification 진행

- BCEWithLogitsLoss
모델 출력층 : output node = 1
모델 내부에서 softmax함수를 적용할 필요가 없음 : sigmoid function 이 이미 포함O
학습 : lossfunction 을 진행하지 않음
추론 : torch.sigmoid 함수로 output을 감싸서 0.5 임계값으로 binary classification 진행

- CrossEntropyLoss
모델 출력층 : output node = 2
모델 내부에서 softmax함수를 적용할 필요가 없음 : 내부적으로 softmax함수가 포함되어 있음
학습 : lossfunction 을 진행하지 않음
추론1 : torch.max로 해도 binary classification 결과 나옴
추론2 : F.softmax 함수로 output을 감싸서 0.5 임계값으로 binary classification 진행


8. tqdm
wandb 사용 시 학습 과정 시각화


9. DenseNet
- 


