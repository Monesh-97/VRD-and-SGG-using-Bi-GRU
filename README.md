# Visual Relationship Detection with Language Priors

whole the things i forked from the https://github.com/Prof-Lu-Cewu/Visual-Relationship-Detection and additionally just run the programs files in colab.

Cewu Lu\*, Ranjay Krishna\*, Michael Bernstein, Li Fei-Fei, 
European Conference on Computer Vision (ECCV), 2016, 
**(oral)**. (\* = indicates equal contribution)

## Citation
```
@InProceedings{lu2016visual,
   title = {Visual Relationship Detection with Language Priors},
   author = {Lu, Cewu and Krishna, Ranjay and Bernstein, Michael and Fei-Fei, Li},
   booktitle = {European Conference on Computer Vision},
   year = {2016},
 }
 ```

## Introduction
Visual Relationship Detection is a task where the input is a simple image and the model is supposed to predict a set of relationships that are true about the image. There relationships are in the form of <subject-predicate-object>. Visual Relationship Detection is a natural extension to object detection where we now not only detect the objects in an image but predict how they are interacting with one another.

Detailed description of the task and our model is provided in [our paper at ECCV 2016](http://cs.stanford.edu/people/ranjaykrishna/vrd/).

##Licence

This software is being made available for research purpose only. Check LICENSE file for details.

## System Requirements
This software is tested on Ubuntu 14.04 LTS (64bit).

MATLAB (tested with 2014b on 64-bit Linux)
[Caffe](http://caffe.berkeleyvision.org/installation.html#prequequisites)

## Demo
To view some example results, you can directly run demo.m on about 50 images. The results will be saved in "results/demo" and "results/demo_zeroShot".
```
>> run demo.m;
```

## Relationship and Preidcate Detection 
To detect relationship in our [dataset](http://cs.stanford.edu/people/ranjaykrishna/vrd/), please run `relationship_phrase_detection.m`. Each image will have a set of relationships (<subject, predicate, object>) predicted with bounding boxes for the subjects and objects as bounding boxes. The relationship detection results (including zero-shot preformance) will also be reported. Predicate detection results can be obtained by running `predicate_detection.m`. 

For each image, we provide our VGG based object detection results (object category, confidence score and bounding boxes) and CNN scores on the union of the bounding boxes of pairs of participating objects in each relationship. You can also train your own object detection models using newer state of the art architechures like ResNet. 
```
>> run relationship_phrase_detection.m;
>> run predicate_detection.m;
```

## Run Demo file in colab :
Follow the following steps to run the program :

1.clone the repository. 
2.move out the files according to the screenshot shows the places.
3.install octave using. 
```
!apt install octave
```
4.open up the demo.m file and copy the matlab program.
5.paste under this command,
```
%%writefile your_filename.m
```
6.Now Run this commmand,
```
!octave -W your_filename.m
```
note: it will run contiously for all the images.
7. For to save the results in python format,
```
a = !octave -W your_filename.m
print(a)
```
Thankyou sir,(https://github.com/Prof-Lu-Cewu)
