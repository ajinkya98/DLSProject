# DLSProject
## This project consists of three main parts:
1. A base Deep Learning model is the UNet model which we have trained for multiclass Image segmenatation. The dataset used for the model training is the DeepGlobeDataset picked up from Kaggle. The dataset comprises of 813 train images, 172 validation images and 171 test images. Unfortunately the validation images donot have masks. Thus we merged it into the testset and scoped out a small portion of the dataset to be the validation set. The metric used to gauge the validation is IOU. Due to large size of the images we downsized the images from 2448 to 1024 and 512 and ran experiments for both. Ran each of them for 100 epochs with the Adam optimizer and a learning rate of 0.01.
2. The second portion of the project includes a transfer learning task. Here we take a new dataset wherein we used our baseline model trained over the land cover classificaiton for landslide detection. Here we freeze the weights and train only the last layer wherein the num classes will be changed from 7 to 1 as its a binary classification for every pixel. After training for 50 epochs we were able to get some decent predictions for the landslide masks. Here we only used the portion of the dataset where the landslide images and masks were present.
3. In this portion we have used the pretrianed baseline model to classify images wehether they have have a landslide in them or not. We were able to get accuracy of around 70 -75 % for this task. Here we used the same landslide dataset wherein we used two labels land slide and non landslide.

Tools used - Python and Pytorch.

All results are in the notebook files.
