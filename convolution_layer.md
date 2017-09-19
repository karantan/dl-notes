# Convolution Layer

The primary purpose of Convolution in case of a ConvNet is to extract features from the input image. Convolution preserves the spatial relationship between pixels by learning image features using small squares of input data.

Consider a 5 x 5 image whose pixel values are only 0 and 1 (note that for a grayscale image, pixel values range from 0 to 255, the green matrix below is a special case where pixel values are only 0 and 1):

![image-5x5](https://ujwlkarn.files.wordpress.com/2016/07/screen-shot-2016-07-24-at-11-25-13-pm.png?w=254&h=230)

Also, consider another 3 x 3 matrix

![image-5x5](https://ujwlkarn.files.wordpress.com/2016/07/screen-shot-2016-07-24-at-11-25-24-pm.png?w=148&h=128)

Then, the Convolution of the 5 x 5 image and the 3 x 3 matrix can be computed as shown in the animation below:

![conv-animation](https://ujwlkarn.files.wordpress.com/2016/07/convolution_schematic.gif?w=268&h=196&zoom=2)


This layer consists of a set of learnable filters that we slide over the image spatially, computing dot products between the entries of the filter and the input image. The filters should extend to the full depth of the input image. For example, if we want to apply a filter of size 5x5 to a colored image of size 32x32, then the filter should have depth 3 (5x5x3) to cover all 3 color channels (Red, Green, Blue) of the image. These filters will activate when they see same specific structure in the images.

![ConvLayer](http://adilmoujahid.com/images/conv-layer.png)

In CNN terminology, the 3×3 matrix is called a ‘filter‘ or ‘kernel’ or ‘feature detector’ and the matrix formed by sliding the filter over the image and computing the dot product is called the ‘Convolved Feature’ or ‘Activation Map’ or the ‘Feature Map‘. It is important to note that filters acts as feature detectors from the original input image.

In the table below, we can see the effects of convolution of the image with different filters.

![convolved-images](https://ujwlkarn.files.wordpress.com/2016/08/screen-shot-2016-08-05-at-11-03-00-pm.png)


Another example. If we take the first number (seven)

![mnist-numbers](http://wiki.fast.ai/images/f/fd/Mnist.png)


Apply these filters:

![conv-filters](http://wiki.fast.ai/images/1/12/Filters1.png)

We get the following result as an output:
![conv-output](http://wiki.fast.ai/images/9/9a/Filtered_sevens.png)

## How to decide which filters to use?

We don't need to manually decide what filters work best at classifying our images, we can simply train a model to do so, using these filters as weights!

For example, we can start with 8 randomly generated filters; that is 8 3x3 matrices with random elements. Given labeled inputs, we can then use [stochastic gradient descent](optimizers.md) to determine what the optimal values of these filters are, and therefore we allow the neural network to learn what things are most important to detect in classifying images.


For more visualization examples check out this video: [Deep Visualization Toolbox](https://www.youtube.com/watch?v=AgkfIQ4IGaM).

## Padding

One thing we have neglected to mention is how these filters operate on the edge and corner pixels, given that the filter necessarily operates on the premise that there are 8 surrounding pixels. There is a variety of approaches to handling these edge/corner cases, but one of the most common and the one we'll use the most in this course is zero-padding. All zero-padding does is add a extra borders of zero pixels around the image prior to passing through a filter so that the output shape from the filter is the same as the input shape.

