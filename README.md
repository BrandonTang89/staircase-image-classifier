# staircase-image-classifier
A neural network to detect and classify staircases in images.

Try it out here: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/BrandonTang89/Staircase-Image-Classifier/master?filepath=Stairs_Prediction_jsonnpy.ipynb)

### Classes
1. Curved
2. Straight
3. Negative

### Dataset
The 1000+ images of each class. The images are a combination of videos taken and images from the internet.

### Network Architecture
The network uses a pretrained version of Google's Inception-ResNet-v2 with an additional average global pooling and 2 dense layers attached at the end to modify it for having 3 classes

The network is compiled with 'adam' optimizer and uses 'categorical-crossentropy' as its loss function.

### Training
1. The new layers were trained for 5 epoches
2. Layers > 271 (above the reduction a block) are trained for 20 epoches

### Results and Evaulation
<pre>
Accuracy Stats
Train Accuracy: 99.26 %
Validation Accuracy: 92.79 %
Test Accuracy: 95.87 %

Loss Stats
Train Loss: 0.024
Validation Loss: 0.192
Test Loss: 0.186
</pre>
