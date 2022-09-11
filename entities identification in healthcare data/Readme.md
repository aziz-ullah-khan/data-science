# Identifying Entities in Healthcare Data
---
To derive Name Entity Recognition (NER) on Medical data set so that we can classify the given word as of type Disease, Treatment or Others 

The dataset provided is in the form of one word per line. Let's understand the format of data below:

- Suppose there are x words in a sentence, then there will be x continuous lines with one word in each line.
- Further, the two sentences are separated by empty lines. The labels for the data follow the same format.

![image](https://user-images.githubusercontent.com/25382680/189512719-c7fc5d18-68f8-4209-bc77-6896e5c84a1b.png)


![image](https://user-images.githubusercontent.com/25382680/189512726-e58d264a-7fc4-4ebb-9385-9e4eb46fad98.png)

**D: Disease, T: Treatment**

The tasks accomplished in the notebook are:
1. Data preprocessing
2. Concept identification
3. Defining the features for CRF
4. Getting the features words and sentences
5. Defining input and target variables
6. Building the model
7. Evaluating the model
8. Identifying the diseases and predicted treatment using a custom NER

