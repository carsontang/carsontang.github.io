---
layout: post
title: CS231n Linear Classification Notes
excerpt: notes to clarify linear classification
category: ml
tags: [machine learning]
mathjax: true
---
A simple linear classifier has the following equation:

$$
\begin{align}
f(x_{random}, W, b) &=  W x_{random} + b \\
W &\in \mathbb{R}^{K \times D} \\
x_{random} &\in \mathbb{R}^D \\
b &\in \mathbb{R}^K \\
\end{align}
$$

In image classification, a single image is represented by $$x_{random}$$ in computer memory. $$x_{random}$$ is an array of $$D$$ numbers, each of which represents a pixel. You can think of $$W$$ as $$K$$ classifiers.

$$\overbrace{x_{random}}^{\text{an image = an array of pixel values}}$$

$$
\begin{align}
W =
\left.
\begin{bmatrix}
\begin{array}{ccccc}
- & - & W_{dog} & - & -\\
- & - & W_{cat} & - & - \\
- & - & W_{turtle} & - & - \\
& & \vdots & & \\
- & - & W_{tiger} & - & - 
\end{array}
\end{bmatrix}
\quad
\right \}
K \text{ classifiers or "templates"}
\end{align}
$$

Notice each of the $$K$$ classifiers are an array of $$D$$ numbers as well. You can think of each classifier as the "ideal" or "template" image for the class of image it represents. For example, one of the classifiers might represent a dog. If you use it to classify a random image, $$x_{random} \in \mathbb{R}^D$$, it'll produce a "dog score". The "dog score" could be the probability the random image, $$x_{random}$$, is an image of a dog. Or it could just be a numerical value that you use to compare against scores when multiplying $$x_{random}$$ by other templates.

$$
\begin{align}
W_{dog} \cdot x_{random} = \text{score of how similar the random image is to a dog's image}
\end{align}
$$

However you interpret the score, when you multiply $$W$$ and $$x_{random}$$, essentially you're producing $$K$$ scores, one for each classifier in $$W$$. You're getting scores for dog, cat, truck, lion, and whatever other classes are in $$W$$. On a more fine-grained level, you're taking the dot product between each classifier of $$W$$ and $$x_{random}$$. If you recall from linear algebra, taking the dot product between two vectors, $$v_1$$ and $$v_2$$, can be thought of as **taking the projection of $$v_1$$ on $$v_2$$ or vice versa**. And you can think of computing projection as **computing the similarity between the two vectors**. In other words, given a random image $$x_{random}$$ and a template image for a dog, $$W_{dog}$$, how **similar** is $$x_{random}$$ to $$W_{dog}$$?

$$
\begin{align}
W x_{random} + b &=
\left.
\begin{bmatrix}
\begin{array}{c}
\text{dog score} \\
\text{cat score} \\
\text{turtle score} \\
\vdots \\
\text{tiger score} \\
\end{array}
\end{bmatrix}
\quad
\right \}
K \text{ scores}
\end{align}
$$

Now compute **similarity scores** between $$x_{random}$$ and every other template image in $$W$$. Finally, after computing $$K$$ similarity scores, you'll have $$K$$ scores. Depending on what your score represents, choose the score that tells you which template your random image, $$x_{random}$$, most represents.

For example, **max(dog score, cat score, turtle score, ..., tiger score) = dog score**. Therefore, the random image, $$x_{random}$$, is most likely to be an image of a dog.