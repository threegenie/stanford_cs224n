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

### Sigmoid function

- for a binary case of the Softmax function → two possible outcomes, yes or no
- input any real number, and it's mapping onto a probability distribution between zero and one

### Unigram distribution

- take words on a large corpus and count up how often each one occurs just as a count of independent words → unigram counts
- it can show you decreasing how often you sample very common words, and increasing how often you sample rarer words → basic meaning for word2vec

### But why not capture co-occurrence counts directly?

→ co-occurnce : 동시출현, 한 문장이나 문단 또는 텍스트 단위에서 같이 출현한 단어로 언어학적 의미에서 의미적 근접성을 가리키며, 단어의 연결을 찾는데 활용됨

with a co-occurrence matrix

- 2 options : windows vs full document
- window : similar to word2vec, captures both syntactic and semantic imformation
- document : leading to Latent Semantic Analysis

### Problems with simple co-occurrence vectors

- increase in size with vocabulary
- need a lot of storage → too large dimension
- classification models might have sparsity issues cause, because a lot of those cells aren't present and might not be very robust

    → robust : 이상치에 영향을 받지 않는 굳건한 통계량

### Solution : Low dimensional vectors

- Reduce the dimensionality
- similar to word2vec

→ Method : Singular Value Decomposition (SVD)

### Hacks to X

scaling the counts in the cells can help a lot

- but some function words(ex. the, he has) are too frequent → it can get much impact than other words
- so we use Pearson correlations instead of Counts

### COALS model

- Improved Model of Semantic Similarity Based on Lexical Co-Occurrence

### Count based vs Direct prediction

**Count based**
- LSA, HAL
- COALS
- Fast training, efficient usage of statistics
- primarily used to capture word similarity
- disproportionate importance given to large counts

**Direct prediction**
- Skip-gram, CBOW
- NNLM, HLBM, RNN
- Scales with corpus size
- inefficient usage of statistics
- can capture complex patterns beyond word similarity

### Encoding meaning in vector differences

Insight : Ratios of co-occurrence probabilities can encode meaning components

### GloVe

- fast training
- scalable to huge corpora
- good performance even with small corpus and small vectors
- it uses neural methods to get word vectors

### How to evaluate word vectors?

Intrinsic evaluation 본질적으로

- evaluation on a specific/intermediate subtask
- fast to compute accuracy
- helps to understand that system

Extrinsic evaluation 외적으로

- evaluation on a real task
- takes long time to compute accuracy
- unclear if the subsystem is the problem or its interaction or other subsystems

~58:51
