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

Some Patterns:
- Layer
- Pipe/filter
- Event bus
- Model view control 
- client- server
- broker

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
>|Enviroments|It might need to work on same languages|Should be work alone. Well-defined interface

**When should be aware of the design pattern?**

> TBH, this paper dosn't anwser my question at all. Can't tell what's the unique requirements difference between ML APPs/ DL APPs/ General APPs


# [Scikit-Learn Design Principles](https://towardsdatascience.com/scikit-learn-design-principles-d1371958059b)

This post doesn't relate to the design patterns though. It enlight my mind about the advanced coding skill.
> importance of programming to an interface, not an implementation.

Sciket-learn has very strong user example and default case. In most of first-trial, we can leave a plenty of configurations empties and get some resaonable(inperfect) result.
> Good design must start from easy example and default settings.

## Extensibility Through Duck-Typing

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA3OTIzMTg0MywtNDI5OTU2NTMwLDExMj
YwOTM0MjEsLTIwNDQzMjgxMDUsLTE0NDk1MTk0NTcsLTEyNDc0
NDU5MTcsODI4NjQ5ODczLC0yMDE2OTY0ODU0LDIxMjgyNDQyLD
IzNDQ4Nzc4MV19
-->