2021-12-17 > [공모전 2등]  
```- 소아흉부 폐질환 진단 및 분류- NIA , 과학기술정보통신부, FA_solution , 고려대학교```  

[내용증명] : [공모전수상.pdf](https://github.com/Pleasant-riot/Lung-Disease-Detection/files/7764519/default.pdf)  
![image](https://user-images.githubusercontent.com/60537388/147138310-e8096107-e371-4191-a792-998fa5c3b0ea.png)  

---------------------------
![image](https://user-images.githubusercontent.com/60537388/145531886-a210ad21-c081-49f6-9b5e-de805b0f5700.png)
## 흉부 폐질환 진단 및 분류 / Pediatric pulmonary disease detection

[Full_PDF] : [흉부.pdf](https://github.com/kikiru328/Lung-Disease-Detection/files/7920522/default.pdf)


[Demonstration_Video] : [Demonstration.zip](https://github.com/Pleasant-riot/Lung-Disease-Detection/files/7690735/Demonstration.zip)

[presentation] : https://www.youtube.com/watch?v=IC1QITRFGHg&ab_channel=CAKD3AI-SOLUTIONPROJECTS

[Environment]

	Python = 3.8.10
	Tensorflow = 2.7.9

--------------------------
## [Summary]
Kaggle의 RSNA Pneumonia Detection Challenge X-ray 데이터를 활용하여 흉부 폐 질환 진단 검사 프로그램을 제작했습니다.
총 3개의 질환 분류가 가능합니다. 정상과 폐렴 그리고 진단되지 않은 x-ray 데이터입니다. 전처리이후 CheXNet 딥러닝 모델을 활용하여 3가지 진단이 분류되도록 하였습니다.

<details>
<summary> <b>[공모전내용 ReadMe]</b> </summary>
<div markdown='1'>  

## [Competition]
공모전의 내용은 대외비로 github에 제공할 수 없습니다.  
간략히 설명하자면 소아의 페 질환 `6개의 질환(정상, 과다팽창, 호흡곤란증후군, 무기폐, 공기누출, 흉막삼출, 폐렴)` 을 분류하는 작업입니다. 	

* 제작환경
		
		python = 3.6
		Tensorflow = 1.13.1
		Keras = 2.4.2

공모전에서 제공받은 독립적인 가상환경에서 하였기에 코드만 업로드를 하였습니다. 공모전 진행시 위와 동일한 과정을 거쳤습니다. 
</div>  
</details>  

## [Project process]
EDA > Preprocess > Image to Array > Classification

### [Process]
모델의 성능을 개선하기 위해서 여러가지 전처리 과정을 거쳤습니다.

#### 1. clahe

![image](https://user-images.githubusercontent.com/60537388/146228675-cb7026b0-b91f-437a-8e60-1f02594f094c.png)  

~~~python
clahe = cv2.createCLAHE(3.0, (20,20))
Changed_image = clahe.apply(image)
~~~

	
clahe를 적용하고 나서 폐 내부의 데이터를 조금 더 정확하게 파악할 수 있었습니다.

#### 2. U-Net Segmentation

![image](https://user-images.githubusercontent.com/60537388/146231178-4fbab414-04f6-41d3-944a-1d7b544e10b7.png)

U-net 모델을 적용하여 전체 X-Ray 부분에서 폐만 추출하였습니다. 추출된 데이터를 이용하여 분류 모델에 적용하였습니다.

#### 3. Image Augmentation
이미지 개당 추가로 4개를 증식시켜 학습시켰습니다.   
~~~python
import imagaug
~~~

## [Model]
딥러닝 모델은 CheXpert에서 개발한 CheXnet을 활용하여 classification을 진행하였습니다.  
백본은 `Densenet121`을 기반으로 진행이 되며, Densenet121이 끝나는 시점에 `CheXNet의 가중치`가 로드 되면서 ouput 층을 바꿉니다.  

<cite>아래 내용은 공모전의 내용입니다. (3분류는 7 -> 3)</cite>
![image](https://user-images.githubusercontent.com/60537388/216279911-99c243dc-1b7a-4dac-963d-2733d997db48.png)

## [GUI]
제작한 모델을 가지고 PyQT5를 이용하여 GUI를 제작했습니다. 제작된 내용은 다음과 같습니다. 시연영상은 위와 동일합니다.
![image](https://user-images.githubusercontent.com/60537388/146233852-82d176b9-8cd0-4a7b-8d02-b76c68f89e31.png)



## [Teammates]

채승혜 https://github.com/SeunghyeChae

진유훈 https://github.com/JINYUHOON

박기범 https://github.com/KIBEOMP
