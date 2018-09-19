# MRI Scan Analysis
Detect abnormal conditions in the brain using a convolutional neural network from Tensorflow.

Developed using the [CodeLab](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/?utm_campaign=chrome_series_machinelearning_063016&utm_source=gdev&utm_medium=yt-desc#0) guide from Google.

Normal brain on the left. Brain with a tumor on the right.

![first jpg](https://user-images.githubusercontent.com/9091157/35780421-29b470a6-09a9-11e8-8748-1a701f876a41.jpg)  ![images 10](https://user-images.githubusercontent.com/9091157/35780431-48bd675a-09a9-11e8-842a-5585d8a74cd4.jpg)


## Requirements

* [Docker Toolbox](https://www.docker.com/products/docker-toolbox)

* Link docker image to Tensorflow library
```
 docker run -it -v ~/tf_files/brain_tumor:/tf_files/brain_tumor gcr.io/tensorflow/tensorflow:latest-devel
``` 

## Usage 

You just need to make a "classifier" directory with a directory "data" inside it with all your images.
```
 [any_path]/classifier/
 [any_path]/classifier/data
 [any_path]/classifier/data/normal_brain
 [any_path]/classifier/data/tumor_brain
```
 and then put your image on it. 
 This "classifier" directory will have your samples but also trained classifier after execution of "train.sh". 

## Train Process
 
Just type
```
 ./train.sh [any_path]/classifier
``` 


## Guess Process

Just type below command for a single guess. Only JPG files work currently.
```
 ./guess.sh [any_path]/classifier /filename.jpg
```


## Accuracy
```
# ./guess.sh /tf_files/brain_tumor/ /tf_files/Tester/tumor1.jpg
normal brain (score = 0.91513)
tumor brain (score = 0.08487)
```




