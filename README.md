# staircase-image-classifier
A neural network to detect and classify staircases in images.

Try out Inception-Resnetv2 here: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/BrandonTang89/Staircase-Image-Classifier/master?filepath=Stairs_Prediction_jsonnpy.ipynb)

Try out MobileNetv2 here: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/BrandonTang89/Staircase-Image-Classifier/master?filepath=Stairs_Prediction_mobilenetv2_h5.ipynb)
## Quick Install
Installing Dependencies (on python 3.6):
<pre>pip install -r requirements.txt</pre>

Installing Jupyter
<pre>pip install jupyter</pre>

Running Jupyter
<pre>jupyter notebook</pre>

## Details on Neural Network
### Classes
1. Left Curved
2. Right Curved
3. Straight
4. Negative

### Dataset
The ~1000 images of each class. The images are a combination of videos taken and images from the internet.

### Network Architecture
The network uses a pretrained version of Google's Inception-ResNet-v2 with an additional average global pooling and 2 dense layers attached at the end to modify it for having 3 classes

The network is compiled with 'adam' optimizer and uses 'categorical-crossentropy' as its loss function.

### Training
1. The new layers were trained for 5 epoches
2. Layers > 271 (above the reduction a block) are trained for 20 epoches with early stopping (val loss, patience=5)

### Results and Evaulation
<pre>
Accuracy Stats
Train Accuracy: 98.12 %
Validation Accuracy: 93.12 %
Test Accuracy: 88.29 %

Average Prediction Run-Time: 0.06131466422184905s
</pre>

<table>
  <tr>
    <td>True Class / Predicted Class</td>
    <td>curved_left</td>
    <td>curved_right</td>
    <td>negative</td>
    <td>straight</td>
  </tr>
  <tr>
    <td>curved_left</td>
    <td>92</td>
    <td>18</td>
    <td>1</td>
    <td>3</td>
  </tr>
  <tr>
    <td>curved_right</td>
    <td>16</td>
    <td>92</td>
    <td>0</td>
    <td>6</td>
  </tr>
  <tr>
    <td>negative</td>
    <td>0</td>
    <td>0</td>
    <td>89</td>
    <td>1</td>
  </tr>
  <tr>
    <td>straight</td>
    <td>1</td>
    <td>1</td>
    <td>1</td>
    <td>89</td>
  </tr>
</table>
  
