---
layout:     post
title:     ML &  Desgin pattern
subtitle: To answer the gap between SW/DS
date:       2020-04-01
author:    Chester
header-img: 
catalog: true
tags:
   Book
   paper
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

[Abstract factory](https://en.wikipedia.org/wiki/Abstract_factory_pattern "Abstract factory pattern") groups object factories that have a common theme.
> **_Estimator_**, **_Predictor_**, and **_Transformer_**. Importantly and crucially these interfaces are complimentary


Extensibility Through Duck-Typing

>A programming style which does not look at an object’s type to determine if it has the right interface; instead, the method or attribute is simply called or used (“If it looks like a duck and quacks like a duck, it must be a duck.”) By emphasizing interfaces rather than specific types, well-designed code improves its flexibility by allowing polymorphic substitution. Duck-typing avoids tests using [`type()`](https://docs.python.org/3/library/functions.html#type "type") or [`isinstance()`](https://docs.python.org/3/library/functions.html#isinstance "isinstance"). (Note, however, that duck-typing can be complemented with [abstract base classes](https://docs.python.org/3/glossary.html#term-abstract-base-class).) Instead, it typically employs [`hasattr()`](https://docs.python.org/3/library/functions.html#hasattr "hasattr") tests or [EAFP](https://docs.python.org/3/glossary.html#term-eafp) programming.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzOTkwMjEwNzIsMTQyMjYzMTIwOCwtND
I5OTU2NTMwLDExMjYwOTM0MjEsLTIwNDQzMjgxMDUsLTE0NDk1
MTk0NTcsLTEyNDc0NDU5MTcsODI4NjQ5ODczLC0yMDE2OTY0OD
U0LDIxMjgyNDQyLDIzNDQ4Nzc4MV19
-->