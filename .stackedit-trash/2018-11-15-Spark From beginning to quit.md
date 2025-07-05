---
layout:     post
title:      Spark From beginning to quit
subtitle:   Try to learn Spark in most economic way
date:       2018-11-17
author:    Chester
header-img: img/makeup_title.jpeg
catalog: true
tags:
   Spark
---
# Intro
Memory anchor for the Spark beginner guide **Spark: The Definitive Guide**. 

# RDD 
Check the paper first.


## Read file

The .collect() method returns all the elements of the RDD to the
driver where it is serialized as a list.


## Transformation
#### map
## Operations
#### count()
#### take(# of smaple)
#### collect()
#### reduce
## Lazy Principle



## DataFrame


### Speed ISSUE

It is important to note that while, with DataFrames, PySpark is often
significantly faster, there are some exceptions. The most prominent one
is the use of Python UDFs, which results in round-trip communication
between Python and the JVM. Note, this would be the worst-case
scenario which would be similar if the compute was done on RDDs

### No map here :(
Instead to use map or apply



### API CheetSheet
![](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/PySpark_SQL_Cheat_Sheet_Python.pdf)
# Reference

 1. List item

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExOTM3ODk1ODVdfQ==
-->