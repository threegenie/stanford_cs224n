## Neural Networks

**About**

- Neural Net Fundamentals
- NLP Classifiers

### Classification intuition

- Traditional ML/Stats approach : to determine a decision boundary to divide two classes

### Details of the softmax classifier

- dot product and apply softmax function to get normalized probability → logistic regression

### Training with softmax and cross-entroyu loss

- our goal is to maximize the probability of the correct class y
- or minimize the negative log probability of that class

### What is cross entropy loss/error

- from information theory
- dot product of probability distribution and logged model probability and make sum of that

### Traditional ML optimization

- only update the decision boundary - move line that separates between the classes

### Neural Network Classifiers

- Softmax gives only linear decision boundaries
- quite limiting - linear한 모델로 설명하기 어려운 데이터들이 많기 때문에
- neural networks can learn much more complex and nonlinear decision boundaries

### An artificial neuron

<img width="253" alt="artificial neuron" src="https://user-images.githubusercontent.com/63702924/133011272-86e19967-370e-4951-8143-be0064ed5784.PNG">


### A neuron can be a binary logistic regression unit

- different from softmax logistic regression
- softmax makes two classes and has two sets of parameters, but this has one set of parameters and modeling the two classes by giving the probability of one class from 0 to 1 - binary logistic regression

### A neural network = running several logistic regressions at the same time

- if we feed a vector of inputs through a bunch of logistic regression functions, then we get a vector of outputs

<img width="252" alt="neural network" src="https://user-images.githubusercontent.com/63702924/133011263-43fa046e-6827-42cb-a347-057b66ec761a.PNG">


### Non-linearities : why they're needed

- without non-linearities, deep neural networks can't do anything more than a linear transform
- with more layers, they can approximate more complex functions

### Named Entity Recognition(NER)

- Find names - named entities
- we predict entities by classifying words in context and then extracting entities as word subsequences

### Why might NER be hard?

- hard to work out boundaries of entity
- entity class is ambiguous and depends on context
- hard to know class of unknown/novel entity

### Window classification

- classify a word in its context window of neighboring words
- softmax - train softmax classifier to classify a center word by taking concatenation of word vectors surrounding it

### Simplest window classifier : Softmax

### Neural Network Feed-forward computation

### Main intuition for extra layer

- the middle layer learns non-linear interations between the input word vectors

### Gradients

- f(x) = x^3
- given a function with 1 output and n inputs - it's gradient is a vector of partial derivatives(편미분) with respect to each input
- m x n matrix of partial derivatives

### Chain rule

<img width="249" alt="chain rule" src="https://user-images.githubusercontent.com/63702924/133011259-62a7161c-7a56-49e1-abca-3666fe93d562.PNG">


Jacobians - reference : [https://angeloyeo.github.io/2020/07/24/Jacobian.html](https://angeloyeo.github.io/2020/07/24/Jacobian.html)

###
