# Loss Functions

The loss function is how your penalizing your output. It measures how far apart the current model is from the provided data. 

## Cross entropy loss

The cross entropy loss is closely related to the Kullback-Leibler divergence between the empirical distribution and the predicted distribution. This function is not naturally represented as a product of the true label and the predicted value, but is convex and can be minimized using stochastic gradient descent methods. The cross entropy loss is ubiquitous in modern deep neural networks.


TODO