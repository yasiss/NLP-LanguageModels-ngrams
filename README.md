# NLP-LanguageModels-ngrams

We will train some n-gram language models on WikiText-2, a corpus of high-quality Wikipedia articles. 
The dataset was originally introduced in the following paper: https://arxiv.org/pdf/1609.07843v1.pdf. 
A raw version of the data can easily be viewed here: https://github.com/pytorch/examples/tree/master/word_language_model/data/wikitext-2.

The code can be run on Goggle Colab to use GPU and CPU resources

### The LanguageModel Class
We will implement 4 types of language models: a unigram model, a smoothed unigram model, a bigram model, and a smoothed bigram model. 

__init__(self, trainCorpus): Train the language model on trainCorpus. 
This will involve calculating relative frequency estimates according to the type of model you're implementing.

generateSentence(self): Return a sentence that is generated by the language model. 
It should be a list of the form [<s>, w(1), ..., w(n), </s>], where each w(i) is a word in your vocabulary 
(including <UNK> but exlcuding <s> and </s>). You may assume that <s> starts each sentence (with probability 1). 
The following words w(1), ... , w(n), </s> are generated according to your language model's distribution. Note that the number of words n is not fixed; 
instead, you should stop the sentence as soon as you generate the stop token </s>.

getSentenceLogProbability(self, sentence): Return the logarithm of the probability of sentence, which is again a list of the form [<s>, w(1), ..., w(n), </s>]. 
We should use the natural logarithm − that is, the base-e logarithm. 

getCorpusPerplexity(self, testCorpus): We need to compute the perplexity (normalized inverse log probability) of testCorpus according to your model. 
For a corpus W with N words and a bigram model, Jurafsky and Martin tells you to compute perplexity as follows:

Perplexity(W)=[∏i=1N1P(w(i)|w(i−1))]1/N
