---
layout:     post
title:      ML &  Desgin pattern
subtitle:   To answer the gap between SW/DS
date:       2020-04-01
author:    Chester
catalog: true
tags:
	-paper
---
# Motivation
How many design patterns? I guess there's limited number for that? Once you DS "How many different categories of ML question?" The number is very shocking. 24 or More.

Another issue which talked from other posts is  overdesign. 
1. Can I find out 3 different design patterns are more useful in ML application? 
2. When should we start to think of design patterns?
3. I can apply the the pesudo project for the exist desgin pattern. 

# Design patterns for Machine Learning Applications

This essay discuesses few different common SAs. 
- Model-View-Controller
- pipes and filterd model

and following 2 real problems:
- cancer cell detection
- intrusion detection


## Question behind paper
**What's the difference between filterd model and layered model?**
> |Model|PIPE/FILTERED|LAYERD|
> |-|-|-|
>|self-contained |Lower |Higher, only allow to use few common dependence|
>|Enviroments|It might need to work on same languages|Should be work alone. Well-defined interface|

** When should be aware of the design pattern?**
> TBH, this paper dosn't anwser my question at all. Can't tell what's the unique requirements difference between ML APPs/ DL APPs/ General APPs

#

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5NDU2NzQwMSw4Mjg2NDk4NzMsLTIwMT
Y5NjQ4NTQsMjEyODI0NDIsMjM0NDg3NzgxXX0=
-->