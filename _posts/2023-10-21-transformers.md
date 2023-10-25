---
layout: post
title: Transformers
excerpt: Intuitively understand what makes an ML transformer so powerful
category: machine-learning
tags: [machine-learning]
---

## Scaled Dot Product Attention
Attention is calculated with the following equation:
$$
\text{softmax} \left( \frac{QK^T}{\sqrt{d_k}} \right)V
$$

$QK^T$ is scaled with $\frac{1}{\sqrt{d_k}}$ because as the dimensions of an individual query vector and an individual key vector increase, their dot product on average will increase. Passing in non-diffuse distributions into softmax will lead to an output that is closer to a one-hot vector. We don't want $\text{softmax} \left( \frac{QK^T}{\sqrt{d_k}} \right)$ to output one-hot vectors because we want the input (query vector) to attend to multiple other inputs (value vector).

## Layer vs Batch Norm
* BatchNorm – compute mean and std for each column (hidden dimension) across batch
* LayerNorm – compute mean and std across single sample and normalize all features within single sample

## KV Cache

The attention layer is computed with the following equation:

$$
\text{softmax} \left( \frac{KQ^T}{\sqrt{d_k}} \right) V
$$

Remember that $K$, $Q$, and $V$ are derived from the input token's embedding, $x$. In decoder-style autoregressive Transformers like GPT, tokens are fed into the model and its output is then appended to the input tokens and fed into the model again. Without a KV cache, the keys and values of the input tokens are recomputed over and over again.

To avoid recomputing the keys and values, we store them in a KV cache.

We can also reduce the size of the KV cache but reducing the number of keys and values.

Multi-query attention (MQA): $N$ heads for query, 1 head for key/value

Grouped-query attention (GQA): $N$ heads for query, $G$ heads for key/value ($G = N/8$) 

## Resources
* [The Positional Encoding by Kazemnejad](https://kazemnejad.com/blog/transformer_architecture_positional_encoding/)
* [Jay Alammmar's Guide to Transformers](https://jalammar.github.io/illustrated-transformer/#representing-the-order-of-the-sequence-using-positional-encoding)
* [Why add positional embedding instead of concatenate?](https://github.com/tensorflow/tensor2tensor/issues/1591)