---
layout: post
title: Class Activation Mapping
excerpt: ""
categories: [papers, tools]
tags: [deep learning, interpreting neural networks, general]
comments: true
author: alexeyev
---

[Trendy-on-my-twitter-feed technique](http://cnnlocalization.csail.mit.edu/) 
for visualizing 'heatmaps' of regions CNN 'treats as important' when classifying stuff + 
[Keras code](https://github.com/jacobgil/keras-cam). Isn't a tendency for neural networks interpretation loveable?

Requirement: the model must have a GAP layer prior to the output.
Looks like the core idea is


> ...to assign a weight to each output from the global average pooling layer, for each of the categories. This can be done by adding a dense linear layer + softmax, training an SVM on the GAP output, or applying any other linear classifier on top of the GAP. These weights set the importance of each of the convolutional layer outputs.


I wonder if this can be adapted for some character-level or word-level NLP models taking advantage of CNN layers 
for implicit feature extraction (Sergey NB! a good task for CSC students). Unfortunately, it seems 
the model can't be used for encoders-decoders (see Requirement).
