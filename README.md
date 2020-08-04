# Images with Aesthetics and Emotions Dataset (IAE Dataset)  

  Aesthetics assessment and emotion recognition are two fundamental problems in user perception understanding. While the two tasks are correlated and mutually beneﬁcial, they are usually solved separately in existing studies. In order to do a better joint study on it, we extend a large scale emotion dataset by further manually rating the aesthetic qualities of images. To our best knowledge, the new dataset is the ﬁrst collection of images that are associated with both aesthetic and emotional labels. 
  
## Introduction
  We introduce a large scale dataset to facilitate multi-task learning for uniﬁed image aesthetics and emotion prediction. We refer to this dataset as the “Images with Aesthetics and Emotions”, or IAE for short. To our best knowledge, IAE is the ﬁrst collection of images associated with both aesthetic and emotional labels. Speciﬁcally, IAE is an extension of the earlier work[1], where 22,086 images are manually divided into eight emotion categories, i.e., amusement, anger, awe, contentment, disgust, excitement, fear, and sadness. Each category consists of more than 1,100 images.  
  We further rate the quality of these images from the aesthetic perspective. To ensure the quality and integrity of the rating process, ten volunteers were invited to rate each image with one of the four quality levels: Excellent (score 10), Good (score 7) , Fair (score 4) and Bad (score 1). The aesthetic quality of each image is measured by the average of the scores from individual raters, and thus takes values on the scale of 1 to 10. Similar to previous rating datasets [2], we ﬁnd that the average scores are well ﬁt by a Gaussian distribution. Then, images with average scores smaller than 5 were labeled as low quality, and the others were labeled as high quality. Finally, we identiﬁed xxxxx high-aesthetic and xxxxx low-aesthetic images, respectively.  
  Fig. 1 displays the number of high-aesthetic and low aesthetic images grouped on each emotional category. As can be seen, if images arouse positive emotions, they are more likely to have high-aesthetic quality; otherwise,they are more likely to be low-aesthetic ones. This phenomenon provides empirical support for our claim that aesthetic and emotional perceptions are correlated and interact with each other.

![image](https://github.com/zhenshen-mla/Series-Photo-Selection/blob/master/examples/structure.png)  

  
## Models
  * `/models/PAUnit.py`: implementation of Parallel Attention Unit;  
  * `/models/ResNet18.py`: baseline with resnet18 backbone;  
  * `/models/ResNet50.py`: baseline with resnet50 backbone;  
  * `/models/ResNet101.py`: baseline with resnet101 backbone;  
  * `/models/Inceptionv3.py`: baseline with Inception network;  
  * `/models/PAUnit.py`: resnet50 network with PAUnit;   
  
## Requirements  

  Python >= 3.6  
  numpy  
  PyTorch >= 1.0  
  torchvision  
  tensorboardX  
  sklearn  
  

## Installation
  1. Clone the repo:   
    ```
    git clone https://github.com/zhenshen-mla/Series-Photo-Selection.git   
    ```   
    ```
    cd Series-Photo-Selection  
    ```
  2. For custom dependencies:   
    ```
    pip install matplotlib tensorboardX sklearn   
    ```
## Usage   
  1. Download the dataset([Automatic triage for a photo series](https://phototriage.cs.princeton.edu/dataset.html)) and configure the data path.   
  2. Train the baseline with ResNet backbone:  
  ``` python train_resnet.py ```  
  3. Train the network with PAUnit:  
  ``` python train_pau.py ```  
