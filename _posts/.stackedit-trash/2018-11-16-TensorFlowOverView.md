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
###  Estimator



### Eager Execution
>Enabling eager execution changes how TensorFlow operations behave—now they immediately evaluate and return their values to Python.



# Low-Level Tensorflow
You might think of TensorFlow Core programs as consisting of two discrete sections:
1.  Building the computational graph (a  [`tf.Graph`](https://www.tensorflow.org/api_docs/python/tf/Graph)).
2.  Running the computational graph (using a  [`tf.Session`](https://www.tensorflow.org/api_docs/python/tf/Session)).
 

## Graph
- operation
	Node in whole graph. he nodes of the graph. Operations describe calculations that consume and produce tensors.
- tensor
	The edges in the graph. It represent value pass between tensor. Most of function will return tf.Tensors 
>**Important:** `tf.Tensors`  do not have values, they are just handles to elements in the computation graph.

在這邊我也很驚訝的表示, 原來computation graph 所認為的edge 和 node跟我直認知有所不同. Tensor


## Sessions
Start the conversation. 
Compare with daily life. We want to host a meeting. Operation is the schdule to decide what should be talked next. Session is the trigger to talk. Before the Session to collaberate environment and schdulde. We won't start to talk.
> If a [`tf.Graph`](https://www.tensorflow.org/api_docs/python/tf/Graph) is like a `.py` file, a [`tf.Session`](https://www.tensorflow.org/api_docs/python/tf/Session) is like the `python` executable.

```python
a = tf.constant(1) # tensor
b = tf.constant(2) # tensor
total = a + b # Grpah
sess = tf.Session() # define session-> define runtime enviroment
print(sess.run(total)) # Run~~~
```
### Feed data
 - ****placeholders**** is the the place let us put external data.
In the easy case, we can use sess.run(feed
 - [**tf.data**](https://www.tensorflow.org/api_docs/python/tf/data) are the preferred method of streaming data into a model.
## Layer
### Creating Layers
 - Dense
 - 
### Initial
```python
init = tf.global_variables_initializer()
sess.run(init)
```
### Executing
 
 - Training 
 - optimizer
 - Prediction
 - Loss

###　Folloing Question
#### What's different between tf.nn and tf.layer ?
Ans: They are different level objects. tf.nn usually has more features and options than layer. They can co-work together.

# Common function
## Operation
#### tf.reduce_sum()
#### tf.reduce_mean()
#### tf.concat()
#### .eval()

## Visualization-Tensorboard
Here's the resource you need to understand how to add tensorboard on Colab and you orginal project
- [Use Tensorboard in Google Colab](https://medium.com/@tommytao_54597/use-tensorboard-in-google-colab-16b4bb9812a6)
- [Graph visualization](https://www.tensorflow.org/guide/graph_viz)
- [Tensorflow log file generate](https://www.tensorflow.org/guide/summaries_and_tensorboard)
### Initial Tensorboard
It's a little bit different to creare writer handler in Colab.
Don't forget to instal tensorboardcolab first:
**!pip install tensorboardcolab**
```python
import tensorboardcolab
tbc=tensorboardcolab.TensorBoardColab()
summary_writer = tbc.get_writer()
summary_writer.add_graph(sess.graph)
```
![](https://lh3.googleusercontent.com/pvyHKus6bAaH5I7BliizsIPg5hXJlGr63ix_jxfWSfmiP3Ifdyq-Ca7vmqcqeKTen53tvWLB482l "Raw Graph without proper naming")
### Naming Scope



### Hyperparameter Visual
### Embedding 
1. PCA visualize
3. T-SNE visualize

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






<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NzQ5NjUxNTldfQ==
-->