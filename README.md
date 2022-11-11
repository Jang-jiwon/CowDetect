# CowDetect

4조 졸업 프로젝트 

yolov7와 deepsort기반 소 가임기 예측 인공지능


# install 
```
git clone https://github.com/Jang-jiwon/CowDetect.git
cd CowDetect
git submodule update --init --recursive
cd StrongSORT-YOLO
pip install -r requirements.txt
wget https://www.dropbox.com/s/x4x6fr88lbgb504/sample_video.mp4
wget https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-e6e_training.pt -O /content/CowDetect/StrongSORT-YOLO/yolov7/yolov7-e6e_training.pt
```

# train
프리징 할 경우

```
$python train.py --workers 8 --device 0 --freeze 105 --batch-size 32 --data ../your_path/data.yaml --img 416 416 --cfg cfg/training/yolov7.yaml --weights 'yolov7_training.pt' --name yolov7-custom --hyp data/hyp.scratch.custom.yaml
```
안할 경우
```
$python train.py --workers 8 --device 0 --batch-size 32 --data ../your_path/data.yaml --img 416 416 --weights 'yolov7_training.pt' --name yolov7-custom 
```


# tracking
```
$python track_v7.py --source sample_video.mp4 --save-vid --class 19 --yolo-weights ../your_path/yolov7-e6e_training.pt
```
</br></br></br></br>
[코랩으로 실행하기](train+tracking.ipynb)
