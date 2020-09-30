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

<br />
After processing the image :-<br /><br />
<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Processed.jpg" width="400" height="300">
</div>

<br />
After the License Plate is detected, we crop the license Plate and save the cropped version in Recognition folder.<br />
Cropped License Plate :-<br /><br />
<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Plate.jpg" width="300" height="100">
</div>

### Digit Segmentation

After getting cropped image of the License plate, We segment different number present on the License plate.
Detected Contours on the License Plate. 
Sort them from Left -> Right order.
Mark the digits and number with a rectangle.

The segmented License Plate is shown below :-
<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Segmented.jpg" width="300" height="100">
</div>

### Digit Recognition

After Segmenting the Digits, we pass each of them from the trained cnn_classifier and predict the letters one by one.
Dataset used for training Digit_classifier is publicly available on Kaggle.
This dataset contains 36 classes for each alphabet and number.
Each class contains 1016 images corresponding to that class.
The Dataset can be downloaded from https://www.kaggle.com/passionoflife/english-typed-alphabets-and-numbers-dataset

Keras was used to build a CNN Model to detect the segmented letters.
The model was compiled with 
Loss = "Categorical_Crossentroy"
Optimizer = "Adam"

After the training, we achieved 94.87% training accuarcy.

Accuracy graph is shown below :-
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Recognition/Accuracy.png" width="500" height="300">

Loss graph is shown below :-
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Recognition/Loss.png" width="500" height="300">

The model detected the 9 out of 10 letters corrected.
Achieving 90% accuracy.

<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Predicted.png" width="300" height="100">
</div>
