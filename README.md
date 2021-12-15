![image](https://user-images.githubusercontent.com/60537388/145531886-a210ad21-c081-49f6-9b5e-de805b0f5700.png)
## 흉부 폐질환 진단 및 분류 / Pediatric pulmonary disease detection

[Full_PDF] : [흉부.pdf](https://github.com/Pleasant-riot/Lung-Disease-Detection/files/7690712/default.pdf) 

[Demonstration_Video] : [Demonstration.zip](https://github.com/Pleasant-riot/Lung-Disease-Detection/files/7690735/Demonstration.zip)

[Environment]

	Python = 3.8.10
	Tensorflow = 2.7.9

--------------------------
## [Summary]
Kaggle의 RSNA Pneumonia Detection Challenge X-ray 데이터를 활용하여 흉부 폐 질환 진단 검사 프로그램을 제작했습니다.
총 3개의 질환 분류가 가능합니다. 정상과 폐렴 그리고 진단되지 않은 x-ray 데이터입니다. 전처리이후 CheXNet 딥러닝 모델을 활용하여 3가지 진단이 분류되도록 하였습니다.

## [Process]
EDA > Preprocess > Image to Array > Classification

## [Skill]
모델의 성능을 개선하기 위해서 여러가지 전처리 과정을 거쳤습니다.
1. clahe
2. 
