# ITNPA1-Deep-Learning-based-Car-Detection-from-Google-Earth-Images-using-YOLOv7-and-PyTorch

This project aims to detect cars in images captured from Google Earth using the YOLOv7 object detection algorithm implemented in PyTorch. The goal is to create a precise and effective model that can be applied in practical applications such as traffic monitoring systems or autonomous vehicles.

## Dataset

We collected a diverse dataset consisting of 100 positive samples from the city of 'Renfrew' and 100 positive samples from 'Stirling'. These samples were used for training and evaluation purposes. Various data preprocessing techniques, including image resizing, normalization, bounding box annotation, anchor box assignment, and data augmentation using Roboflow, were applied to prepare the dataset.

## Methodology

The YOLOv7 model, combined with the capabilities of PyTorch, was employed for car detection. YOLOv7 utilizes a one-stage object detection technique by dividing the input image into a grid of cells and predicting bounding boxes and class probabilities for each cell. Convolutional neural networks (CNNs) serve as the backbone network for feature extraction. The model incorporates anchor boxes of different aspect ratios and sizes to accurately predict bounding box dimensions. With the efficient architecture of YOLOv7 implemented in PyTorch, we achieved real-time car object detection by directly predicting objects in a single pass through the network.

## Results

The combination of PyTorch and YOLOv7 proved to be highly effective, providing fast and accurate car detection in various scenarios. The model exhibited strong performance, balancing inclusiveness and confidence, improving precision with increasing confidence, and demonstrating the trade-off between recall and precision. These results highlight the capabilities of the YOLOv7 model in accurately detecting cars. All the results can be found in Yolov7/runs/detect folder.

## Instructions

To run the code in this repository, please follow these steps:

Step 1 – Clone YOLOv7 Repo
Clone the yolov7 repository from GitHub by running the following command in the terminal.

git clone https://github.com/Qurat5/ITNPA1-Deep-Learning-based-Car-Detection-from-Google-Earth-Images-using-YOLOv7-and-PyTorch.git

Step 2 – Install requirements

!pip install -r yolov7/requirements.txt
!pip install -r yolov7/requirements_gpu.txt

Step 3 – Train yolov7 on the custom dataset

!python train.py --workers 1 --device 0 --batch-size 16 --epochs 100 --img 640 640 --hyp data/hyp.scratch.custom.yaml --name yolov7-custom --weights yolov7.pt

Step 4 – Train yolov7 on the custom dataset

!python detect.py --weights best.pt --conf 0.5 --img-size 640 --source img.jpg --view-img --no-trace



