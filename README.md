# License-Plate-Recognition

This Project detects the number on the License Plate of a car using an Image.

This project is divided in three main parts:-
1. License Plate Detection
2. Digits Segmentation
3. Digits Recognition

In this project, Recognition is not dependent to any number.
This can detect the number of any length unless it is written in English Alpha-numeric format.

### License Plate Detection

To detect License Plate from the Image, we used YOLOV3.
Used YOLOV3 to detect only 1 class ["LP"].
To detect license plate, used pre-trained weights for License plate detetction.
Pre-trained weights for License Plate detection can be downloaded from https://www.kaggle.com/achrafkhazri/yolo-weights-for-licence-plate-detector
