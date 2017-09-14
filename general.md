# Q & A

## What is the difference between a feed forward neural network and a convolution neural network?

Feed forward actually means how the network learns from the features, whereas a convolution neural network is type of neural network. For example, depending on how a convolution neural net learns, it can be named as a feed forward convolution neural network.

Feed forward means that a neuron from the layer close to the input layer (can be output layer if there is no hidden layer) get features values, applies to them weights and bias and uses an activation function to the result then send the results to the next layer, if there is no hidden layer then produces an output.

Convolution refers to the fact that from a dimension of an input you have, a filter is applied to it to take some of the interesting features from that dimension.

They both use back propagation for training the network.

## Training Artificial Neural Networks

The goal of the training phase is to learn the network's weights. We need 2 elements to train an artificial neural network:

- Training data: In the case of image classification, the training data is composed of images and the corresponding labels.
- Loss function: A function that measures the inaccuracy of predictions.

Once we have the 2 elements above, we train the ANN using an algorithm called backpropagation together with gradient descent (or one of its derivatives). For a detailed explanation of backpropagation, I recommend this [article](https://mattmazur.com/2015/03/17/a-step-by-step-backpropagation-example/).

## What are Convolutional Neural Networks?

Convolutional Neural Networks (ConvNets or CNNs) are a category of Neural Networks (special type of feed-forward networks) that have proven very effective in areas such as image recognition and classification. ConvNets have been successful in identifying faces, objects and traffic signs apart from powering vision in robots and self driving cars.

These models are designed to emulate the behaviour of a visual cortex. CNNs have special layers called convolutional layers and pooling layers that allow the network to encode certain images properties.


## Convolutional Neural Networks Architecture

The simplest architecture of a convolutional neural networks starts with an input layer (images) followed by a sequence of convolutional layers and pooling layers, and ends with fully-connected layers. The convolutional layers are usually followed by one layer of ReLU activation functions.

The convolutional, pooling and ReLU layers act as learnable features extractors, while the fully connected layers acts as a machine learning classifier. Furthermore, the early layers of the network encode generic patterns of the images, while later layers encode the details patterns of the images.

Note that only the convolutional layers and fully-connected layers have weights. These weights are learned in the training phase.

![Example of an CNN Architecture](http://adilmoujahid.com/images/cnn-architecture.png)


## What is Fully Connected Layer?

The Fully Connected layer is a traditional Multi Layer Perceptron that uses a softmax activation function in the output layer (other classifiers like SVM can also be used). The term “Fully Connected” implies that every neuron in the previous layer is connected to every neuron on the next layer.

![fully_connected_layer](https://user-images.githubusercontent.com/7062631/30430832-c6216010-995c-11e7-8a5d-d49dc825650c.png)

Apart from classification, adding a fully-connected layer is also a (usually) cheap way of learning non-linear combinations of these features. Most of the features from convolutional and pooling layers may be good for the classification task, but combinations of those features might be even better.