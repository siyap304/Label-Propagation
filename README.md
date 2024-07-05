# Label-Propagation

My aim is to create a model for the task of singer classification. The requirements are as follows:
1) It should correctly label all the unlabelled files in the dataset
2) If a file of a new singer is introducted, the embeddings to this file should be far away from the embeddings of the existing singers

## Dataset

My dataset contains a total of around 17k audio files of which around 2k are labeled. There are a total of 200+ singers in this. 
For simplification, I will consider a total of 70 singers - 7 files in train set
Gold set(Test set) - rest of labeled files + a few files downloaded from YouTube

## A simple approach

Trained a simple ResNet18 model to analyze the data.

Used the pre-trained model of ResNet18 trained on images - since this is task for Singer Classification, using a state of the art model for Singer Classification might lead to better results

## SOTA model

Trained the SOTA model in [Singer Identity Representation Learning using Self-Supervised Techniques](https://hal.science/hal-04186048v1)



## Label Propagation

## Clustering