## Introduction and Word Vectors

### **How do we represent the meaning of a word?**

Definition : Meaning

- the idea that is represented by a word
- the idea that a person wants to express by using words, signs, etc.
- the idea that is expressed in a work of writing

### How do we have usable meaning in a computer?

- common solution : using WordNet which contains lists of synonym sets and hypernyms - NLTK → it can tells you about word meanings and relationships between word meanings

### Problems with resources like WordNet

- Great as resource but missing nuance → some words(synonym) can only represent narrow meanings
- Missing new meanings of words → cannot cover newly coined words like slang
- Subjective
- Requires human labor to create and adapt
- Can't compute accurate word similarity

### Representing words as discrete symbols

- In traditional NLP, we regard words as discrete symbols: hotel, conference, motel - a localist representation
- Words can be represented by one-hot vectors
- because of derivational morphology - we can make bigger words by adding more stuff in to it - but we have infinite space of words  - so if we wanna represent sensible size vocabulary, we can get very big vectors

### Problems with words as discrete symbols

- If we use One-hot vectorization : It is difficult to find natural similarity relationship on one hot vectors of words
- No relationship between orthogonal vectors
- Too big vector dimension - we need as lots of dimensions as number of words in vocabulary

### Representing words by their context

- Distributional Semantics : A word's meaning is given by the words that frequently appear close by - You can use context to figure out word meaning. - theory of meeting-meaning
- When a word appears in a text, its context is the set of words that appear nearby
- We can use many contexts of a word to build up a representation of the word

### Word vectors

- We can build dense vector for each word, so that it is similar to vectors of words that appear in similar contexts
- Word vectors : Word embeddings = Word representations , sometimes call a Distributed representation - represent the meaning of a word as a numeric vector
- we can represents a word as a dense vector where by all of the numbers are non-zero

### Word meaning as a neural word vector - visualization

- by visualization of word vectors, we can see that some morphological forms which can be grouped together
- 2D projection can be performed

### Word2Vec : Overview

- A framework for learning word vectors
- Thomas Mikolov came up with in 2013 called the word2vec algorithm

**Ideas :** 

- we have a large corpus of text
- every word in a fixed vocabulary is represented by a vector
- use the similarity of the word vectors for c and o to calculate the probability of o given c (or vice versa)
- keep adjusting the word vectors to maximize this probability
- how close things are in the vector space can be a notion of meaning similarity

### Word2Vec : objective funtion

- Objective function(cost or loss function) is the average negative log likelihood:
- Minimizing objective function ↔ Maximizing predictive accuracy
- we want to minimize the objective function by calculate center word vector and context word vector

### Word2Vec : prediction function

- similar with Softmax function
- softmax function maps arbitrary values to probability distribution - it sorts of map any numbers into a probability distribution

### Training a model by optimizing parameters

- to train a model, we adjust parameters to minimize a loss → Optimization

### To train the model : Compute all vector gradients

- Theta represents all model parameters in one long vector
- R^2dV is d-dimensional vectors and V-many words
- Theta belongs to R^2dV
- Every word has two vectors
- we optimize these parameters by walking down the gradient
- there are as many parameters as vector dimensions
- word vectors would calculate a higher probability for the words that actually occur in contexts of this center word
