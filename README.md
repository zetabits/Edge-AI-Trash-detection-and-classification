# Edge-AI-Trash-detection-and-classification

## Description
We took garbage dataset of 2 classes (Bottles and Cans) from Kaggle for the training of FOMO (Faster Objects, More Objects) MobileNetV2 0.35 model, used for object detection, and deployed it on Arduino Nicla Vision. Our hardware is able to detect the plastic bottles and metal cans and is able to classify them. We used Edge impulse for the training purpose as it is very straight forward and does not require any coding, also it gives the tflite model which can be directly deployed on the edge devices. Arduino Nicla vision (Cortex-M7 480 MHz) is used because of its small size which can be deployed anywhere.

## Installation 
1. Dataset zip file is available in the repository, which can be downloaded.
2. Open Edge impulse and sign in into it.
3. Change the labelling method to bounding boxes
4. Select the target device, in our case, Arduino Nicla Vision (Cortex-M7 480 MHz)
5. If you want to collect data from your own hardware go to Devices and collect the data, we had data from the kaggle dataset which we uploaded and labelled
6. Go to data acquisition and upload the training data and testing data from the Data zip file in repo. Labelling is not required as it is already labelled so it will use the labels info from the file itself.
7. Go to Create Impulse, select the image size as 96 x 96 and select the Resize mode to 'Fit longest axis', add processing block and learning block and save impulse.
8. In the image section save parameters as RGB and save, then select generate features and features will be generated in few minutes.
9. Go to object detection and select specifications, training cycle: 80, Learning rate: 0.001, Data augmentation: yes, Profile int8 model: yes, validation size: 20%, select model as FOMO (Faster Objects, More Objects) MobileNetV2 0.35 and then start training.
10. Training will take 15-20 minutes and it will give a confusion matrix with F1 score.
11. Go to model testing and classify the test data, which will give the accuracy of the model, we got 85% accuracy for our model.
12. Go to deployment and choose OpenMV as deployment option and click on 'build' which will download your tflite model which can be deployed on your device using OpenMV.
13. 

## Results
![Alt text](fomo-int8-cm.png)       
Confusion Matrix of FOMO int8 model       

![Alt text](fomo-int8-accuracy.png)     
Accuracy of the FOMO int8 model on the test dataset (20%)       

## How to use the project

## Working of the Project
Youtube: https://youtu.be/8U-2VrPENp8?si=sKW4kywQF0OKIItJ

## Credits
[Ashhar Zaman](https://github.com/zetabits),
[Md Farhad Hussain](https://github.com/mfarhadhussain),
[Dinesh T](https://github.com/dinesh-tamilselvan)
