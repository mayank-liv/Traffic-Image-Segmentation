# Traffic-Image-Segmentation
## Deep Learning project for sematic segmentation of traffic images. Part of a larger project to aid self-driving cars.


## Overview - 
In this project, I aim to build a Keras and Tenserflow based model to help segment out different objects that are present in the image. 
This project is a minor project, which forms a part of a larger project to aid self-driving cars. Its incredibly important for the AI technology running an autonomous vehicle, to be able to differentiate between various objects in the images captured by the vehicle's cameras. Before the software decides what to do with the data being collected by the vehicle, it needs to know where the objects like trees, road, other cars, buildings etc are. For this, we need to be able to perform sematic segmentation of the images.
This project aims to do just that.

## Dataset - 
The dataset for this project was available at https://www.kaggle.com/kumaresanmanickavelu/data and contains 5 different sets of data containing 1000 images each along with the corresponding labels. The objects in the image can be segmented into 13 different classes (you can find out more details about these classes and the colour assigned to its segments at https://carla.readthedocs.io/en/latest/cameras_and_sensors/#camera-semantic-segmentation ).

## Model Used -
I make use of a U-net here, as it is known to provide good results in image segmentation tasks. 

| | |
------
| | |
| | | 
| | |
| | |
| | | 
| | |
