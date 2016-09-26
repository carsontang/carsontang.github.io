---
layout: post
title: Why won't linear regression work for spam filtering?
excerpt: A short summary on why it's folly to apply linear regression for the problem of spam filtering.
category: machine learning
tags: [machine learning]
mathjax: true
---

## Motivation
Let's say you're given **10,000** emails, each labeled as **spam** or **not spam**, and the wide range of vocabulary of the emails spans **100,000** words total. Should you use linear regression on the labeled emails to build a spam filter? **No**. Let's learn why.

## Turning this into a math problem
First, let's set this up as a math problem.

- **m** = number of training samples
- **n** = number of features

In this problem, $$m = 10,000$$ and $$n=100,000$$. Let's represent a single email by a **feature vector**:

$$
x =
\begin{bmatrix}
1 \\
0 \\
0 \\
\vdots \\
1 \\
\vdots \\
0 \\
\end{bmatrix}
\quad
\begin{array}{l}
\text{a} \\
\text{ability} \\
\text{able} \\
\vdots \\
\text{bargain} \\
\vdots \\
\text{zap} \\
\end{array}
$$

A **1** in the $$i$$-th position of the feature vector means the email has the corresponding $$i$$-th word (i.e., a **1** in the **1st** position means the word **"a"** exists in the email). On the other hand, a **0** means the word doesn't appear. In the example above, the feature vector shows the email contains the words **"a"** and **"bargain"** but not **"ability", "able",** and **"zap"**. Notice that the feature vector doesn't take into account the _order_ with which the words appear in an email.

If you were to apply linear regression on this problem, the goal would be to find 100,000 **weights**. Each of these weights ($$\theta_1, \theta_2, \cdots, \theta_{100,000}$$) controls how much influence each of the words in the email have on the decision to classify that email as spam or not. For example, if $$\theta_2 = 0$$, then it's telling us the **2nd** word in the feature vector, the word **"ability"**, doesn't give us more information about whether or not an email is spam.

Mathematically, we want the dot product of the **weight vector** and the feature vector, or $$x^T \theta$$. $$x^T$$ is a $$1 \times n$$ vector and $$\theta$$ is a $$n \times 1$$ vector, so their dot product is a $$1 \times 1$$ vector, which is a scalar called the **hypothesis**, and it's often denoted by $$h_\theta(x)$$. The hypothesis can be any of a range of values. It can be **20, 102.5, 900.1092,** or **1,000,000**.

## Reason 1: The hypothesis's range should be {0, 1}
This brings us to the first folly of using linear regression to build a spam filter. The hypothesis should be a value 1 or 0 (**spam** or **not spam**, respectively). Yet linear regression allows it be any real number. Mathematically, we want $$h_\theta(x) \in \{0, 1\}$$, yet with linear regression we get $$h_\theta(x) \in \mathbb{R}$$.

## Reason 2: What is a good threshold value $$b$$?
Because $$h_\theta(x) \in \mathbb{R}$$, we have to define a function that allows us to transform $$h_\theta(x)$$ into **0** or **1**.

$$
f ( h_\theta(x) ) =
\left\{
    \begin{array}{ll}
    0 & \text{if } h_\theta(x) > b \\
    1 & \text{if } h_\theta(x) \leq b
    \end{array}
\right.
$$

where **b** is a threshold value. If the hypothesis is above **b**, we'll say the email is not spam. If it's below or equal to **b**, we'll say it is spam. Now comes the question, what should **b** be? And even if you determine **b**, if you add a new email to your set of emails with which you built a spam filter, the new email could dramatically change the **weight vector** and alter how your spam filter perceives existing email. Watch this [excellent explanation by Andrew Ng](https://www.youtube.com/watch?v=HZ4cvaztQEs#t=49m53s) if you're still confused.

## Reason 3: The normal equations cannot be solved
If we stack all the emails, we get an $$m \times n$$ matrix

$$
X =
\begin{bmatrix}
    \begin{array}{ccc}
    -- & \left(x^{(1)}\right)^T & -- \\
    -- & \left(x^{(2)}\right)^T & -- \\
    & \vdots & \\
    -- & \left(x^{(m)}\right)^T & --
    \end{array}
\end{bmatrix}
$$

The label for each email (**spam, 1** or **not spam, 0**) can be represented by a vector **y**

$$
y =
\begin{bmatrix}
    \begin{array}{c}
    1 \\
    0 \\
    0 \\
    1 \\
    \vdots \\
    1
    \end{array}
\end{bmatrix}
$$

To find the optimal weight vector $$\theta$$, use the following equation

$$
\theta = \left( X^TX \right)^{-1} X^T y
$$

This is called the **normal equation**. Unfortunately, for our problem, it can't be solved because $$X^TX$$ has no inverse.