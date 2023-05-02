# Object Detection in an Urban Environment

## The Goals of this Project:
*  Get Waymo's dataset
*  choose 3 pretrained models to work with
*  adjust the configuration of the models
*  Train the models
*  Test the model and output a video of the detection

## Pre-trained model from model zoo:
I chose 3 models to work with however, I was able to test only 2 as I can no longer access AWS cloud gateway. This is due to the credit limit.

* EfficientDet D1 640x640 (Default)
* SSD MobileNet V1 FPNLite 640x640
* SSD ResNet50 V1 FPN 640x640

## Experiment
I trained three different models for object detection. I started with the EfficientDet D1 640x640 model, aiming for an acceptable loss of 0.4 for both training and evaluation, and a DetectionBoxes_Precision/mAP with a value of 0.5. However, the performance was poor, with a value of 0.1.

Next, I tried training the SSD ResNet50 V1 FPN 640x640 (RetinaNet50) model, which is known to be one of the best detection models. Despite high expectations, the model performed poorly due to bad hyperparameter selection, resulting in a training loss of 0.5 and an evaluation loss of 0.95, indicating overfitting.

After learning from the mistakes made with the ResNet50 model, I trained the SSD MobileNet V1 FPNLite 640x640 model, which performed better than ResNet but still had poor performance due to either poor model architecture or incorrect hyperparameters. However, the model had higher mAP values and a better state for video output.

To improve performance, better hyperparameter tuning and potentially increasing the number of training steps may be necessary. Additionally, data augmentation could be added to improve the input data.

# Conclusion

While the SSD MobileNet V1 FPNLite 640x640 model performed the best, it is still considered poor for self-driving cars, where performance is critical. However, it is the fastest to implement and deploy.

For future work, I plan to improve the hyperparameters tuning of the SSD ResNet50 V1 FPN 640x640 (RetinaNet50) model to avoid overfitting. With these improvements, I believe this model will be the best for self-driving cars.
