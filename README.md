# AI-methods-to-recognize-human-activity-Python
Using artificial intelligence methods to recognize the type of human activity (Python)

The project presents the methods of detecting the human pose, and thus the
algorithms intended for this purpose. It contains the author's description of the system
and his own set of training and test examples. The developed system classifies 7 different types
of activities in the field of sports and everyday life, including interaction with objects.
Coordination points, body area and the type of activity performed are marked on the pose
detected in the image. The system consists of two components containing neural networks, one
is HRNet, a solution taken from the literature, and the other was written from scratch and
research was carried out on it. The influence of the number of neurons, the selection of the
number of epochs, the number of data batches on the accuracy of detection and classification
was checked. Studies have shown that a large network with a small amount of data tends to
learn by memory and adapt to noise, hence it loses the ability to generalize.
# Objective:
to design a system intended for detection and classification of human activity. It works by analyzing the video stream using a deep learning model designed to detect human poses and then classify the activities performed by them. Designed the system can be used in practice to detect a human figure and recognize his activity in real time after connecting a camera. The project used data from video recordings as material for learning the system and preparing tests for the project. The system is ultimately intended to classify selected activities, for which 7 different types have been selected.
# Technologies & tools
The project was made on the Linux Ubuntu operating system. The code was written in Visual Studio Code in the Python programming language version 3.8.10. Operations performed on images required the installation of libraries, including: such as: open pose, open CV (referred to in the code as "cv2"), mmcv, numpy, matplotlib, torach and those built in at the factory. These libraries facilitate motion analysis and tracking, image processing (filtering, edge detection, corner detection, histograms), face and gesture recognition. They can be used to attach photos to generate views similar to, for example, Google Street View. They are used in graphic operations and are prepared for machine learning algorithms. Code version control was used Gitlab and Github platforms. Video recordings were used as input data via camera: Webcam 1080P, model W88S, 3.6 mm lens, as well as selected recordings from open data sets. A neural network was used to write the code and train computer with graphics processor (GPU): NVIDIA SMI470.141.03 CUDA version: 11.4 and a regular quad-core (CPU) M1200.

# Instructions for starting a system for detecting and classifying human activity
1. Download the file and place it preferably in a separate directory for order
a) model for pose estimation from: https://github.com/open-mmlab/mmpose (hrnet_w32_coco_512x512-bcb8c247_20200816.pth),
b) model for classification from the downloaded zip file (trained_model.pt),
c) csv files for training and for test from the downloaded zip file (the classification has been simplified and organized for learning. It is defined in the Excel file at the end of the line: 0-6).
2. Preparing recordings of 7 activities for which the system code was written in a separate input folder: jogging, waving, skipping, jumping jacks "jacking"), squats, bending, carrying.
3. Preparing a second folder for exiting the recording system after processing it.
4. Open the Visual Studio Code environment with the downloaded and open codes.
5. Open the terminal and check whether the planned execution steps will be performed in the virtual environment whose name in the project is "(vnv3)" and the language version: Python 3 (Python 3.8.10). If not, you should create a virtual environment or enter it and preferably download the same version of Python, i.e. 3.8.10.
6. Before running, remove one "#" character in the first line of the "simplified command.sh" file
7. Running the activity classifier (file called second-kod.py)
a) Finding the path to the directory where the file is located,
b) Entering the directory (e.g.: /home/asia/mmpose/demo or cd ~/mmpose/demo),
c) Entering the name of the code file to be run in the terminal along with the version of the language used (pyton3 second-code.py).
8. Generating an activity classifier graph (file named graph-kod.py)
a) Finding the path to the directory where the file is located,
b) Entering the directory (e.g.: /home/asia/mmpose/demo or cd ~/mmpose/demo),
c) Entering the name of the code file to be run along with the language version used in the terminal (python3 graph-code.py).
9. Starting the entire system
a) Finding the path to the directory where the file "first-kod.py" is located as an estimator, because a file called second-kod.py is connected to it as a classifier
b) Enter the directory (e.g.: cd ~/Desktop or /home/asia/mmpose/demo or cd ~/mmpose/demo)
c) Entering the name of the code file to be run in the terminal (./polecenia_uproszczowane.sh)
# *
To change file locations, folder names, files, and videos, you must update them in your code and script.

# >> Ad.6 Classifier operation:

• You can choose to run it on a graphics processing unit (GPU) called cuda or a regular CPU; line: device=’cuda’ or use the commented “CPU” (use 1 option and leave the second one commented out).

• Controlling the precision of detection and classification by changing the values: Epoch num, batch size.

• You can also control the number of network neurons in the model class for linear layers (except for the values 480 and 7, which remain unchanged, other values can be modified); line: Class Model(nn.Module) self.l1=nn.Linear().
