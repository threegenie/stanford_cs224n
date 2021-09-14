## Language Models and RNNs

### Language modeling

- task of predicting what word comes next
- computing the probability distribution of the next word - from pre-defined list of words

### n-gram language models

- pre-Deep learning
- a chunk of n consecutive words (n개의 연이은 단어들)
- next words depends only on the preceding n-1 words
- by counting words in some large corpus of text, we can get n-gram and (n-1)-gram probabilities → 문장 내 단어 발생/전체 corpus 내 단어 발생
- first sparsity problem - some words are never seen an event happen in the training data, then model assigns zero probability to that event
- solution to this sparsity problem - we should add a small delta to the count for every word in the vocabulary → every possible word that come next has a least some small probability
- second sparsity problem - some contexts are never happened so model can't assign
- solution to this sparsity problem - if we can't find context in the corpus, then back off to just conditioning on the last two words rather than last three words  → back-off

<img width="291" alt="sparsity problem" src="https://user-images.githubusercontent.com/63702924/133183864-72ac8bff-8490-481d-84be-120a2eb283fd.PNG">

### Generating text with a n-gram language model

<img width="159" alt="n-gram language model" src="https://user-images.githubusercontent.com/63702924/133183870-7cc4344f-aefc-4d4b-83b7-0fee02ff92a6.PNG">

- can use a language model to generate text

~ 14:50

