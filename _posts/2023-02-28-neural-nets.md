---
layout: post
title: Basics of Neural Nets
excerpt: neural network concepts
category: machine-learning
tags: [machine-learning]
---

## Notes
* A perceptron cannot model the XOR function but a multi-layer perceptron (MLP) can.
* MLPs can compute any Boolean function. MLPs are universal Boolean functions. A one-hidden-layer MLP is a Universal Boolean Function.
* An XOR of N variables will require $$3(N-1)$$ perceptrons in a deep network, O(N). It will require $$2^{N-1}+1$$ perceptrons in one-hidden-layer network, O(2^N).
* A network with fewer than the minimum required number of neurons cannot model an N-input perceptron properly.
* deep boolean MLPs that scale *linearly* with number of inputs can become *exponentially* large if using only 1 hidden layer

## Resources
* [CMU 11-785 Deep Learning Lecture 2](https://deeplearning.cs.cmu.edu/S23/document/slides/lec2.universal.pdf)