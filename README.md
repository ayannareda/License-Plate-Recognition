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

After getting cropped image of the License plate, We segment different number present on the License plate.<br />
Detected Contours on the License Plate. <br />
Sort them from Left -> Right order.<br />
Mark the detected letters with a rectangle.<br />

The segmented License Plate is shown below :-<br />
<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Segmented.jpg" width="300" height="100">
</div>

### Digit Recognition

After Segmenting the Digits, we pass each of them from the trained cnn_classifier and predict the letters one by one.<br />
Dataset used for training Digit_classifier is publicly available on Kaggle.<br />
This dataset contains 36 classes for each alphabet and number.<br />
Each class contains 1016 images corresponding to that class.<br />
The Dataset can be downloaded from https://www.kaggle.com/passionoflife/english-typed-alphabets-and-numbers-dataset<br /><br />

Keras was used to build a CNN Model to detect the segmented letters.<br />
The model was compiled with <br />
Loss = "Categorical_Crossentroy"<br />
Optimizer = "Adam"<br /><br />

After the training, we achieved 94.87% training accuarcy.<br />

Accuracy graph is shown below :-<br />
<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Recognition/Accuracy.png" width="500" height="300">
</div>

Loss graph is shown below :-<br />
<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Recognition/Loss.png" width="500" height="300">
</div>

The model detected the 9 out of 10 letters corrected.<br />
Achieving 90% accuracy.<br /><br />

<div align="center">
<img src="https://github.com/gearhead0909/License-Plate-Recognition/blob/master/Predicted.png" width="300" height="100">
</div>
