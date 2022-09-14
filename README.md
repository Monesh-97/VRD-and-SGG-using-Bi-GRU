# Visual-Relationship-Detection-and-Scene-Graph-Generation-using-Bi-Directional-Gated-Recurren


## Introduction
Visual relationship detection is an intermediate image understanding task that detects two objects and classifies a predicate that explains the relationship between two objects in an image. Relations among entities play a central role in image understanding. Due to the complexity of modeling (subject, predicate, object) relation triplets, it is crucial to develop a model that cannot only recognize seen relations, but also generalize to unseen cases. Inspired by a previously proposed visual translation embedding model,the context-augmented translation embedding model that can capture both common and rare relations. The previous Visual translation embedding model maps entities and predicates into a low-dimensional embedding vector space where the predicate is interpreted as a translation vector between the embedded features of the bounding box regions of the subject and the object. This model additionally incorporates the contextual information captured by the bounding box of the union of the subject and the object, and learns the embeddings guided by the constraint predicate,union(subject, object). In addition to the framework combined with a language model that learns which relationships are more suitable between pairs of object classes. The model solves the scene graph inference problem using the standard Bi-GRU model and learns to iteratively improve its predictions. Our joint model can take advantage of contextual cues to make better predictions on objects and their relationships from an image.In this work, it is explicitly model the objects and their relationships using scene graphs, a visually-grounded graphical structure of an image. Where in the graph the node represents the objects and the directed vertex represents the relationship among the nodes. The experiments show that our model significantly outperforms previous methods on generating scene graphs using Visual Genome dataset.
## Architecture 
![image](https://user-images.githubusercontent.com/42969032/190064714-38fc1fd7-ab3a-4b99-9427-853ec0252568.png)







## System Requirements
This software is tested on Ubuntu 14.04 LTS (64bit) and Google Colab.

MATLAB (tested with 2014b on 64-bit Linux)




## Relationship and Preidcate Detection 
To detect relationship in our [dataset](http://cs.stanford.edu/people/ranjaykrishna/vrd/), please run `relationship_phrase_detection.m`. Each image will have a set of relationships (<subject, predicate, object>) predicted with bounding boxes for the subjects and objects as bounding boxes. The relationship detection results (including zero-shot preformance) will also be reported. Predicate detection results can be obtained by running `predicate_detection.m`. 

For each image, we provide our VGG based object detection results (object category, confidence score and bounding boxes) and CNN scores on the union of the bounding boxes of pairs of participating objects in each relationship. You can also train your own object detection models using newer state of the art architechures like ResNet. 
## I. Demo
First Unzip the Project_Final.zip file where you can get the Project_Final.ipython file to see the programs results and splited each module outputs with the corresponding stepwise order.
To view some example results, you can directly run Project_final.ipynb
```
>>scc=get_scene_graph(image_id,images='/content/visual_genome_python_driver/visual_genome/data', image_data_dir='/content/visual_genome_python_driver/visual_genome/data/by-id/',synset_file='/content/visual_genome_python_driver/visual_genome/data/synsets.json')

>>print(scc.objects)
>>print(scc.relationships)
```

## II. Demo for to Run mat file in colab :
Follow the following steps to run the program :

1.clone the repository. 
2.move out the files according to the screenshot shows the places.
3.install octave  in colab using. 
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
# Final Output :
![image](https://user-images.githubusercontent.com/42969032/190064866-e67b0f02-d036-4467-8763-0306f50bdeb3.png)

![image](https://user-images.githubusercontent.com/42969032/190064564-32fd1cf9-4115-4212-ab9b-5237b9756455.png)
## Licence :

This software is being made available for research purpose only. Check LICENSE file for details.

@Thankyou  https://github.com/Prof-Lu-Cewu 
