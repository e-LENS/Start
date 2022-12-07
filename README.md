# eLENS

# Software

## Prerequisites
* LINUX
* Python 3
* CPU or NVIDIA GPU

## Getting started
### Installation
```
git clone https://github.com/hazirbas/posenet-pytorch
cd posenet-pytorch
pip install -r requirements.txt
```

### Dataset
* Outdoor dataset

  Download [King's College dataset](https://www.repository.cam.ac.uk/handle/1810/251342) under `datasets` folder
  
* Indoor dataset

  Download [7 Scenes dataset](https://www.microsoft.com/en-us/research/project/rgb-d-dataset-7-scenes/) under `datasets` folder

```
datasets/KingsCollege
datasets/Chess
datasets/Fire
datasets/Heads
datasets/Office
datasets/Pumpkin
datasets/RedKitchen
datasets/Stairs
```

* 각 데이터셋에 대해 mean image 연산

```
python util/compute_image_mean.py --dataroot datasets/[데이터셋이름] --height 256 --width 455 --save_resized_imgs
```

* 6DoF 전처리


### PoseNet train/test

각 데이터셋에 대해 PoseNet 학습 및 테스트

* Train a model
```
python train.py --model posenet --dataroot ./datasets/[데이터셋이름] --name posenet/KingsCollege/beta500 --beta 500 --gpu 0
```

* Test a model
```
python test.py --model posenet  --dataroot ./datasets/[데이터셋이름] --name posenet/KingsCollege/beta500 --gpu 0
```

* 학습된 PoseNet 모델 및 학습 결과는 `./checkpoints/posenet/[데이터셋이름]/beta500/`에 저장됨
* 학습된 모델의 테스트 결과는 `./results/posenet/[데이터셋이름]/beta500/`에 저장됨


# Hardware

## Prerequisites
* Jetson Nano 2GB Developer Kit
* Jetracer
* micro SD card (64GB~)
* balenaEtcher



