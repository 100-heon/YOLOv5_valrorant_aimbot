YOLOv5를 활용한 발로란트 게임의 에임보정 프로그램입니다.
재미로 봐주세요 :)
psk01000 계정을 잃어버려서 fork 해왔습니다..ㅎ

------파일 설명-----

best.pt

-google colab에서 학습한 모델 중 가장 학습이 잘 된 모델입니다. 나중에 python에서 작업할 때 불러와야 할 모델입니다.


main.py

-best.pt파일을 불러 온 뒤 스크린샷을 띄우고 그안에 detect된 객체의 좌표를 불러오고 계산 한 뒤 arduino로 보내주는 메인 코드입니다.


~~.ino

-아두이노 파일입니다. main.py에서 전송한 데이터를 전달 받으면 이동 하고 클릭하는 코드가 들어있습니다.
아두이노 레오나르도를 사용하였습니다.

~~.yaml

-학습 시킬 클래스를 정의하는 부분입니다. 기존 YOLOv5는 80가지 정도의 클래스를 탐지할 수 있으나 우리가 탐지하려는 객체는 게임 속 적 이기 때문에 bot이라는 
클래스만 남기고 모두 제거하였습니다. 

Q&A
1. 아두이노를 사용한 이유는 무엇인가요?

A) 파이썬에서 마우스 제어를 하려고 시도하였으나 게임에서 소프트웨어적인 마우스제어는 허용하지 않아서 하드웨어로 인식되는 아두이노 레오나르도를 사용하였습니다.

2. 다른게임에도 적용이 가능한가요?

A) 원하는 게임을 학습시켜서 best.pt만 교체해준다면 가능 할 것 같습니다. 그러나 게임마다 캐릭터의 크기가 다르기 때문에 좌표수정이 필요할 것으로 보입니다.

![봇인식](https://user-images.githubusercontent.com/62214011/212617776-92759dc0-f086-46f5-8c5a-ba174292a2cc.gif)

![결과물](https://user-images.githubusercontent.com/62214011/212617258-9a14d090-6225-4999-ae74-d3d1c6f3527f.gif)
