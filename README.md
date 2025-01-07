# Deep-Learning-Weather-Classification

#### Video Illustrating Weather Classification using Convolutional Neural Networks (CNN):


![Weather Classification GIF](https://github.com/pooja-singh702/Deep-Learning-Weather-Classification/blob/1f5781fccaaf2d4e7501014bab6b0669f55da5af/Untitled%20video%20-%20Made%20with%20Clipchamp%20(2).gif)

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
#### Model Summary
```


### 1. Model 1: Base Fully Connected Model
- **Architecture**: Multi-layer fully connected (dense) network with ReLU and Softmax activations.
- **Performance**: 
  - Training Accuracy: 67.81%
  - Test Accuracy: 72.95%

### 2. Model 2: CNN (Convolutional Neural Network)
- **Architecture**: Convolutional layers (Conv2D), MaxPooling layers, Dropout, and Flatten before the dense layers.
- **Weight Initialization**: Experimented with Gaussian weight initialization with standard deviations (0.44 and 0.01).
- **Optimizer**: Used Adam, SGD with momentum, and Nesterov.
- **Performance**: 
  - Training Accuracy: 94.09%
  - Test Accuracy: 78.42%

### 3. Model 3: CNN with Data Augmentation
- **Augmentation**: Applied data augmentation techniques (e.g., changing hue, saturation, rotation, etc.) to improve generalization.
- **Performance**:
  - Training Accuracy: 94.09%
  - Test Accuracy: 80.82%

### 4. Model 4: VGG19 Transfer Learning
- **Transfer Learning**: Used the pre-trained VGG19 model with added ReLU and Softmax activations for improved prediction accuracy.
- **Performance**:
  - Training Accuracy: 88.70%
  - Test Accuracy: 88.36%

### 5. Custom Architecture (Your Own Model)
- **Custom Network**: Developed your own model, adjusting the architecture, layer structures, and optimization strategies.
- **Outcome**: Significant improvement in accuracy from 21% to 82%.

```
#### FIG1: Accuracy scores of models , fig2: models with different Architectures 
![FIG 1 Accuracy Metrics for Different Cnn Architectures](https://github.com/user-attachments/assets/f5401cfc-ce55-4817-92d4-61e72e6b6d0a)
![FIG 2](https://github.com/user-attachments/assets/c60b02f5-f72d-4645-a6fd-9bafe811c64a)


#### Showig How Change in Architecture improved accuracy from 21% in arch1 to 83% in arch2:

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


#### Conclusions:
```
1. By adding an extra Max-Pooling after each convulational layer, keeping everything else from Arch 1 constant, accuracy for train and test data set increased substantially from ~22% to ~81% for test data whereas reducing a layer and one max pooling after 2 convulations decreased accuracy marginally.

2. Adding more convulational layers and max-pooling after each Conv will increase accuracy of model.
```
