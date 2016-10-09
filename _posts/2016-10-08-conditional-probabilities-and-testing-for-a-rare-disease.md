---
layout: post
title: Conditional Probabilities and Testing for a Rare Disease
excerpt: If you test positive for a rare disease, don't panic. Your chances of being afflicted with a rare disease are still quite low.
category: statistics
tags: [statistics]
mathjax: true
---

Let $$T$$ be the event that a person tests positive for the disease, and let $$D$$ be the event that a person has the disease. Assume this rare disease afflicts 1% of the population. Suppose a test for a rare disease is 99% accurate. This means $$P(T \vert D) = 0.99$$ and $$P(T^c \vert D^c) = 0.99$$. What's the conditional probability that you have a rare disease, given that you've tested positive for it?

Using Bayes' rule and the law of total probability,

$$
\begin{align}
P(D \vert T) &= \frac{P(T \vert D)P(D)}{P(T \vert D)P(D) + P(T \vert D^c)P(D^c)} \\
&= \frac{0.99 \cdot 0.01}{0.99 \cdot 0.01 + 0.01 \cdot 0.99} \\
&= \frac{0.99 \cdot 0.01}{0.99 \cdot 0.01} \frac{1}{1 + 1} \\
&= 0.5
\end{align}
$$

Thus, even if you've tested positive for a disease with 99% accurate test, you're still 50-50 when it comes to actually being afflicted. If the test is 95% accurate, you have only a 16% chance of having the rare disease.

Why is a test that's "99% accurate" showing that you have a 50% chance of being afflicted? To understand this, notice that in the equation above, $$P(D)$$ is very low. It tells us that only 1% of people are afflicted with a rare disease. If you were to wake up today and feeling normal, what would you think the chances are that you have a rare disease that afflicts only 1% of the population? You'd probably think that your chances are low. This is the **prior probability**, or $$P(D)$$. It's **how much** you believe you're afflicted before you gain any information. Then, you get tested positive. Now you've gained new information, and your belief, the posterior probability or $$P(D \vert T)$$, should factor in that information.

You can also build intuition another way. Consider a population of 1 million people. 10,000 have the rare disease, and 990,000 don't. Of the 10,000 afflicted people, 9900 would test positive, and 100 would test negative. Of the 990,000 healthy people, 980,100 would test negative, and 9,900 would test positive. So, of those would tested positive, 9,900 are healthy and 9,900 are afflicted. This means if you test positive, you still have a 50% chance of actually being healthy.