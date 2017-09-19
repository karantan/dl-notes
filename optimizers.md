# Optimizers

Gradient descent is one of the most popular algorithms to perform optimization and by far the most common way to optimize neural networks. At the same time, every state-of-the-art Deep Learning library contains implementations of various algorithms to optimize gradient descent.

For more information read [this blog post](http://ruder.io/optimizing-gradient-descent/).

![Stochastic gradient descent](http://hduongtrong.github.io/assets/gradient_descent/all.gif)

## Adam

It was first published in a paiper titled [Adam: A Method for Stochastic Optimization](https://arxiv.org/abs/1412.6980).

- Adam is a replacement optimization algorithm for stochastic gradient descent (SGD) for training deep learning models.
- Adam combines the best properties of the AdaGrad and RMSProp algorithms to provide an optimization algorithm that can handle sparse gradients on noisy problems.
- Adam is relatively easy to configure where the default configuration parameters do well on most problems.