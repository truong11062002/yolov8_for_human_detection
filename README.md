# Dataset

This project is trained on human detection dataset
You can download this dataset at this link: [Human Detection Dataset](https://drive.google.com/u/0/uc?id=1--0QuKMwj31K-CSvD8oq5fceFweiFPuN&export=download)

# Installation

This project builds upon [Ultralytics](https://github.com/ultralytics/ultralytics). You can see [The Ultralytics documentation](https://docs.ultralytics.com/) for installation constructions


# Result and Models



| P | R | mAP50 | mAP50-95    |
| -------- | -------- | -------- | --- |
| 0.857     | 0.743     | 0.847     | 0.598    |

You can download onnx model (.onnx) at this link: [model](https://github.com/truong11062002/yolov8_for_human_detection/releases/download/weights_yolov8_human_detection/best.onnx)

You can download pytorch model (.pt) at this link: [model](https://github.com/truong11062002/yolov8_for_human_detection/releases/download/weights_yolov8_human_detection/best.pt)

# Download pretrained model
```
!wget https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8s.pt
```

# Training
```
!yolo train model=yolov8s.pt data='./data.yaml' epochs=20 imgsz=640
```
**data.yaml**: containing information about your dataset

# Validating
```
!yolo val model=./best.pt data= ./data.yaml'
```

**best.pt**: file weight of model after training
**data.yaml**: containing information about your dataset

# Predict

## Upload an image
```
!yolo predict model=./best.pt source='./Crowd-of-Diverse-People_800x528.jpg'
```
## Upload online image
```
!yolo predict model=./best.pt source='https://assets.weforum.org/article/image/XaHpf_z51huQS_JPHs-jkPhBp0dLlxFJwt-sPLpGJB0.jpg'
```
## With youtube video
```
!yolo predict model=./best.pt source='https://youtu.be/MsXdUtlDVhk'
```

# Export model to onnnx format
```
!yolo export model=./best.pt format=onnx
```
