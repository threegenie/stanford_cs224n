## Backpropagation and computation graphs

### Derivative wrt a weight matrix

- Feedforward
- Backpropagation

### Deriving gradients for backprop

- derivative of single Wij : dot product of Error signal from above, and Local gradient signal
- use chain rule over and over
- or use Shape convention

### Deriving gradients wrt words for window model

- the gradient that arrives at and updates the word vectors can simply be split up for each word vector
- continue our gradients down

→ Downstream Task - input vector가 neural network의 feedforward, backpropagation 과정을 거쳐 가중치를 업데이트 하는 과정

### Retraining word vectors

- if we have small training data set, don't train the word vectors
- it would better to train = update = fine-tune word vectors to the task

### Backpropagation

- taking derivatives and using chain rule
- forward propagation : expression evaluation as you do in any programming in language interpreter
- downstream gradient = upstream gradient X local gradient

### Gradient checking : Numeric gradient

- h에 아주 작은 값을 대입하여 순간 기울기를 구하는 것
- not used in neural networks

### We have models with many params! Regularization!

- regularization prevents overfitting when we have a lot of features
<img width="162" alt="overfitting" src="https://user-images.githubusercontent.com/63702924/133022549-8fb0d1c6-f525-4f30-8526-6d2fd83db947.PNG">

### Non-linearities

- Sigmoid - logistic
- tanh - rescaled and shifted sifmoid
- hard tanh
- ReLU
- Leaky ReLU
- Parametric ReLU

### Learning rates

- start around learning rate = 0.001
- better results can be obtained by allowing learning rates to decrease as you train
