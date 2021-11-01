[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/)
# Instance-segmentation-with-MaskRCNN-on-Custom-dataset
In this project, I trained an architecture of convolutional neural network that was published in 2019. This model is well suited for instance and semantic segmentation. There is an option to use pre-trained weights. However, I took a step further and trained my own model using one of 600 classes from the Google Open Images dataset. I chose cat as segmentation object, because I love my cat :).
# Dataset

![image](https://user-images.githubusercontent.com/55941654/139727096-a0068ba2-c1c7-4821-af39-f825743c15e7.png)

## A dataset of ~9 million varied images with rich annotations
The images are very diverse and often contain complex scenes with several objects (8.4 per image on average). It contains image-level labels annotations, object bounding boxes, object segmentations, visual relationships, localized narratives, and more.
For downloading images I use python libary which is <a href="https://pypi.org/project/openimages/">openimages</a>, for downloding particular class of the dataset.
I download the annotations in a xml format, so i should convert them to a bitmap format in order to enter them to MaskRCNN load_mask() function.
# What is Image Segmentation
The computer vision task Image Segmentation is the process of partitioning a digital image into multiple segments (sets of pixels, also known as image objects). This segmentation is used to locate objects and boundaries (lines, curves, etc.).

There are 2 main types of image segmentation that fall under Mask R-CNN:
<ul>
  <li>Semantic Segmentation</li>
  <li>Instance Segmentation</li>
</ul>

## Semantic Segmentation
Semantic segmentation classifies each pixel into a fixed set of categories without differentiating object instances. In other words, semantic segmentation deals with the identification/classification of similar objects as a single class from the pixel level.

![image](https://user-images.githubusercontent.com/55941654/139725568-3cdbccc5-ad0b-4d97-a77e-0afed6fbc093.png)

As shown in the image above, all objects were classified as a single entity (person). Semantic segmentation is otherwise known as background segmentation because it separates the subjects of the image from the background.

## Instance Segmentation
Instance Segmentation, or Instance Recognition, deals with the correct detection of all objects in an image while also precisely segmenting each instance. It is, therefore, the combination of object detection, object localization, and object classification. In other words, this type of segmentation goes further to give a clear distinction between each object classified as similar instances.

As shown in the example image above, for Instance Segmentation, all objects are persons, but this segmentation process separates each person as a single entity. Semantic segmentation is otherwise known as foreground segmentation because it accentuates the subjects of the image instead of the background.


# Mask RCNN
Mask R-CNN is a Convolutional Neural Network (CNN) and state-of-the-art in terms of image segmentation. This variant of a Deep Neural Network detects objects in an image and generates a high-quality segmentation mask for each instance.

![image](https://user-images.githubusercontent.com/55941654/139724945-bf7748e9-3d4a-4b7c-aa22-80c43e27daef.png)

Mask R-CNN was built using Faster R-CNN. While Faster R-CNN has 2 outputs for each candidate object, a class label and a bounding-box offset, Mask R-CNN is the addition of a third branch that outputs the object mask. The additional mask output is distinct from the class and box outputs, requiring the extraction of a much finer spatial layout of an object.

![image](https://user-images.githubusercontent.com/55941654/139726659-9c7ac678-da7f-4571-9bee-f90d576c5095.png)

Mask R-CNN is an extension of Faster R-CNN and works by adding a branch for predicting an object mask (Region of Interest) in parallel with the existing branch for bounding box recognition.


# Results
Some results after running for 1 epoch 

The model has some errors, which is ok because i trained it just for 1 epoch. 

![1](https://user-images.githubusercontent.com/55941654/139692582-d9fd1afa-5a14-45f3-b48d-979a44dd9d2f.jpg)

![2](https://user-images.githubusercontent.com/55941654/139692745-939dbdbf-f0ea-469a-86eb-9e9354d6d746.jpg)

![3](https://user-images.githubusercontent.com/55941654/139692760-4b95f9c5-fb79-4bb3-a09f-127039827c2d.jpg)

![4](https://user-images.githubusercontent.com/55941654/139692763-9942c441-fa35-4e28-b7f6-07048f8671ef.jpg)
