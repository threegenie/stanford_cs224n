## Natural Language Processing with Deep Learning

**ABOUT**

- Word Vectors and Word Senses

### Review : Main idea of word2vec

- Iterate through each word of the whole corpus
- predict surrounding words using word vectors →  center word and two outside context words in window of size 2

### Word2vec parameters and computations

- By dot product of outside and center and applying softmax, we can get probabilities
- we make a model to get high probability of all words that occur in the context

### Word2vec maximizes objective function by putting similar words nearby in space

- the distance of the words is unintuitive - a word can be close to lots of other words in different directions

### Optimization : Gradient Descent

- our goal is minimize a cost function
- Gradient descent is an algorithm to minimize cost function
- taking small steps in the direction of negative gradient to reach the minimum
- reaching minimum can be easy in 2-dimensional curve, but sometimes we are in high multi dimensional space

### Gradient Descent

- Update equation
    - we multiply small alpha which is step size or learning rate

### Stochastic Gradient Descent

- problem : cost function is a function of all windows in the corpus, so it is very expensive to compute
- we have to wait long time before making a single update → Not reasonable for pretty much all neural nets
- solution : Stochastic gradient descent(SGD)

### Word2vec : More details

- for easier optimization, use two vectors but can do it with just one vector per word
- Two main model :
    - Continuous Bag of Words(CBOW) : Get all of the outside words and predict the center word(by considering independently like a Naive Bayes model)
    - Skip grams(SG) : Get one center word and predict all the words in context

30:20까지
