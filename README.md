# Deep-Learning-Weather-Classification

Video Illustrating Weather Prediction using Convolutional Neural Networks (CNN):

![Description of GIF](https://github.com/pooja-singh702/Deep-Learning-Weather-Classification/blob/1f5781fccaaf2d4e7501014bab6b0669f55da5af/Untitled%20video%20-%20Made%20with%20Clipchamp%20(2).gif){: width="1920" height="1080"}

![Weather Classification GIF](https://github.com/pooja-singh702/Deep-Learning-Weather-Classification/blob/main/Untitled%20video%20-%20Made%20with%20Clipchamp.gif)

#### Brief Description of data & objectives:
```
A deep learning project that utilizes Convolutional Neural Networks (CNN) to predict weather conditions (e.g., rain, fog) based on historical weather data (temperature, humidity, wind speed). The Main objective of neural network project is to analyze and identify behavior of Deep learning techniques on weather data set. Given current changes in climate and spontaneous change in weather conditions, an attempt is being made to see if deep learning can identify any changes such as sudden rains or fog approaching to make better decisions.
```

#### Data Structure and Preprocessing

```
The dataset consists of 1,528 weather images, categorized into five classes: cloudy, foggy, shiny, rainy, and sunrise. Each class is stored in its own folder, with images labeled according to the respective folder name. The dataset structure is as follows:

cloudy/
foggy/
shiny/
rainy/
sunrise/
Each image in these folders is labeled based on its class folder.

```

#### Data Processing

```
Images are resized to 300x300 pixels to standardize their dimensions for input into the Convolutional Neural Network (CNN).
img_read = cv2.resize(img_read, (300, 300))
This ensures all images are of consistent size, allowing the CNN to process them effectively.

```
#### Labeling

```
Labels are assigned to images based on the folder name they are stored in. For example, images in the cloudy folder are labeled as cloudy. This automated labeling system ensures that each image is paired with the correct weather condition.

```

#### Color Channel Adjustment

```
Since OpenCV loads images in BGR format, but CNNs typically expect RGB, we convert the images by swapping the color channels:
(b, g, r) = cv2.split(img_read)  # Split into Blue, Green, Red channels
img_read = cv2.merge([r, g, b])  # Merge into Red, Green, Blue
This step ensures that the images are correctly formatted for better model performance.

```

#### 
![Accuracy Metrics for Different Cnn Architectures](https://github.com/user-attachments/assets/f5401cfc-ce55-4817-92d4-61e72e6b6d0a)
![Image](https://github.com/user-attachments/assets/c60b02f5-f72d-4645-a6fd-9bafe811c64a)


Showig How Change in Architecture improved accuracy from 21% in arch1 to 83% in arch2:

#### This Fig Shows Architecture that Improved Accuracy:
```
Layer (type)                Output Shape              Param #   
=================================================================
 conv2d_2 (Conv2D)           (None, 296, 296, 32)      2432      
                                                                 
 max_pooling2d_1 (MaxPooling  (None, 148, 148, 32)     0         
 2D)                                                             
                                                                 
 conv2d_3 (Conv2D)           (None, 148, 148, 16)      4624      
                                                                 
 max_pooling2d_2 (MaxPooling  (None, 74, 74, 16)       0         
 2D)                                                             
                                                                 
 dropout_4 (Dropout)         (None, 74, 74, 16)        0         
                                                                 
 flatten_1 (Flatten)         (None, 87616)             0         
                                                                 
 dense_4 (Dense)             (None, 128)               11214976  
                                                                 
 dropout_5 (Dropout)         (None, 128)               0         
                                                                 
 dense_5 (Dense)             (None, 5)                 645       
                                                             
```


Conclusions:
```
1. By adding an extra Max-Pooling after each convulational layer, keeping everything else from Arch 1 constant, accuracy for train and test data set increased substantially from ~22% to ~81% for test data whereas reducing a layer and one max pooling after 2 convulations decreased accuracy marginally.

2. Adding more convulational layers and max-pooling after each Conv will increase accuracy of model.
```
