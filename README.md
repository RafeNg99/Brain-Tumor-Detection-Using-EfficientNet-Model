# Brain-Tumor-Detection-Using-EfficientNet-Model

## Introduction
I have built a convolutional neural network (CNN) using EfficientNet-B4 in PyTorch to detect brain tumor in MRI images.

About the data:
The dataset consists of 155 images with brain tumor (designated here as 1) and 98 images without brain tumor (designated here as 0) and these images are split into three different sets: training, validation ans test sets. The original dataset is split into 80% training data and 20% test data. Then from the training set, it is split further into 80% training data and 20& validation data. You may find the images [here](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection)

## Data Augmentation & Pre-processing
Pre-process the images by normalizing their pixel values to ranging from approximately -2.12 to +2.64 as standardization for the Pretrained EfficientNet-B4 since it pretrained on ImageNet was trained with these normalization values. Data augmentation transforms or modifies each image to increase the diversity and variablility of the data which can help the model generalize better to unseen data and mitigate issues such as overfitting. The images are randomly flipped horizontally or vertically, randomly rotated and the brightness is either decreased or increased.

##B uilding the CNN Model
EfficientNet uses a compound scaling method to uniformly scale all dimensions of width, depth and resolution using a compound coefficient. This increases overall model performance while taking the changeable available resources into consideration. 

## Result
Since the dataset is imbalanced, using accuracy as the main metric will provide false interpretation of the model. Hence, recall will be used as the main classification metric as it is best to reduce false negatives or Type II error from occurring where patients with brain tumor are diagnosed as tumor-free. The recall obtained is 0.97 which is suitable to be deployed to classify whether a brain tumor is present or absent in the patient as chances of the model misclassifying a patient with brain tumor as tumor-free are low.
