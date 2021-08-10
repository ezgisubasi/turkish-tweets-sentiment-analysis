# turkish-tweets-sentiment-analysis

<p align="center"> 
   <img width="900" height="400" alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/52889449/127268644-015209d7-7c11-44ff-92b4-691ca5e3686f.png">
</p>

This sentiment analysis project determines whether the tweets posted in the Turkish language on Twitter are positive or negative. Since Turkish is not the most studied language, it has an insufficient amount of data. Therefore I created a new dataset with 15000 tweets by combining multiple datasets.


# Text Preprocessing

* Convert to lower case
* Remove @ mentions and hyperlinks
* Remove punctations, emojies, and numbers
* Remove stop words and rare words
* Tokenization
* Sentence normalization
* Lemmatization

# Zemberek

Zemberek is a natural language processing (NLP) tool that works with the Turkish language. This project performs the tokenization, sentence normalization, and lemmatization parts of the text preprocessing using this library. 

# Data Visualization

### Positive Negative Balance

It shows how many percent of tweets are positive or negative.

<p align="center">    
   <img width="450" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127268283-0ac12507-17b4-4e5c-9181-1dbb1fb6bc69.png">   
</p>

## Visulazing N-Grams

N-gram is a language model which predicts the probability of a given N-gram within any sequence of words in the language. If we have a good N-gram model, we can predict p(w | h) – what is the probability of seeing the word w given a history of previous words h – where the history contains n-1 words.

<p align="center">    
   <img width="450" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127269418-cfd7a698-58e2-49c4-b14b-b7debb2abb38.png">   
</p>

### Top Unigrams

When N=1, it becomes a unigram. Unigram considers words in the text one by one. According to the words frequency bar chart, "bir" is the most used unigram.

<p align="center">    
   <img width="600" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127271988-f60ed25c-ea82-4773-b999-3b1697d6a87f.png">   
</p>

### Top Bigrams

When N=2, it is called a bigram. In the bigram, words are handled in pairs. In this dataset, the most used bigram is "orospu çocuk".

<p align="center">    
   <img width="600" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127272115-769ea322-1457-49bf-971c-7895e9be9f5c.png">   
</p>

### Top Trigrams

Finally, if N=3, it is a trigram. In trigrams, the frequencies of the words are evaluated in groups of three words. Accordingly, the most occurred trigram in the dataset is "allah bela vermek".

<p align="center">    
   <img width="600" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127272152-512d2756-be08-4896-be0e-5de2a3c06c1c.png">   
</p>

## WordCloud

WordCloud is a visualization technique for text data wherein each word is picturized with its importance in the context or its frequency. This is a very handy application when it comes to understanding the crux of the text. In the WordCloud example below, a distribution has occurred according to the most used words among all tweets in the dataset.

<p align="center">    
   <img width="700" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127272362-b1061dc8-984e-49b4-b42f-4317e6e12344.png">   
</p>

# Deep Learning

## Baseline Model

The Baseline Model has 2 densely connected layers of 64 hidden elements at the beginning. The input_shape for the first layer is equal to the number of words we allowed in the dictionary and for which we created one-hot-encoded features. In order to predict 2 different sentiments, the last layer has 2 hidden elements. The softmax activation function makes sure the three probabilities sum up to 1.

### Handling Overfitting

* Reducing network's size 

I reduced the size of the network by removing one layer and reducing the number of hidden elements in the remaining layer to 32. According to the graph, we can observe that loss increases much slower compared to the baseline model. It takes more epochs before the reduced model starts overfitting.

<p align="center">    
   <img width="500" alt="Ekran Resmi 2021-08-10 03 29 54" src="https://user-images.githubusercontent.com/52889449/128790723-1b3cab55-731e-4d01-a77b-e9a2fa99faf7.png">
</p>

* Adding regularization

I added L2 regularization to the model for dealing with overfitting. According to the graph, it starts overfitting earlier than the baseline model. However, the loss increases much slower afterward.

<p align="center">    
   <img width="500" alt="Ekran Resmi 2021-08-10 03 30 43" src="https://user-images.githubusercontent.com/52889449/128790772-6a6ca4d3-0d62-42ee-9cc1-28f3a0ebccba.png">
</p>

* Adding dropout layers

Lastly, I added dropout layers to the model. It starts overfitting a bit later and the loss also increases slower than the baseline model.

<p align="center">    
   <img width="500" alt="Ekran Resmi 2021-08-10 03 31 38" src="https://user-images.githubusercontent.com/52889449/128790816-88b6a4cd-458a-4673-af50-10f1e2a19e10.png"> 
</p>

## Embedding Layer

Keras provides an Embedding Layer that helps to train specific word embeddings based on the training data. It converts the words in the vocabulary to multi-dimensional vectors.

<p align="center">    
   <img width="400" alt="Ekran Resmi 2021-08-10 20 13 41" src="https://user-images.githubusercontent.com/52889449/128904882-a5113a14-d2c0-40e5-aafe-66a39e0edbc6.png">   
    <img width="400" alt="Ekran Resmi 2021-08-10 20 13 56" src="https://user-images.githubusercontent.com/52889449/128904839-171e10ec-b2cf-4804-ac14-4726b6737797.png">
</p>

## Pre-trained Word Embedding: GloVe

Since the training data is not so big, the model might not be able to learn good embeddings for the sentiment analysis. Luckily we can load pre-trained word embeddings built on much larger training data. The GloVe database contains multiple pre-trained word embeddings and more specific embeddings trained on tweets.

<p align="center">      
   <img width="400" alt="Ekran Resmi 2021-08-10 20 14 20" src="https://user-images.githubusercontent.com/52889449/128904805-f6f5e304-62bc-4fcb-862b-73981592a601.png">  
   <img width="400" alt="Ekran Resmi 2021-08-10 20 14 35" src="https://user-images.githubusercontent.com/52889449/128904744-a1760da6-96bd-4f89-884e-e08fecdf1454.png">
</p>


# Model Performance

According to the accuracy scores obtained at the end of the project, the best model is the Regularized Model with an accuracy of 87.03%. Although the Embedding Layer and Pre-trained Word Embedding: GloVe were modeled separately, the performance result was not as good as the Regularized Model.

<p align="center">    
   <img width="625" alt="Ekran Resmi 2021-08-10 03 31 38" src="https://user-images.githubusercontent.com/52889449/128904072-c640a7d4-e758-4173-9008-e1b464641eeb.png"> 
</p>
