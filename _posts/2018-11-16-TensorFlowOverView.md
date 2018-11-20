---
layout:     post
title:      Tensorflow Study Note
subtitle:   Overview for Tensorflow NAIVE
date:       2018-11-16
author:    Chester
header-img: img/failure.jpg
catalog: true
tags:
    Project
    DeepLearning
   Tensorflow
---
## Hello World
Tensorflow progress day to day. In the first case I try to understand is MXNT image classification. 


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


## Some stupid Question
#### What's different between operation and layer?


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY4NjQ1MDQ4MCw2MjYyNzUwMjIsNTY3Mz
M2ODczLDM0MDA5MzkzMV19
-->