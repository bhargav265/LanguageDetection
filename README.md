## Team
Nikhil Thakur - MS CS <br />
Akshay Sharma - MS CS <br />
Bhargav Parsi - MS CS <br />
Shraddha Manchekar - MS CS <br />

## Abstract
In natural language processing, language identification or language guessing is the problem of determining the language of the given content.
There are several statistical approaches to language identification using different techniques to classify the data.

## Introduction
In this project we have implemented 2 approaches to language identification. The first approach uses N-grams and the second uses deep neural network.
The first approach has been implemented in Java and the second in Python. 


## N-gram Model
An n-gram is a contiguous sequence of n items from a given sequence of text or speech. It is an N-character slice of a longer string. Typically, the string is sliced into a set of overlapping N-grams.

Given a novel document to be classified, the system computes the N-gram profile of this document (document profile) and compares the distance between this document profile and
the language profiles for all the supported languages. The language profile is basically the top N of the list of bi-grams and tri-grams sorted by frequency. The top 300 or so N-grams are almost always highly correlated to the language. Thus, the language profile of a sporty document will be very similar to the language profile generated from a political document in the same language. This gives us confidence that if we train the system on the Declaration of Human Right we will still be able to classify documents to the correct language even though they might have completely different topics. Starting at around rank 300 or so, an N-gram frequency profile begins to become specific to the topic. For the training and testing we took the data from <a target="_blank" href = "http://www.statmt.org/europarl/">European Parliament Proceeding Parallel Corpus</a>. The dataset contains text data for 21 european languages.



Given below are the top 50 most frequent combination of bigrams and trigrams that we found from the training corpus.

<body style="background-color:powderblue;">
<strong>[of the, in the, to the, the european, on the, it is, the commission, that the, and the, for the, to be, ' s, with the, by the, european union, we are, like to, the european union, that we, is a, we have, member states, the council, in this, this is, i would, at the, is the, will be, is not, of this, i am, from the, there is, that is, of a, has been, of the european, which is, as a, would like, must be, do not, have been, we must, and i, should be, would like to, that it, european parliament]<strong>
</strong></body>

To reduce the computation we computed the language model for each language and serialized each one of them. Then, while testing we directly used them after deserializing.
For preprocessing the text, tokenization etc. we used the Stanford CoreNlp library. You can find the full Java code on the Github page.


## Deep Neural Network Model


### Architecture of the Neural Network
From the previous Section, we see that the model gets 132 features. Recalling that there are 1400000 training examples and 350000 testing examples, we input the training examples into the Deep NN. We used Keras with Tensorflow to achieve this task. <br />
1. The first Layer has 132 Nodes 

## Results

## Conclusion

## References

1. Gyawali, Binod, Gabriela Ramírez-de-la-Rosa, and Thamar Solorio. "Native Language Identification: a Simple n-gram Based Approach." BEA@ NAACL-HLT. 2013.
2. Carlos Ramisch. “N-gram models for language detection.”
3. Kadri, Said, and Abdelouahab Moussaoui. "An effective method to recognize the language of a text in a collection of multilingual documents." Electronics, Computer and     	   Computation (ICECCO), 2013 International Conference on. IEEE, 2013.
4. 


