# Intelligent-Recycling-Algorithm
*Academic Project - Deep Learning in Vision*

The goal of this project is to create an algorithm that will recognize the different type of waste so it can be recycled correctly. This project has been inspired to help/imitate @OceanCleanUp and @Recycleye. In a first place we will use object detection algorithm, such as Mask RCNN architecture, to detect and classify trash images, use the model and apply to our custom dataset. Different layers of the algorythm must be retrained in order to get our results.

## Objective: 

<img src="https://github.com/NatchosR/Deep-Recycling/blob/main/images/output2_copy.png" width=50% height=20%>

Picture of trash detected using TACO's version of MaskRCNN

## Result:

<img src="https://github.com/NatchosR/Deep-Recycling/blob/main/images/bottles.png" width=70% height=70%>

Picture of trash detected in my living room using our simplified version [Simple_Trash](https://github.com/NatchosR/SimpleTrash).
> *Note: Due to the complexity of tuning MaskRCNN algorithm on the TACO dataset, we reduced the scope of our project to Simple_Trash, you can find [here](https://github.com/NatchosR/SimpleTrash). The objective is similar, except that we reduce the number of class, to only detect 'Bottles'. This project was 3 ECTS credit.*
## References:
**GitHub**
+ https://github.com/matterport/Mask_RCNN: We will use the pretrained model from this repository and then retrained it with our own trash classes/labels
+ https://github.com/pedropro/TACO: We will use this repository as inspirations. This repo consist in our absolute goal!
+ https://github.com/garythung/trashnet: We will use the data from this repository.

**Data**

Google drive folder: https://drive.google.com/drive/folders/1rBGwrHzXDPx0t1G2MpHyeYgLuO4w5fT4?usp=sharing
Contain:
+ dataset from trashnet project(https://github.com/garythung/trashnet)
+ pretrained model for Mask_RCNN(https://github.com/matterport/Mask_RCNN)
+ some random images for random predictions

## Strategy:

### 0. Explore Mask RCNN
Explore and understand Mask__RCNN model from Matterport, we need 3 key informations/concepts. 
1. How to load a custom dataset (picture size, DataLoader, ...)
2. How to custom/add classes to the model, so it can predict different trash category
3. Which model evaluation is in place, and how to implement a new one if not satisfied
4. What do we need to re-train, everything? Classifier only? What do we need for the training (annotation, class, segmentation, ...)?

### 1. Dataset/preprocess/loading
From the different data source, get annotations, labels, and more if needed (essentially https://github.com/garythung/trashnet and maybe https://github.com/pedropro/TACO). 
Process the data according to the model format and load the data so the model can interpret them.

### 2. Custom Mask
Implement new classes for different trash category. And potentially, new evaluation criteria, like IoU (intersection of Union), MAP (Mean Average Precision), or other evaluation estimator. 

### 3. Train the Network 
(...)

