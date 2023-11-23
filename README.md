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
## good result:
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/5839592e-35de-4dc5-9c50-d625674eb61f)
The initial phase of an identified object that has been classified as an activity called “running
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/bb4ffbf1-b538-4613-a715-7b9a82ea3a4d)
Activity classified as a squat from a straight-on and angled camera angle
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/d31f6666-8642-48fa-b4f5-f662c0b6c2d3)
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/1bfbfc49-2aa7-43bf-98cb-e4b4a17bc924)

![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/d5027050-f0d2-4992-bde0-25f93c7ad7fe)
Activity classified as "crouching" - bending down to pick up, for example, an object from a distance
front and side

![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/e575250e-379f-4c24-a5ab-8f3dcdfcbcf8)

![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/0a2337ac-7eaf-4984-a6ed-bebee6109f72)
Classified activity: "carrying" a container, as a human-object interaction
in an angled shot looking from behind
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/ea0fca2d-0421-44c7-8e70-2b894cf9b1a6)
Classified activity: "carrying" a container, as a human-object interaction
in a side view

## examples of detection errors:
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/358be2d5-b5ed-4e97-bee2-8600e8668179)
An example of a video being rejected due to an incorrectly detected pose. Other human-like objects and unnecessary points of the environment were detected

![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/8dbbd432-8740-49b0-a53d-59163de9fe06)
Example of a rejected video due to a person being mistaken for a human-like object (mannequin)
and in the figure next to it, a device was additionally detected in the gym

![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/fa10bd40-bceb-4fde-8612-530338abab5c)
Example of a rejected video due to double detection of a character. The pose stayed
identified in the actual place and additionally in the mirror

## test on images in another part of time
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/87c65161-bce5-4d00-899f-2adf6125fa7f)
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/7359178d-3ffd-4afb-b8e5-614127f9d96e)
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/3c273278-b4e7-4ea4-ac29-56f4115113e7)
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/ca7e5d3c-2933-480b-b982-9f955acb1a52)

## graphs
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/e7e5798e-7c6e-4d30-b617-d57d599fb1ac)
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/f7b6d9f2-9e9f-4f4e-b200-fe0629fd0ec6)

