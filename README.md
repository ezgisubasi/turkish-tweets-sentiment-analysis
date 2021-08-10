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

<p align="center">    
   <img width="450" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127271988-f60ed25c-ea82-4773-b999-3b1697d6a87f.png">   
</p>

### Top Bigrams

<p align="center">    
   <img width="450" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127272115-769ea322-1457-49bf-971c-7895e9be9f5c.png">   
</p>

### Top Trigrams

<p align="center">    
   <img width="450" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127272152-512d2756-be08-4896-be0e-5de2a3c06c1c.png">   
</p>

## WordCloud

WordCloud is a visualization technique for text data wherein each word is picturized with its importance in the context or its frequency. This is a very handy application when it comes to understanding the crux of the text. In the WordCloud example below, a distribution has occurred according to the most used words among all tweets in the dataset.

<p align="center">    
   <img width="450" alt="Ekran Resmi 2021-06-28 01 27 32" src="https://user-images.githubusercontent.com/52889449/127272362-b1061dc8-984e-49b4-b42f-4317e6e12344.png">   
</p>

# Deep Learning



## Baseline Model

### Handling Overfitting

* Reducing network's size

<p align="center">    
   <img width="535" alt="Ekran Resmi 2021-08-10 03 29 54" src="https://user-images.githubusercontent.com/52889449/128790723-1b3cab55-731e-4d01-a77b-e9a2fa99faf7.png">
</p>


* Adding regularization

<p align="center">    
   <img width="535" alt="Ekran Resmi 2021-08-10 03 30 43" src="https://user-images.githubusercontent.com/52889449/128790772-6a6ca4d3-0d62-42ee-9cc1-28f3a0ebccba.png">
</p>

* Adding dropout layers


<p align="center">    
   <img width="535" alt="Ekran Resmi 2021-08-10 03 31 38" src="https://user-images.githubusercontent.com/52889449/128790816-88b6a4cd-458a-4673-af50-10f1e2a19e10.png"> 
</p>

## Embedding Layer

<p align="center">    
   <img width="535" alt="Ekran Resmi 2021-08-10 20 13 41" src="https://user-images.githubusercontent.com/52889449/128904882-a5113a14-d2c0-40e5-aafe-66a39e0edbc6.png">   
</p>

<p align="center">    
   <img width="535" alt="Ekran Resmi 2021-08-10 20 13 56" src="https://user-images.githubusercontent.com/52889449/128904839-171e10ec-b2cf-4804-ac14-4726b6737797.png">
</p>

## Pre-trained Word Embedding: GloVe

<p align="center">      
   <img width="535" alt="Ekran Resmi 2021-08-10 20 14 20" src="https://user-images.githubusercontent.com/52889449/128904805-f6f5e304-62bc-4fcb-862b-73981592a601.png">
</p>

<p align="center">    
   <img width="535" alt="Ekran Resmi 2021-08-10 20 14 35" src="https://user-images.githubusercontent.com/52889449/128904744-a1760da6-96bd-4f89-884e-e08fecdf1454.png">
</p>


# Model Performance

<p align="center">    
   <img width="535" alt="Ekran Resmi 2021-08-10 03 31 38" src="https://user-images.githubusercontent.com/52889449/128904072-c640a7d4-e758-4173-9008-e1b464641eeb.png"> 
</p>






