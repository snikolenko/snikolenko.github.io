---
layout: post
title: Decoupled Neural Interfaces using Synthetic Gradients
excerpt: ""
categories: papers
tags: [deep learning, general, training]
comments: true
author: snikolenko
---

"[Decoupled Neural Interfaces using Synthetic Gradients](https://arxiv.org/abs/1608.05343)" trains separate neural networks to predict gradient values and/or next inputs and thus provide synthetic update values. Sounds crazy but seems to work. The goal is to remove "update locking" and let parts of the network update while parts above them along the gradient computation graph are still updating. Report better training for long horizon RNNs.
