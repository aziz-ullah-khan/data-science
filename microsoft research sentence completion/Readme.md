# The Microsoft Research Sentence Completion Challenge
----

## Abstract
Sentence completion is a challenging task and is extremely time consuming, which is the challenge of today. Many researchers worked on the autocompletion of the sentence but the complexity arise with the high volume of textual data processing. N-grams along with word2vec and with the combination of wordnet play a key role in the solving the problem by allowing the words to vectorize with the help of word2vec and the distances between the words can be found for similarity. Wordnet which is a lexical database and having semantic relationship between words in over twenty hundred languages and is the part of Natural Language Toolkit corpus. In this study n-grams (uni-gram, bi-gram, tri-gram) are implemented separately and also along with wordnet with word2vec. The dataset used in this study is the Microsoft research sentence completion challenge. The models are first trained with the training textual data and performance is evaluated on the multiple-choice question with five options. The evaluation metrics shown for this study are accuracy, precession, recall, f-1 score respectively. In this novel approach satisfactory results are generated.

**Keywords:** Natural Language processing, n-grams, NLTK, Wordnet, Word2Vec.

## Introduction
Over the fast few years, sentence completion is a very dominant research topic and the reason is due to the use of sentence completion in the communication system for saving lots of time. Sentence completion is using in all communication ranging form textual message to email and as well as the report writing as well. Sentences are basically the foundation and building blocks of all the language over the world and is the core component of the Natural Language processing (NLP) [1]. In sentence completion prediction of next word play a key role and the prediction of the next word is the fundamental task of Natural language processing [2]. Words prediction for sentence completion is a large domain and is not limited to collection of sequences of words occurrence but the relations of words is also utmost important [3]. There are many approaches to predict the words and in this study n-gram models are first implemented. N-grams models of uni-gram which is basically the collection of all the words and assign the probability to each word with the number of occurrences. Bi-gram is basically the collection two words sequence and can be stated that the occurrence word depends on the previous one words. Tri-gram is the collection of three words and is like the coming word depend on the previous two words. 

As the machines are not understanding by the textual data and the words should be converted to the format the machine can understand and can process in no time. With the evolvement of machine learning it is highly recommended and is the need to convert text to numbers. Many researchers proposed methodology for doing such. In the recent era for the purpose of natural language processing words conversion to vectors are introduced.  Words2Vec is the model used to convert words to vector and with the help of cosine similarity similar words can be find out. The author Jatnika [4] explained the whole concept of the word2vec modeling. 
Synonyms and antonyms are the core of the sentence prediction for semantic analysis. In certain scenario it is desired to have similar word. Wordnet which is the part of NLTK corpus contain the desired data and can be used for such analysis.
The dataset for this research work is chosen is the Microsoft research sentence competition. The dataset was created and constructed form the Gutenberg project data [5]. Seed sentences which are the training sentences are selected from five of Sir Arthur Conan Doyle’s Sherlock Holmes novels.

## Literature Review
Zweig  and Burges [5] presented the Microsoft research sentence completion data which consist of one thousand and forty sentences, and each of these sentences have four imposter sentences, in which only a words is changed with the imposter word in the original sentence having similar statistical occurrences. The objective work was to determine the correct word out of five for each sentence. The language model which was used in the research was to determine 30 alternate words for the words having low frequency and selected 4 imposter words respectively. 
Jatnika [4] described the vector similarity of the words for prediction of word and explained word2vec for semantic similarities in the English language. The model was tested on certain pair of words and found word2vec model better for similar word indication. 
Dumbali [2] explained the prediction of real time words using n-grams and stated a new word predictor which is grammatically accurate .
Gaikwad [6] explained the tunning of hyperparameters for n-grams models with the usage of machine learning algorithms. The author explained the sentiments analysis on the movie review dataset and presented the tuned hyper parameters.  
Ros [3] in his findings proposed an algorithms for that construct the relationship with any number of seed words.  Ros used word2vec and cosine similarity in his research
Yang [7] in 2021 proposed an approach of combining syntax information with the pre-trained language model. The author incorporated RNN based and Transformer based pre-trained models for better sentence semantic understanding. 

