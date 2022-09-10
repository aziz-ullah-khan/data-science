# QUORA QUESTION PAIRS
---

## Introduction

Sentences or questions similarities is utmost important in many applications and machine learning approaches have applied to solve this problem by many researchers. Questions similarities is very hot topic these days and many researchers are approaching the problem to solve with a reasonable accuracy. 
In this project, we deep dived with different algorithms/experiments to find the optimal solution to the problem along with the comparison of multiple models.
The dataset used for this project is obtained from the Kaggle competition with the name “Quora Question Pairs” and is available openly on the website Kaggle.com. In our approach we implemented many classical models like logistic regressions, decision tree. Subsequently we configured BERT transformers with different model type. 

## Exploratory Data Analysis

### Data Definition

The dataset used in this project in acquired from the Kaggle platform which mainly consist of three files: Train, Test, Submission. For our experiments we used train dataset which we split for training and testing purpose to generate results. Brief insight of the dataset of the training file shown in fig. 1 below. 

![image](https://user-images.githubusercontent.com/25382680/189496203-93b03cd4-6ce3-42b3-8383-e4471711bb91.png)
<center>Figure 1:  Training Dataset insights</center>

### Data Distribution and Statistics 

The goal of this project is to find the similarity of the two questions which are available in the dataset to classify whether the two questions are similar or not. First, we performed the exploratory data analysis of the data to get required insights. 
In our dataset the is duplicate column in the labels which is the required target. Here is duplicate is the categorical values with 0 as the questions are not similar and 1 indicate the questions are similar. In fig. 2 shows the distribution of the values.

![image](https://user-images.githubusercontent.com/25382680/189496427-014fefb5-547f-4037-ab9c-b80a3e5513a7.png)
Figure 2: Labels

The distribution of labels columns is clearly shown in fig. 3 below, here 36.9% questions are similar while 63.1% are not similar. 
![image](https://user-images.githubusercontent.com/25382680/189496439-e977db94-2d1a-4ba7-ba50-ac15c9b39dfc.png)
Figure 3: Labels column categorical distributions

After analyzing the labels, analyzed the question1 column and question2 columns and the statistics are shown in Fig. 4 and Fig. 5 respectively. 
![image](https://user-images.githubusercontent.com/25382680/189496461-fc415f7f-4719-4bae-b7d6-746e0484c13b.png)
Figure 4: Question1 column statistics

![image](https://user-images.githubusercontent.com/25382680/189496500-bcdb8f56-bc99-4f54-b473-2e46fbc11cf3.png)
Figure 5: Question2 column Statistics

As shows in the figures above the most repeated sentence in question one is “How do I improve my English speaking? “, while in question2 the most repeated question is “How can you look at someone's private…“
The word cloud of the question1 is shown in Fig. 6
![image](https://user-images.githubusercontent.com/25382680/189496514-45750511-2639-455a-b0be-84da967189e6.png)
Figure 6: Word Cloud of Question1 Column


Here it is clearly shown that the most repeated words are how, what, why respectively. 
These are the original word cloud without any modifications. 
![image](https://user-images.githubusercontent.com/25382680/189496535-59cb7fa8-906f-4cab-b5c5-5f4fa37332c4.png)
Figure 7: Word Frequency

The word frequency is shown in Fig. 7
In the figure it is clearly shown that the word what is appeared almost 150k while I how and why also appeared in majority. 
Word cloud of question2 column is shown in Fig. 8, Here same like question1 the most repeated words are what, how, I, why. 

![image](https://user-images.githubusercontent.com/25382680/189496552-4d626e81-8252-401a-b139-02443f9d653b.png) ![image](https://user-images.githubusercontent.com/25382680/189496558-c679b500-0972-45e8-a846-86923045b1c2.png)
Figure 8: Question2 Column Word Cloud & Word Frequency

## Data Common Preprocessing
For preprocessing of the data for the purpose of cleaning the data, first process the data converted to lower case and then punctuations are removed. The removed punctions are:
“!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~”.

Subsequently, stop words have been removed to avoid irrelevant redundancy in the data. 
Table 1: Spacy Stop words
For the purpose of Natural Language Processing in the preprocessing steps, spacy is used and the stop words shown in the Table 1 shows some spacy stop words. A total of three hundred twenty-six stop words are sued for the removal purpose.  
Later on, lemmatization is performed to convert the words to the root word to remove the repetitions of words in the features. 
For the purpose of generating the feature vectors different techniques have been applied like word2vec, TDIDF vectorizer for better performance.  

## Data Modelling 

### Classical Machine Learning Algorithms
For the purpose of modeling, different models have been implements which are Logistic Regressions, k-Nearest Neighbors, Decision Tree and Random Forest respectively. 
As we have our data in the text format and machine learning model need numerical data, a transformation is required on the textual data to convert to numerical. For the purpose of conversion, we converted the words with the help of TFIDF and word2Vec. Both the questions are transformed to vectors with each value as a feature. After the transformation, the data has been split for train and testing purpose. All the training data is passed from different models and with the different evaluation parameters, all the models evaluated and the results of the whole models are shown in Table 2 below. 

Table 2 Classical Models evaluation results
![image](https://user-images.githubusercontent.com/25382680/189496798-cdfc761b-ecc1-4554-8b13-f818c4edf343.png)
From the above evaluation results, it’s clear that random forest performs well with 69.28% accuracy which is good results with the comparisons to others. Also, the f1-score of random forest shows its dominancy over the others. 

### Bidirectional Encoder Representations from Transformers (BERT)
BERT is the bidirectional encoder representations from transformers and is very powerful in the field of natural language processing these days. BERT models are known as state-of-the-art models due to it’s pretrained models. BERT models used attention mechanisms which is of transformers which learn contextual relations in the textual data. For implementing BERT, simpletransformers library is used due to its simplicity and easy implementations approach. In this project BERT, ROBERTA, DistilBERT, ALBERT are implemented after the preprocessing of the data. Data is feed to these models for getting the pattern in the data with the BERT mechanism. The models mentioned above are fine tuned with the processed data. These models are then evaluation on accuracy, precision, recall and F1 Score accordingly. After thoroughly evaluation of the different models, fine tuned the models for achieving high results. 

Overview of the model’s evaluation is shown in Table 3 below. 

Table 3: BERT Models Evaluation Results
![image](https://user-images.githubusercontent.com/25382680/189496838-50269b39-ee83-4f57-aedf-3406e5c0e1ec.png)

Table 3 shows the evaluation results which in comparison with the classical models performed very well and the results are quite promising. The above shows the results of the optimized solution of the BERT models, hyper-parameters are tuned to get the satisfactory results. To compare the above model types Roberta performed well and the accuracy is 80.06%, the other metrics precision, recall and F1 score are also showing the dominancy over the rest of the models. Model type BERT is also in competition with the Roberta and the accuracy is almost 80%. So, the overall performances of these models are over the line. There is always room to improve any machine learning models, so these models can be further optimized by tunning the hyper-parameters further. 

## Conclusion 
In our approach for handling the task of questions similarity we implemented different models both the classical and deep neural networks. Multiple experiments have been performed and with the evaluation results the outcome is satisfactory. With post analyzing the metrics it has been concluded that the BERT models outperform than the classical models. The main challenges that are faced is the computational time and training time of BERT models and also high machine specifications are required for achieving results with no latency. With the usage of GPU’s, the model’s performance in term of computations increased. Overall, the results achieved with this project are satisfactory and further enhancement is possible with fine tunning the hyper-parameters. 
