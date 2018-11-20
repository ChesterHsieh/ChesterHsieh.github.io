---
layout:     post
title:      Tensorflow Study Note
subtitle:   Overview for Tensorflow NAIVE
date:       2018-11-16
author:    Chester
header-img: 
catalog: true
tags:
    Project
    DeepLearning
   Tensorflow
---
## Prerequisite
This article is try to bring those who has basic knowledge about the deep learning and neural network. I strongly recommend the [course](https://www.coursera.org/specializations/deep-learning) for deep learning.

While I want to implement side project, I realize I don't know how to start. Here's I play the role to explore Tensorflow. Hope  you can get some idea form this. 

## Hello World
Tensorflow progress day to day. In the first case I try to understand is MNIST image classification. It's  hello world case for first deep learning class

####
```python
mnist = tf.keras.datasets.mnist ## Dowload the file into varible


(x_train, y_train),(x_test, y_test) = mnist.load_data()
x_train, x_test = x_train / 255.0, x_test / 255.0

model = tf.keras.models.Sequential([
  tf.keras.layers.Flatten(),
  tf.keras.layers.Dense(512, activation=tf.nn.relu),
  tf.keras.layers.Dropout(0.2),
  tf.keras.layers.Dense(10, activation=tf.nn.softmax)
])
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

model.fit(x_train, y_train, epochs=5)
model.evaluate(x_test, y_test)
```
#### Build Model

 1. build layer
 2. decide the compile

#### Training

 1. epochs
	 Only one parameter is enough to set this
2. evaluation
	Follow the metrics decide in compile

#### Following Question

 1. How we tuning the model for next step
 2. How about more complicated problem for doing this?
## High Level Tool
#### Eager Execution
>Enabling eager execution changes how TensorFlow operations behave—now they immediately evaluate and return their values to Python.

#### 


## Graph
#### Operation


#### dataflow graph
Actually the graph is how we desing the layer and all prepocessing function. Tensorflow use graph to represent whole model
![](https://www.tensorflow.org/images/tensors_flowing.gif?hl=zh-cn)

Need to notice that, graph is low-level part of Tensorflow. Estimator and Keras are trying to put hide the details of graphs and sessions from the end user.

Here's the advantage to use dataflow:

> - Parallelism. By using explicit edges to represent dependencies between operations, it is easy for the system to identify operations that can execute in parallel.

透過這樣的表示, 系統可以更容易判斷是否可以平行運算. 我對這邊的系統有些微存疑. 可能後續章節會提到.Friday, 16. November 2018 02:32PM 

>- Distributed execution. By using explicit edges to represent the values that flow between operations, it is possible for TensorFlow to partition your program across multiple devices (CPUs, GPUs, and TPUs) attached to different machines. TensorFlow inserts the necessary communication and coordination between devices.

可以在不同運算單元上作Switch
> - Compilation. TensorFlow's XLA compiler can use the information in your dataflow graph to generate faster code, for example, by fusing together adjacent operations.


>- Portability. The dataflow graph is a language-independent representation of the code in your model. You can build a dataflow graph in Python, store it in a SavedModel, and restore it in a C++ program for low-latency inference.

成功的達成Concept complex but code easy

## tf.Graph

#### Building a tf.Graph
#### Sessions
Start the conversation. 
Compare with daily life. We want to host a meeting. Operation is the schdule to decide what should be talked next. Session is the trigger to talk. Before the Session to collaberate environment and schdulde. We won't start to talk.




## Workshop Case Study
[Translation](https://colab.research.google.com/github/tensorflow/tensorflow/blob/master/tensorflow/contrib/eager/python/examples/nmt_with_attention/nmt_with_attention.ipynb)

####
In this sample code, tensorflow team build up an training case for Spanish <-> English translation. It cover couple important concept:
- Seq2Seq
- Attention model
#### Attention model
#### 






## Some stupid Question
#### What's different between operation and layer?



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgwNjE2MjY0NCw5ODQxODAxNzIsMTQ5OT
kwODQ1MywxODY5ODI4MTYzLDk4NTY4NTEyLC0xNjM2NjkwMzk4
LDYyNjI3NTAyMiw1NjczMzY4NzMsMzQwMDkzOTMxXX0=
-->