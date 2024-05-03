# YOLOv9 - Fixed Version

Implementation of paper - [YOLOv9: Learning What You Want to Learn Using Programmable Gradient Information](https://arxiv.org/abs/2402.13616)

<div align="center">
    <a href="./">
        <img src="./figure/performance.png" width="79%"/>
    </a>
</div>


## Performance 

MS COCO

| Model | Test Size | AP<sup>val</sup> | AP<sub>50</sub><sup>val</sup> | AP<sub>75</sub><sup>val</sup> | Param. | FLOPs |
| :-- | :-: | :-: | :-: | :-: | :-: | :-: |
| [**YOLOv9-C**](https://github.com/WongKinYiu/yolov9/releases/download/v0.1/yolov9-c.pt) | 640 | **53.0%** | **70.2%** | **57.8%** | **25.5M** | **102.8G** |
| [**YOLOv9-E**](https://github.com/WongKinYiu/yolov9/releases/download/v0.1/yolov9-e.pt) | 640 | **55.6%** | **72.8%** | **60.6%** | **58.1M** | **192.5G** |
| [**Best.pt**](https://github.com/Teameviral/yolov9/blob/main/runs/train/exp/weights/best.pt) | 640 | **88.5%** | **90%** | **93.6%** | **2k+** | 
<!-- small and medium models will be released after the paper be accepted and published. -->


## Installation

1. Google Colab

```
!git clone https://github.com/Teameviral/yolov9.git
%cd yolov9
!pip install -r requirements.txt -q

```

2. AWS/Azure/Raspberry Pi/Linux

   Make Sure git is installed on your system. 
   ```
   sudo apt-get install git
   ```
   Now Clone the repo - Remember the command
   ```
   git clone https://github.com/Teameviral/yolov9.git
   ```
   Change Directory
   ```
   cd yolov9
   ```

   Enable and Activate Virtual Environment

   ```

   python3 -m venv venv
   source venv/bin/activate
   ```

   Now install neccessary modules -

   ```
   pip install -r requirements.txt -q
   ```

  ## Test the Model

We will use gelan-c.pt which is a low weight object detection model - You can use any model which is perfect your work.
```
path=Yolov9/ObjectDetectionModels/weights/gelan-c.pt #Model Location
```
Run it to test your model
```
!python detect.py --weights {HOME}/weights/yolov9-e.pt --conf 0.1 --source {HOME}/test1.jpg --device 0
```
**For Raspberry Pi:**

``` python3 detect.py --weights yolov9/ObjectDetectionModels/weights/gelan-c.pt --conf 0.1 --source yolov9/test1.jpg --device 0 ```

**For Live Webcam:**
```
python3 detect.py --weights yolov9/ObjectDetectionModels/weights/gelan-c.pt --conf 0.1 --source 0 yolov9/test1.jpg --device 0
```
CPU Version
```
python3 detect.py --weights yolov9/ObjectDetectionModels/weights/gelan-c.pt --conf 0.1 --source 0 yolov9/test1.jpg --device cpu

```

Now you will see the result - Make sure that you write the path in correct format.

## Train Your Model


