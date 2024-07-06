# Label-Propagation

The aim is to create a model for the task of singer classification. The requirements are as follows:
1) It should correctly label all the unlabelled files in the dataset
2) If a file of a new singer is introducted, the embeddings to this file should be far away from the embeddings of the existing singers

## Dataset

The dataset contains a total of around 17k audio files of which around 2k are labeled. There are a total of 200+ singers in this. 
For simplification, I will consider a total of 70 singers - 7 files in train set
Gold set(Test set) - rest of labeled files + a few files downloaded from YouTube

## A simple approach

Trained a simple ResNet18 model to analyze the data. 

Used the pre-trained model of ResNet18 trained on images - since this is task for Singer Classification, using a state of the art model for Singer Classification might lead to better results

**For training, mel-spectrograms of audio files are used everywhere**

## SOTA model

Trained the SOTA model in [Singer Identity Representation Learning using Self-Supervised Techniques](https://hal.science/hal-04186048v1)

1) Implemented the model using only contrastive loss (Completely self-supvervised)
2) Since model was overfitting, tried using kfold cross validation
3) Implemented the model using contrastive loss + supervised loss

#### Observation -

F1 score decreased in the model which used contrastive + supervised loss. The reason for the decrease may be that the feature space shaped by contrastive loss may not align well with the decision boundaries needed for classification.

## Label Propagation

Performed label propagation on the model from [Label Propagation for Deep Semi-supervised Learning](https://openaccess.thecvf.com/content_CVPR_2019/papers/Iscen_Label_Propagation_for_Deep_Semi-Supervised_Learning_CVPR_2019_paper.pdf)

## Clustering

Extracted embeddings of mel-spectrograms and performed kmeans clustering. Using the clustering loss, trained the model.
