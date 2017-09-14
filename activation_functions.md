# Activation Functions
Activation functions transform the weighted sum of inputs that goes into the artificial neurons. These functions should be non-linear to encode complex patterns of the data. The most popular activation functions are ***Softmax***, ***Sigmoid***, ***Tanh*** and ***ReLU***. ReLU is the most popular activation function in deep neural networks.

![Activation functions](http://adilmoujahid.com/images/activation.png)

In `Keras` activations can either be used through an Activation layer, or through the activation argument supported by all forward layers:

```python
from keras.layers import Activation, Dense

model.add(Dense(64))
model.add(Activation('tanh'))
```

This is equivalent to:

```python
model.add(Dense(64, activation='tanh'))
```

For more information about Keras activations see [their documentation](https://keras.io/activations/).

## Most popular activations

Softmax function is typically used only in the output layer of a neural network to represent a probability distribution of possible outcomes of the network. ReLU or rectified linear is a popular variant of activation functions especially in deep convolutional NN to impose non linearity to the incoming activations.

### Softmax

Softmax function calculates the probabilities distribution of the event over ‘n’ different events. In general way of saying, this function will calculate the probabilities of each target class over all possible target classes. Later the calculated probabilities will be helpful for determining the target class for the given inputs.

The main advantage of using Softmax is the output probabilities range. The range will 0 to 1, and the sum of all the probabilities will be equal to one. If the softmax function used for multi-classification model it returns the probabilities of each class and the target class will have the high probability.

The formula computes the exponential (e-power) of the given input value and the sum of exponential values of all the values in the inputs. Then the ratio of the exponential of the input value and the sum of exponential values is the output of the softmax function.

![softmax](https://cloud.githubusercontent.com/assets/14886380/22743228/91be8964-ee54-11e6-9a59-c55ea02a9146.png)

#### Properties of Softmax Function

- The calculated probabilities will be in the range of 0 to 1.
- The sum of all the probabilities is equals to 1.

#### Softmax Function Usage

- Used in multiple classification logistic regression model.
- In building neural networks softmax functions used in different layer level.


***Used for the multi-classification task.***

For more information about Softmax function read [this article](http://cs231n.github.io/linear-classify/#softmax) and [wiki page](https://en.wikipedia.org/wiki/Softmax_function).

### Sigmoid
In mathematical definition way of saying the sigmoid function take any range real number and returns the output value which falls in the range of 0 to 1. Based on the convention we can expect the output value in the range of -1 to 1.

The sigmoid function produces the curve which will be in the Shape “S.” These curves used in the statistics too. With the cumulative distribution function (The output will range from 0 to 1)

#### Properties of Sigmoid Function

- The sigmoid function returns a real-valued output.
- The first derivative of the sigmoid function will be non-negative or non-positive.
  - Non-Negative: If a number is greater than or equal to zero.
  - Non-Positive: If a number is less than or equal to Zero.

#### Sigmoid Function Usage

- The Sigmoid function used for binary classification in logistic regression model.
- While creating artificial neurons sigmoid function used as the activation function.
- In statistics, the sigmoid function graphs are common as a cumulative distribution function.


***Used for the binary classification task.***

### ReLU (Rectified Linear Units)

ReLU is an element wise operation (applied per pixel) and replaces all negative pixel values in the feature map by zero. The purpose of ReLU is to introduce non-linearity in our ConvNet, since most of the real-world data we would want our ConvNet to learn would be non-linear. Convolution is a linear operation – element wise matrix multiplication and addition, so we account for non-linearity by introducing a non-linear function like ReLU

The ReLU operation can be understood clearly from image below:

![relu-operation](https://ujwlkarn.files.wordpress.com/2016/08/screen-shot-2016-08-07-at-6-18-19-pm.png?w=1496)

ReLUs' machinery is more like a real neuron in your body.

![relu_function](https://cloud.githubusercontent.com/assets/14886380/22743194/73ca0834-ee54-11e6-903f-a7efd247406b.png)

ReLU activations are the simplest non-linear activation function you can use, obviously. When you get the input is positive, the derivative is just 1, so there isn't the squeezing effect you meet on backpropagated errors from the sigmoid function. Research has shown that ReLUs result in much faster training for large networks. Most frameworks like TensorFlow and TFLearn make it simple to use ReLUs on the the hidden layers, so you won't need to implement them yourself.

> Dying ReLU problem: ReLU neurons can sometimes be pushed into states in which they become inactive for essentially all inputs