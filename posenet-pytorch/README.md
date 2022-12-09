### Initialize the network with the pretrained googLeNet trained on the Places dataset
If you would like to initialize the network with the pretrained weights, download the places-googlenet.pickle file under the pretrained_models/ folder:


아래 코드를 통해 다운받거나
```
wget https://vision.in.tum.de/webarchive/hazirbas/poselstm-pytorch/places-googlenet.pickle
```

아래 구글드라이브의 pretrained_models 디렉토리를 다운받는다. 

https://drive.google.com/drive/folders/19P1yU4HAmjYRiVjuhGXh2Weqgf1rpdbW


### 7Scenes dataset 6-DOF preprocessing

__1. 7Scenes dataset directory structure를 확인한다.__
```
posenet-pytorch/dataset/[dataset이름]
├── seq-01
│   ├── frame-000000.color.png
│   ├── frame-000000.pose.txt
│   ├── frame-000001.color.png
│   ├── frame-000002.pose.txt
│   ├──  ...
│   
├── seq-02
  ...
├── TrainSplit.txt
├── TestSplit.txt
├── dataset_train.txt
└── dataset_test.txt   
```

__2. `7scenes_preprocessing.py` 의 `data_path`를 위 dataset 디렉토리 path로 설정한다.__

ex)
```python
data_path=".\posenet-pytorch\dataset\[dataset이름]"

```

__3.  `7scenes_preprocessing.py` 의 `train_seqnum`과 `test_seqnum` 을 `TrainSplit.txt`와 `TestSplit.txt` 파일 내용으로 변경한다. __

ex)

<img src="https://user-images.githubusercontent.com/108324590/206702952-db287461-2286-4d12-a1b4-66011418b3cf.jpg" width="15%" height="15%">
<img src="https://user-images.githubusercontent.com/108324590/206703213-fbe7a77a-967b-4328-b407-cefd4df9d3d1.jpg" width="20%" height="20%">

```python
train_seqnum=[1, 2]
test_seqnum=[3, 4]

```



__4. Run `7scenes_preprocessing.py`__


=> 변형된 label값들은 `./dataset_train.txt` & `./dataset_test.txt` 에 저장된다.


