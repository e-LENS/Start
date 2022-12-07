# eLENS

# Software

## Prerequisites
* LINUX
* Python 3
* CPU or NVIDIA GPU

## Installation
```
git clone https://github.com/hazirbas/posenet-pytorch
cd posenet-pytorch
pip install -r requirements.txt
```

## Dataset
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


## PoseNet train/test

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

## Installation

1. Format the micro SD card
2. Download [jetson-nano-2gb-sd-card-image](https://developer.nvidia.com/jetson-nano-2gb-sd-card-image) and unzip it
3. Use Etcher to write the Jetson Nano Image to the microSD card
4. Download [JetRacer image](https://drive.google.com/file/d/1YtnjQ77w1B9REzy1JgLJbVSs2K3ocAEr/view?usp=sharing) and unzip it
5. Use Etcher to write the Jetracer Image to the microSD card

## Connect to JetRacer

1. WIFI에 JetRacer 연결
2. Jetson Nano의 piOLED에서 Wlan0 interface의 ip address 확인 or `ifconfig` command로 확인
3. 이후 브라우저에서 `http://<ip address>:8888` 주소로 RetRacer에 무선 연결
4. Password `jetbot` 을 입력해 Jupyter Lab 실행

## Basic motions


