# Deep Learning Notes

## Why Deep Learning?
Traditionally machine learning algorithms define a set of features in their data. Usually these are features that are hand-crafted and thus they tend to be pretty brittle in practice when they are deployed. 
Deep learning aims to learn these features directly from data in a **hierarachical** manner.

## The perceptron
> The structural building block of deep learning.

### Forward Propagation
<!-- Image -->
<p align="center">
    <img src="./images/perceptron.PNG" />
</p>
Each of these inputs are multiplied by their corresponding weights and then added together. We then take this single number as a result of that addition, add a bias to it and pass it through a non-linear activation function to produce our final output y.

### Common Activation Functions
<!-- Image -->
<p align="center">
    <img src="./images/activation.PNG" />
</p>

The sigmoid activation function takes any value and outputs a number between 0 and 1. This makes it very well suited for probability problems.

### Importance of Activation Functions
> The purpose of activation functions is to introduce non-linearities into the network.

<!-- Image -->
<p align="center">
    <img src="./images/imptactivation.PNG" />
</p>

In the real world, data is almost always non-linear. Using a neural network with a linear activation function is like trying to separate the red and green dots with a single straight line.

### Why are loss functions difficult to optimise?

<!-- Image -->
<p align="center">
    <img src="./images/learningrate.PNG" />
</p>

The gradient tells us which direction to step next, while the learning rate controls the magnitude of that next step. (eg. how much to step in the direction of that gradient)  
A learning rate that is too small converges slowly and gets stuck in false local minima.  
A learning rate that is too large can overshoot the global minima and become unstable, never converging.  
An optimal learning rate has to be large enough to avoid the local minima but small enough so that they can converge on the global minima.

### What is regularization?

Technique that constrains our optimization problem to discourage complex models. This is needed to prevent overfitting and help the model generalize well on unseen data.

#### Regularization 1: Dropout


<!-- Image -->
<p align="center">
    <img src="./images/dropout.PNG" />
</p>

* During training, randomly set some activations to 0.  
* Typically drop between 20-50% of activations in layer.  
* Forces network to not rely on any 1 node.

#### Regularization 2: Early Stopping

<!-- Image -->
<p align="center">
    <img src="./images/earlystopping.PNG" />
</p>

* Stop training before the model overfits