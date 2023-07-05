---
layout: post
title: Basics of Neural Nets
excerpt: neural network concepts
category: machine-learning
tags: [machine-learning]
---

## Notes
### MLP as universal boolean function
* A perceptron cannot model the XOR function but a multi-layer perceptron (MLP) can.
* MLPs can compute any Boolean function. MLPs are universal Boolean functions. A one-hidden-layer MLP is a Universal Boolean Function.
* An XOR of N variables will require $$3(N-1)$$ perceptrons in a deep network, O(N). It will require $$2^{N-1}+1$$ perceptrons in one-hidden-layer network, O(2^N).
* A network with fewer than the minimum required number of neurons cannot model an N-input perceptron properly.
* deep boolean MLPs that scale *linearly* with number of inputs can become *exponentially* large if using only 1 hidden layer
* not all Boolean circuits have a clear depth vs size tradeoff

### MLP as universal classifier
* a perceptron takes the weighted sum of inputs and compares that sum to a threshold. If the threshold is matched or exceeded, the perceptron "fires" (aka outputs 1)
* perceptron can distinguish between a datapoint being in one area vs another
* perceptrons can be composed into a network to compute arbitrary classification "boundaries"
* MLPs can capture **any** classification boundary
* deeper networks may require far fewer neurons than shallower networks to express the same function

## Why does PyTorch store nn.Linear weights as transpose?
It's due to historical reasons. From Soumith Chintala:
> it's historical weight layout, changing it is backward-incompatible. Unless there is some BIG benefit in terms of speed or convenience, we wont break userland.

See https://github.com/pytorch/pytorch/issues/2159.

## Glossary
* model – summarizes data, don't need to have every piece of data, you can just have a model which allows you to predict more data even if you didn't immediately have it

## Resources
* [CMU 11-785 Deep Learning Lecture 2](https://deeplearning.cs.cmu.edu/S23/document/slides/lec2.universal.pdf)