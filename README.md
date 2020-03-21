# tensorrt_car_det_yolov3
## 1. Install TensorRT on Ubuntu
## 2. Test TensorRT_yolo3_module
- a. Download vehicle / license plate detection model from Baidu online disk
- b. `python2 yolov3_to_onnx.py`. Convert yolov3 model .weights file to .onnx file
- c1. `python3 onnx_to_trt_1batch.py`. If you only need to process one image each time, for example you only have one camera. Executing this script you need python 3.x, and you will have a file named **yolov3-608.trt**, which is the file we ultimately need.
- c2. `python3 onnx_to_trt_multibatch.py`. If you need to process multiple images each time, for example you have multiple cameras. Executing this script you also need python 3.x, and you will have a file named **yolov3-608.trt**, which is the file we ultimately need. And the data accuracy is **FP16**, so the acceleration is more obvious.
- d1.`python3 trt_yolo3_module_1batch.py`, if you choose **c1**
- d2.`python3 trt_yolo3_module_multibatch.py`,if you choose **c2**. It detects 4 images at a time.
## 3. Test yolov3-tiny-onnx-TensorRT
- This project has been packaged into **class**, so you can use it directly according `import xx` command.
- a. `python2 yolov3_tiny_to_onnx.py`