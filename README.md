# Deep-Learning-Weather-Classification

Illustrating Weather Classification Project:
![Image shows weather image as input and output as text as type of weather image it is]()
![Weather Classification GIF](https://github.com/pooja-singh702/Deep-Learning-Weather-Classification/blob/main/Untitled%20video%20-%20Made%20with%20Clipchamp.gif)



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
