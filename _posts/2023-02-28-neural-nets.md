---
layout: post
title: Basics of Neural Nets
excerpt: neural network concepts
category: machine-learning
tags: [machine-learning]
---

## Notes

## Initialization
* If loss is extremely high upon initialization, and then it rapidly drops, perhaps your initial params are bad
* for ex, if neural network is predicting next character (27 chars total), at initialization, there is no reason to expect one character to be more likely than another. Thus, each character is equally likely with a probability of 1/27. The loss should be log(1/27) = 3.2958. If loss is extremely high, like 27, then fix the initial params.

## Batch Normalization
* ideal if hidden layer pre-activations (hpreact) were unit Gaussian, so key idea: make hpreact unit Gaussian!
* compute mean of each hidden dimension across entire batch
* compute std of each hidden dimension across entire batch
* for each example in batch, normalize its dimensions with mean and std computed from batch
* furthermore, during training, we don't want to restrict hpreact to always be unit Gaussian. Therefore, scale and shift hpreact with params (initialized to scale=1 and shift=0 initially)
* during inference, use mean/std computed across entire training set during training
* during training, keep running mean and std (outside of SGD)
* BatchNorm acts as a regularizer
* Whenever you're using BatchNorm after a Linear layer, you don't need a bias in the linear layer b/c it's spurious due to the BatchNorm bias, which will bias the distribution
* Usually used after a layer that involves multiplications, like a linear or convolution layer
* linear -> normalization -> nonlinearity is often the order used in deep neural networks
* in PyTorch's BatchNorm1d, the momentum matters if the batch size is too small, which will thrash the running mean and std
* Researchers don't like that the stats 

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