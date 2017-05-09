---
layout: post
title: Machine Learning and Deep Learning Resources
excerpt: Links to machine learning and deep learning resources
category: machine learning
tags: [machine learning]
mathjax: true
---

# Advice for building good models
* Zero-mean data is generally better than nonzero-mean data. If the inputs of a neuron were always positive, the gradient that'd flow out of the neuron would either be all positive or all negative. In 2D, this means gradient descent would take a zig-zaggy path, which is a constrained path. See [CS231n Lecture 5 by Andrej Karpathy](https://www.youtube.com/watch?v=gYpoJMlgyXA&t=18m38s) for more details.
# Textbooks
* [Deep Learning Book by Ian Goodfellow, Yoshua Bengio, Aaron Courville](http://www.deeplearningbook.org/)
* [Neural networks and deep learning by Michael Nielson](http://neuralnetworksanddeeplearning.com/)
* "It is the **loss function** that will direct what the intermediate hidden variables should be, so as to do a good job at predicting the targets for the next layer." [Link](https://www.youtube.com/watch?v=MRH9ABxCUZ0#t=54m56s)

# References
* [Intuitive YouTube explanation of the entropy equation](https://www.youtube.com/watch?v=2s3aJfRr9gE)
* [Intuitive explanation of cross entropy](http://colah.github.io/posts/2015-09-Visual-Information/)
* [References for new deep learning students at the Montreal Institute for Learning Algorithm](https://docs.google.com/document/d/1IXF3h0RU5zz4ukmTrVKVotPQypChscNGf5k6E25HGvA/edit)
* [Neural networks with at least one hidden layer are universal approximators.](http://cs231n.github.io/neural-networks-1/#representational-power)
* **Prefer L2 regularization, dropout, and input noise over smaller neural networks to prevent overfitting**. The takeaway is that you should not be using smaller networks because you are afraid of overfitting. Instead, you should use as big of a neural network as your computational budget allows, and use other regularization techniques to control overfitting.
* Read this [CS231n note about representational power of neural networks](http://cs231n.github.io/neural-networks-1/#representational-power) for tips on best practices.
* [Reading roadmap of important deep learning papers](https://github.com/songrotek/Deep-Learning-Papers-Reading-Roadmap)
* [Deep learning links from Ujjwal Karn, an NLP and deep learning engineer](https://github.com/ujjwalkarn/Machine-Learning-Tutorials#deep)
* [Introduction to Automatic Differentiation](http://alexey.radul.name/ideas/2013/introduction-to-automatic-differentiation/)
* [A Neural Parametric Singing Synthesizer](https://arxiv.org/pdf/1704.03809.pdf) with [samples](http://www.dtic.upf.edu/~mblaauw/IS2017_NPSS/)
* [Speech synthesis technology by Lyrebird](https://lyrebird.ai/)
* [zi2zi: Master Chinese Calligraphy with Conditional Adversarial Networks](zi2zi: Master Chinese Calligraphy with Conditional Adversarial Networks)
* [Deepmind Differenetial Neural Computer](https://github.com/deepmind/dnc)