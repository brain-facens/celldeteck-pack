

# Cellphone detection using YOLOv5
Python package for cell phone detection using YOLOv5-based custom model

# Install
```
git clone https://github.com/L0G1C06/celldetec-pack
cd celldetec-pack
pip install -e .
```
 
# Train

- Two ways:
  - First one:
    ```python
    from yolov5 import train

    train.run(imgsz=640, weights="yolov5s.pt", data="path/to/data.yaml, cfg="yolov5s.yaml")
    ```
  - Second one:
    ```
    $ yolov5 train --data path/to/data.yaml --cfg yolov5s.yaml --weights yolov5s.pt --batch-size 16 --img 640
    ```
    
# Inference

- Two ways:
  - First one:
    ```python
    from yolov5 import detect
    
    detect.run(imgsz=640, weights="yolov5s.pt, source=0(for webcam))
    ```
    
  - Second one:
    ```
    $ yolov5 detect --weights yolov5s.pt --source 0 --img 640
    ```
    
# Export 
Export yout model for torchscript, onnx, coreml, pb, tflite and tfjs

``` 
$ yolov5 export --weights yolov5s.pt --include torchscript, onnx, coreml, pb, tfjs
```
    
# Classify 
Train, val, predict image classifier

```
$ yolov5 classify train --img 640 --data mnist2560 --weights yolov5s-cls.pt --epochs 1
```

```
$ yolov5 classify predict --img 640 --weights yolov5s-cls.pt --source path/to/images/
```

# Segment
Train, val, predict instance segmentation model

```
$ yolov5 segment train --img 640 --weights yolov5s-seg.pt --epochs 1
```

```
$ yolov5 segment predict --img 640 --weights yolov5s-seg.pt --source path/to/images/
```
