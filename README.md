# Traffic-Image-Segmentation
## Deep Learning project for sematic segmentation of traffic images. Part of a larger project to aid self-driving cars.


## Overview - 
In this project, I aim to build a Keras and Tenserflow based model to help segment out different objects that are present in the image. 
This project is a minor project, which forms a part of a larger project to aid self-driving cars. Its incredibly important for the AI technology running an autonomous vehicle, to be able to differentiate between various objects in the images captured by the vehicle's cameras. Before the software decides what to do with the data being collected by the vehicle, it needs to know where the objects like trees, road, other cars, buildings etc are. For this, we need to be able to perform sematic segmentation of the images.
This project aims to do just that.

## Dataset - 
The dataset for this project was available at https://www.kaggle.com/kumaresanmanickavelu/data and contains 5 different sets of data containing 1000 images each along with the corresponding labels. The objects in the image can be segmented into 13 different classes (you can find out more details about these classes and the colour assigned to its segments at https://carla.readthedocs.io/en/latest/cameras_and_sensors/#camera-semantic-segmentation ).

## Model Used -
I make use of a U-net here, as it is known to provide good results in image segmentation tasks. It consists of the following layers -

| Layer | Output Shape | No. of parameters |
|-------|--------------|-------------------|
| Conv2D | (None, 600, 800, 8) | 224 |
| Conv2D | (None, 600, 800, 8) | 584 |
| MaxPooling2D | (None, 300, 400, 8) | 0 |
| Conv2D | (None, 300, 400, 16) | 1168 |
| Conv2D | (None, 300, 400, 16) | 2320 |
| MaxPooling2D | (None, 150, 200, 16) | 0 |
| Conv2D | (None, 150, 200, 32) | 4640 |
| Conv2D | (None, 150, 200, 32) | 9248 |
| MaxPooling2D | (None, 75, 100, 32) | 0 |
| Conv2D | (None, 75, 100, 64) | 18496 |
| Conv2D | (None, 75, 100, 64) | 36928 |
| Conv2DTrans  | (None, 150, 200, 64) | 16448 |
| Concatenate | (None, 150, 200, 96) | 0 |
| Conv2D | (None, 150, 200, 32) | 27680  |
| Conv2D | (None, 150, 200, 32) | 9248 |
| Conv2DTrans | (None, 300, 400, 32) | 4128 |
| Concatenate | (None, 300, 400, 48) | 0 |
| Conv2D | (None, 300, 400, 16) | 6928 |
| Conv2D | (None, 300, 400, 16) | 2320 |
| Conv2DTrans | (None, 600, 800, 16) | 1040 |
| Concatenate | (None, 600, 800, 24) | 0 |
| Conv2D | (None, 600, 800, 8) | 1736 |
| Conv2D | (None, 600, 800, 8) | 584 |
| Conv2D | (None, 600, 800, 1) | 9 |

Total parameters = 143,729 

All the parameters are trainable.




### NOTE - Due to speed and memory restrictions, this model was trained to just identify and segment the road from the image, rather than all the objects in the image.



## Training Results - 

![Screenshot (107)](https://user-images.githubusercontent.com/46377211/65821860-04159200-e259-11e9-836b-f804bb358ca4.png)

