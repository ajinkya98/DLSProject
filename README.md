# Satellite Image Segmentation, Prediction & Natural Event Detection
## This project consists of three main parts:
1. A base Deep Learning model is the UNet model which we have trained for multiclass Image segmenatation. The dataset used for the model training is the DeepGlobeDataset picked up from Kaggle. The dataset comprises of 813 train images, 172 validation images and 171 test images. Unfortunately the validation images donot have masks. Thus we merged it into the testset and scoped out a small portion of the dataset to be the validation set. The metric used to gauge the validation is IOU. Due to large size of the images we downsized the images from 2448 to 1024 and 512 and ran experiments for both. Ran each of them for 100 epochs with the Adam optimizer and a learning rate of 0.01.
2. The second portion of the project includes a transfer learning task. Here we take a new dataset wherein we used our baseline model trained over the land cover classificaiton for landslide detection. Here we freeze the weights and train only the last layer wherein the num classes will be changed from 7 to 1 as its a binary classification for every pixel. After training for 50 epochs we were able to get some decent predictions for the landslide masks. Here we only used the portion of the dataset where the landslide images and masks were present.
3. In this portion we have used the pretrianed baseline model to classify images wehether they have have a landslide in them or not. We were able to get accuracy of around 70 -75 % for this task. Here we used the same landslide dataset wherein we used two labels land slide and non landslide.

Tools used - Python and Pytorch.
## Results:
### Intersection Over union (IOU) Score for 60 Test Samples Tested for Image Segmentation:
![Capture](https://user-images.githubusercontent.com/32778343/153116591-9d57737f-ec65-48ff-8db6-dc6a124e2fcc.JPG)

### Real Satellite RGB Images:
![Capture2](https://user-images.githubusercontent.com/32778343/153116593-32cd15b7-1247-4644-8eac-990465029c38.JPG)

### Image Segmentations Predicted By the Unet Model for the above real satellite images:
![Capture3](https://user-images.githubusercontent.com/32778343/153116594-a56d00d5-206e-4326-add6-efc919e63161.JPG)

### Landslide Satellite Images from the Bijie-landslide-dataset:
![Capture4](https://user-images.githubusercontent.com/32778343/153116595-33407ee6-e110-48db-aa59-00f1f8425837.JPG)

### Predicted Image Segmentation for landslide images above using transfer learning from the Basline Unet Model:
![Capture5](https://user-images.githubusercontent.com/32778343/153116596-a62314ff-472b-4d71-b4ea-26150caa2ea6.JPG)

### Accuracy plot for the baseline model and the landslide model:
![Capture6](https://user-images.githubusercontent.com/32778343/153116597-55d20cfb-7945-4085-b421-a2de63343206.JPG)

### Loss Comparision between the baseline model and the landslide model: 
![Capture7](https://user-images.githubusercontent.com/32778343/153116598-2f448421-ac99-4106-8796-88fb0330d995.JPG)
