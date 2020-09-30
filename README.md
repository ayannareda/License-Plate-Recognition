# License-Plate-Recognition

This Project detects the number on the License Plate of a car using an Image.<br /><br />

This project is divided in three main parts:-<br />
1. License Plate Detection<br />
2. Digits Segmentation<br />
3. Digits Recognition<br /><br />

In this project, Recognition is not dependent to any number.<br />
This can detect the number of any length unless it is written in English Alpha-numeric format.<br /><br />

### License Plate Detection

To detect License Plate from the Image, we used YOLOV3.<br />
Used YOLOV3 to detect only 1 class ["LP"].<br />
To detect license plate, used pre-trained weights for License plate detetction.<br />
Pre-trained weights for License Plate detection can be downloaded from https://www.kaggle.com/achrafkhazri/yolo-weights-for-licence-plate-detector<br /><br />

Original Image used as a sample is shown below :-<br /><br />
<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Original.jpg" width="400" height="300">
</div>

After processing the image :-<br /><br />
<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Processed.jpg" width="400" height="300">
</div>
After the License Plate is detected, we crop the license Plate and save the cropped version in Recognition folder.
Cropped License Plate :-
<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Plate.jpg" width="300" height="100">
</div>