## system result
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/1a856386-347a-488d-bd6b-9615ed7bfd43)
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/ca47553c-563d-4438-b8cd-6177f72053bc)
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/0d93acdc-c0c7-4521-ab7c-bda7dcd41c7e)
![image](https://github.com/AsiaEwa/AI-methods-to-recognize-human-activity-Python/assets/101841759/8b6c3df0-fb38-481c-b06f-9d8f02b4475b)
Perfect result of the confusion matrix, the results are only on the diagonal of the square 
One of the best results of the project showing the classifier confusion matrix

## Applicable to eg.:
Previously, the machine perceived a human being as a "square" made of tetrahedrons.
figure and did not even include body language. Technological advancement of artificial intelligence
reaches an increasingly higher level of inference and interpretation. This is also essential
part of the markerless arbitrary motion capture (MoCap) technology. Belong to them
among others animations and simulations of characters and verification of gait abnormalities. It is important
making identification in real time. It is then possible to verify the quantity
people in a given area, as well as reacting if an irregularity is detected. Including
In an accident, it could be exceeding the maximum number of people and not allowing entry
more of them. Based on the body's movements, we are able to identify any irregularities,
infer actions to which we should respond appropriately depending
from estimating the type of detected anomaly. The ability to identify fluently is
practically indispensable in many areas. Useful in law enforcement, care
caring for children and the elderly, as well as in health care. Identification systems find
also its application in sports games and ergonomic selection
workplaces.
### Communication and robotics
Tracking people's movements provides many opportunities to create improvement methods
functioning in everyday life and unusual situations in which they are used
integral devices helpful to humans. This allows you to predict behavior and their
analysis, providing benefits and thus preventing many unfavorable situations. Mobile
robots and autonomous vehicles detect and predict more accurately based on videos
pedestrian behavior than the person himself, apart from special cases, of course, therefore no
Full automation has been introduced everywhere.
Autonomous vehicles are also an example where human pose detection
is important. Waymo cars are considered one of the safest, but
it happens that a human driver following an autonomous car,
is hit due to an unexpected stop due to a pedestrian passing by
through the belts. The behavior of pedestrians and the traffic of autonomous vehicles is constantly changing
in the refinement phase. 56
### Human-computer cooperation
In the past, human-like androids were considered a conceptually fictional invention
most often in books and films. They have been built, are currently operational and are being improved
e.g. Tesla Bot, Sophia. Compared to other robots, humanoids are the ones with more
advanced scale of technological difficulty of implementation. 3D pose estimation helps
computers in achieving a relatively high level of understanding of human behavior,
but this is not yet an effect that could be considered perfect. In case the robot
will be equipped with a system for identifying human pose and activity, which will allow it to be used further
improvement, Then you can expand its scope of capabilities to the effect detected
position of a person from a given category (class) performed the programmed task, and these activities
can be defined as cooperation between a robot and a human. Robots cooperating with humans
when they are able to recognize human pose, they perform tasks more efficiently
in the way that one expects of them.
### Monitoring and security
Identifying anomalies in human movements in video can make activities easier
preventive measures and make us safer. Crowd monitoring and identification
much after the fact is not something satisfying. When brutal ones are detected
behavior, the system can trigger an alarm by calling the appropriate services directly to the point
events to check for suspicious behavior and stop it if possible
incident. Movement tracking is necessary for this type of activity. Based on location
key points the system can generate alerts in real time when potential
the attack is underway. As some research suggests, identifying people with their hands raised or
lying down may also be associated with an alarming situation.
### Sport
Examining the arrangement of human joints can be useful for various types of interpretations
sports indicators, useful both for people practicing sports and also
coaches or physiotherapists. An example is kinematic position correction. You can
use this data to provide instant feedback and quantify a person's performance
performing a given activity or a series of motor activities. Recognition of activities is
desirable when assessing movements in learning swimming, football, Tai Chi and more
more others. Fitness enriched with artificial intelligence techniques improves
conducting a series of training sessions. These techniques allow for increased security,
as well as receiving real-time feedback on training
carried out at home.
### Psychology and medicine
The assessment of the three-dimensional pose of a human figure is also used in behavior
health prevention in telehealth. Thanks to this, the doctor can prepare a quantitative assessment
motor assessment when the patient is at home. Identification of anomalies
in human motor behavior is important in order to detect diseases that manifest themselves
through movement changes typical of a given disease, e.g. autism. Early diagnosis
helps improve the patient's life, partially neutralizing the effects of the disease. Activity tracking
motor skills improves the diagnosis of people's mental states and their well-being
emotional.
### Shopping in online stores
Virtual shopping was created as a new way to make shopping easier for customers
trying on. Thanks to this solution, the customer can see what it will look like in a given one
product before making a purchase, which will allow you to make a more sensible decision. It enables
is choosing the style, color, size and, above all, the presentation of the product
simulated in practice. This is a good solution when we want to take advantage of convenience
and a wider selection of products available in online stores, but also for people
who have problems with movement, are e.g. disabled. Virtual pose estimation
in 3D projection is the basis for virtual trying on through collaborative fitting
subject to the shape of the figure and the angles of the face.
### To sum up, the designed system can be implemented in innovative projects
based on:
* estimating human activity,
* motion transfer and augmented reality,
* robot training,
* motion tracking for consoles,
* human fall detection,
* analysis of motor diseases - prognosis and medical diagnosis
(prevention and facilitation of treatment),
* gesture detection applications,
* care for animals, children and the elderly,
* full body communication in sign language (e.g. traffic police signals),
* applications supporting sports game analysis,
* applications for analyzing dance techniques (e.g. in ballet dances),
* a virtual tool for learning posture, body work, finesse,
* monitoring, supervision and security, e.g. civil, in production halls,
* optimization of street and industrial traffic,
* activity recognition using a smartphone, smartwatch and other gadgets.






