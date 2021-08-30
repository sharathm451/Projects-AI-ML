
# Object Detection
## My Result:
![IMG20210830015931](https://user-images.githubusercontent.com/67855083/131312983-9fd7159c-c5c6-423b-ac5a-fafd24646e97.jpg)
### Video detection
https://user-images.githubusercontent.com/67855083/131313163-29f7af4a-ece9-4765-8ef3-13fbadd0b3ac.mp4


## Introduction to Tensorflow Object Detection API

Convolutional Neural Networks have revolutionalized Pattern Recognition in last decades. As a result, CNNs are currently used for varous applications such as Object Detection and Image Recognition.

The TensorFlow object detection API is a software framework used for object detection tasks. Tensorflow Object Detection API and other similar APIs (Keras RCNN, YOLO) uses pre trained CNNs inside the framworks for predictions. Most of those pretrained models are trained using, the COCO dataset, the KITTI dataset, and the Open Images Dataset. These models are trained to detect some fixed type of categories of objects such as, persons, cars, dog, tooth brush and etc. If you want to detect custom objects you can retrain those models using your own datasets.

# CNN models used in Tensorflow Object Detection API

![Logo](https://cdn-images-1.medium.com/max/800/1*-EyxSs2OiyWm-E6MSpSJiA.png)

## mAP (mean Average Precision)

AP (Average precision) is a popular metric in measuring the accuracy of object detectors like Faster R-CNN, SSD. Average precision computes the average precision value for recall value over 0 to 1

# How Object Detection is done

1.Generates the small segments in the input image

![Logo](https://miro.medium.com/max/724/0*kUNj3PTh2dVyf03m.png)

2.Feature extraction is carried out for each segmented rectangular area to predict whether the rectangle contains an valid object.

![Logo](https://oscimg.oschina.net/oscnet/up-04d098f4a9e8de7694ad3d1d72c5ca5fd0c.JPEG)

3.Overlapping boxes are combined into a single bounding rectangle (Non Maximum Supression)

![Logo](https://img-blog.csdnimg.cn/img_convert/2e0323ae5508d1de219214006f986a89.png)


# SSD Mobile Net
The SSD architecture is a single convolution network that learns to predict bounding box locations and classify these locations in one pass. Hence, SSD can be trained end-to-end. The SSD network consists of base architecture (MobileNet in this case) followed by several convolution layers:

![ssd](https://user-images.githubusercontent.com/67855083/131311104-5d08891b-fbdf-477b-871a-480ee85e686e.png)

SSD does not predict the shape of the box, rather just where the box is. The k bounding boxes each have a predetermined shape. The shapes are set prior to actual training. For example, in the figure above, there are 4 boxes, meaning k=4.

1.first the image is sent to the VGG Network and extracts the feature maps

2. These Feature  maps are sent to the ssd conv 6 layers Network then, it does the classification of each object detection.

3. Then it performs the 8732 Predictions of bounding boxes on each detected object which has already set the original ground truth image boxes.

4. Now, the task is to match these Predicted k=8732 number of boxes with the ground truth boxes with maximum no. of overlapped boxes
 
5. The maximum overlapped boxes are top 200 predictions with higher confidence percentage
 
6. This is filtered by the Non-Maximum Suppression with picking top 200 predictions of overlapped boxes
 
7. This overlapped boxes are selected with the IOU(Intersection Of Union)function and expel the remaining boxes with different sizes and aspect ratios
 
8. These different sizes and aspect ratios are prior set in the training of ssd network.

9.You can see this operation in handle models with masks,i.e...detected masks and detected boxes. reframed_boxes > 0.5(iou>0.5)
## Input
300x300 color Image (3@300x300)

## Outputs
SSD Mobile Net output the category of the detected objects and coordinates of there bounding rectangles offset (x,y,w,h)
![outputs](https://user-images.githubusercontent.com/67855083/131311413-2500bea2-46e4-4d1b-9fa5-b6202ecfc30c.png)

## output_dict
![dict](https://user-images.githubusercontent.com/67855083/131311629-5d96ae42-73ce-456b-8863-c6f9b5e5f231.png)

## output_dict[detection_classes]
![dict1](https://user-images.githubusercontent.com/67855083/131311783-fe138498-ebba-4c72-a61a-c4d001b7fbf2.png)

## category_index
![dict3](https://user-images.githubusercontent.com/67855083/131311929-d8c9bad6-b1f3-4d18-9479-67b498546f25.png)

## output_dict['detection_scores']
![dict4](https://user-images.githubusercontent.com/67855083/131312092-e14a55ec-cf5f-4287-9802-a5e731e1c5ee.png)

## output_dict['detection_scores']
![dict5](https://user-images.githubusercontent.com/67855083/131312371-13bf39d8-c8d7-40db-a329-00a508ca7eec.png)

## Detection Boxes parameters
![boxes](https://user-images.githubusercontent.com/67855083/131312631-c82ab2a6-ff5f-4039-bc60-6f1bc636d538.png)

## Installation

# Installing the Tensorflow Object Detection API
1.Download the tensorflow object detection api from https://github.com/tensorflow/models

2.Open the Anaconda Prompt and install the dependencies for windows,

pip install tensorflow

pip install keras

pip install opencv-python

pip install Cython

pip install contextlib2

pip install pillow

pip install lxml

pip install jupyter

3.Download the files from this repository

4.Copy and paste protoc.exe file in the path models-master\research

5.Open the Commmand Prompt in models-master\research and copy and run the command included in protoc command.txt

6.Copy the files 1.0 Object Detection Tutorial.ipynb, 1.0 Customized Object Detection.ipynb & 1.1 Customized Object Detection-Video.ipynb into models-master\research

7.Run above codes and check

# Acknowledgements

## Image Courtesy & Credits
https://www.analyticsvidhya.com/  