### Proposed Method
![image](https://user-images.githubusercontent.com/25382680/189684518-b92cb02a-b927-441a-adf8-7e6474e6e2ab.png)

Figure 1: Proposed Methodology

Fig. 1 is the block diagram of the proposed model and is a novel approach for handling the sentence completion challenge. First the dataset of MS research competition data is taken for this study. The dataset has over 500 text files, a text MCQS and a file containing answers. First the system read all the files and then process subsequently. 
##	Preprocessing
In the preprocessing phase the data is cleaned by applying different techniques. First of all, punctuation is removed from the text with the help of built-in string punctuations like comma, period, hyphen, quotes etc. All the punctions that were removed are:
!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~
Tokenization of texts is done subsequently which is the splitting of text data into tokens. In tokenization the text is splitting on whitespace, prefix, suffix and are one some exceptions as well. Natural Language Toolkit (NLTK) is used for the purpose of tokenization. After tokenization lemmatization is done.
For further reducing of dimensionality of the features, either stemming or lemmatization is implemented for the better results. Stemming is basically removing the end of the words to somehow replace the word with the root word. As stemming is not perfect as it’s like implementing a straight forward approach which is not a good fit for all the words. On the other side lemmatization work on the words tags and replace the words with the correct root word.  So, transformation of the words with lemmatization is accurate and we performed lemmatization instead of stemming.

###	N-gram models
N-gram model is basically the statistical or probabilistic language model used for predicting next word/item. It takes n number of sequences and on n-1 words predict the next word. In uni-gram all the textual data is converted into unique words with the number of count then the probability is calculated accordingly for prediction. In bi-gram two words are taken as a sequence and probabilities are counted subsequently. In the bi-gram model the next word is predicted with the help of the previous words. In the tri-gram model sequence of three words are considered and in the same manner probability is calculated for all the sequences. Here two words are considered for the next word prediction. 

### Word2vector
Word2vector is widely used technique in natural language processing and using neural network model to learn the association of words in the large corpus. Word2vec convert the words to vectors which play a huge role in the word’s similarity calculation. In this research we used word2vector model and finding the cosine similarity of the words to find the similar words. Wordnet is database of words is also incorporated in this study for finding synonyms of the words. 

###	Predictions
With the help of n-gram models’ sequence of words are collected. The collected words are then trained by word2vec to get the vectors for each word. In the prediction phase both n-gram and n-grams with word2vec along with wordnet is implemented which can be better explained with testing. The MCQs file is first pre-processed and answers are predicted in two approaches.
In the first approach with uni-gram random words are picked and compare the options of the MCQs and select the options having high probability. In the bi-gram options are compared for probability and high probability option is selected. Just like bi-gram, options are selected with tri-gram. 
In the second approach n-gram is combined with wordnet and word2vec. Select randomly from the sequences for all uni-gram, bi-gram and tri-gram, synonyms of the 5 options are selected with wordnet and then with the help of word2vec cosine similarity is calculated. Words with high cosine similarity are selected for the MCQ.

##	Results Analysis
Evaluation with accuracy, recall, precision and f1-score is the simplest approach for the analysis. Here all the results are explained with the metrics. 

###	Uni-gram results
Fig. 2 shows the result so of uni-gram model. In the figure it’s clear not predicting the answer properly. As the default option for the MCQs is e, so e is picked for all the MCQs and the accuracy is 20% due by default value.

![image](https://user-images.githubusercontent.com/25382680/189691055-77c13fe7-b693-4e3a-855f-f528e86d89f2.png)  ![image](https://user-images.githubusercontent.com/25382680/189691091-d3b7e8aa-a660-455a-bfd5-48b82e093029.png)

Figure 2: Uni-gram confusion Matrix - Classification report

![image](https://user-images.githubusercontent.com/25382680/189691456-2e090c9f-f994-4bdc-8eee-fa61da40df6b.png)  ![image](https://user-images.githubusercontent.com/25382680/189691477-a1b12613-a07b-4f72-aebe-e744b5d5c1c8.png)

Figure 3: Uni-gram + Wordnet and Word2Vec

The results shown in fig.3 above is generated on uni-gram model with wordnet and word2vec. The results improved from the uni-gram shown in Fig. 2. This model performed well in all the metrics and the drop of accuracy to 19% is due to this model is actually predicting the output rather than picking the default value as in the uni-gram alone.  From the confusion matrix it is shown that this model actually predicted the options. In the classification report it clearly indicated that the default value of the MCQs is e and the option have low recall and precision, which shows this model improved from the previous one. 

###	Bi-gram results
Fig. 3 is having sort of clear pattern that the model predicted the correct options. The accuracy is improved from the uni-gram model and all the metrics precision, recall along with f1-score are improved. Both the confusion matrix and the classification report convey the improved model performance. 

![image](https://user-images.githubusercontent.com/25382680/189691638-5c937481-4a19-4597-8605-58bb172b1ec5.png)  ![image](https://user-images.githubusercontent.com/25382680/189691663-79857d52-fedc-42e0-8406-532b622a6534.png)

Figure 4: Bi-gram- Confusion matrix - Classification report

Results for the bi-gram along with wordnet and word2vec are shown herein:

![image](https://user-images.githubusercontent.com/25382680/189691773-2fa2fa07-3ec9-4f7a-ae72-5387e5d4245f.png)  ![image](https://user-images.githubusercontent.com/25382680/189691798-6be5642b-1606-472d-9c09-4ef77156a58a.png)
Figure 5: Bi-gram + Wordnet and Word2Vec

The results shown in Fig. 5 are out of competition with the bi-gram in all the metrics and the reason is the random pick of only 5 words to check the similar words by using wordnet and word2vec. Still, it’s an improvement and achievement to generate such results with random 5 words. This model will perform well with tuning the hyper parameters discussed in the nest section. 

### Tri-gram results
In the fig. 4 below, a clear pattern in the corrected MCQs is shown which is the indicator that this model performs well from both uni-gram and bi-gram. This model has the accuracy of 29%. From the classification report it is shown that the rest of the metrics that are precision, recall and f1-score improved as a whole. 

![image](https://user-images.githubusercontent.com/25382680/189692017-ce7352ca-4df5-467a-9c3f-50e07137fc8d.png)   ![image](https://user-images.githubusercontent.com/25382680/189692049-07ddd359-448e-4fee-93c4-89e2db47e95c.png)

Figure 6: Tri-gram- Confusion matrix - Classification report

![image](https://user-images.githubusercontent.com/25382680/189692113-059c1cec-e1f0-48a5-afce-5aebfcc2ea9f.png)   ![image](https://user-images.githubusercontent.com/25382680/189692132-4c5a45f6-33bc-4c41-b921-11a310ae37b4.png)

Figure 7: Tri-gram + wordnet and Word2Vec

With the comparison of Fig. 7 which is the Tri-gram with wordnet and word2vec to the tri-gram model shows contrast in the performance. In this model there is only a pick of random 5 numbers, so still this model performed well. This model also performed will from the bi-gram model (wordnet and word2vec). The accuracy of this model can be improved with playing with the hyper parameters. 

The hyper parameters that can be tuned in this model are:
1.	N-gram, we can increase the sequence size. 
2.	Random selection of words, here we used 5 words.
3.	Get more synonyms from wordnet, here we picked 5 synonyms. 
4.	In the word2vec training, we can increase the min count, here used min of 1. 
5.	Vector size and windows in word2vec can be tunned as well. 

##	Conclusion and Future work
In this study word prediction for sentence completion was implemented. The methodology of the models was explained in depth. N-grams models were implemented along with wordnet and used word2vec for cosine similarity. The results generated are in competition with the research articles. The evaluation of the results was done with the accuracy, recall, precision and f1-score. The results generated in this study are satisfactory and in competition with the research articles and tri-gram model performed well. 
This model can be further tunned with the hyper parameters as there are many more combination to explore and the approach can be implemented with deep learning and recurrent neural networks to generate better results. Long short-term memory RNN can also be implemented to generate better results. 

## References
[1]	W. Au, B. Chong, A. A. Azzi, and D. Valsamou-Stanislawski, “{F}in{SBD}-2020: The 2nd Shared Task on Sentence Boundary Detection in Unstructured Text in the Financial Domain,” Proc. Second Work. Financ. Technol. Nat. Lang. Process., pp. 47–54, 2020, [Online]. Available: https://www.aclweb.org/anthology/2020.finnlp-1.8.

[2]	J. Dumbali and A. Nagaraja Rao, “Real time word prediction using N-grams model,” Int. J. Innov. Technol. Explor. Eng., vol. 8, no. 5, pp. 870–873, 2019.

[3]	S. C. Projects and K. Ros, “Digital Window @ Vassar Iteratively Linking Words Using Word2Vec and Cosine Similarity Iteratively Linking Words Using Word2Vec and Cosine Similarity,” 2020.

[4]	D. Jatnika, M. A. Bijaksana, and A. A. Suryani, “Word2vec model analysis for semantic similarities in English words,” Procedia Comput. Sci., vol. 157, pp. 160–167, 2019, doi: 10.1016/j.procs.2019.08.153.

[5]	G. Zweig and C. J. C. Burges, “The Microsoft Research Sentence Completion Challenge,” Challenge, pp. 1–7, 2011.

[6]	D. P. Gaikwad, “Hyper Parameters Tuning of N-gram evaluation based Machine Learning Model for Sentiment Analysis,” vol. 5, no. 04, pp. 428–436, 2018.

[7]	C. Yang, “Learning Better Sentence Representation with Syntax Information,” 2021, [Online]. Available: https://arxiv.org/abs/2101.03343.


  


  
