# Firefox Bugs Classifications
----
## Abstract
For the purpose of bugs reports classification, information gathered from the users as feedback or captured from reporting the bugs to the developers, here in this research a tool is developed which are classifying the bugs into their respective bug type with the subsequent classification of the bug reports into their respective components as well. 

Machine learning techniques such as BERT are proved quite performing in this study for the classification of bugs. It also showed that the bug reports with the help of machine learning can quickly fixed the bugs by identifying the bug in no time and user experience is also promised. Moreover, the proposed model can be further enhanced in different areas. 

**Keywords:** Natural Language Processing, Machine Learning, Bug Reports, Scikit-Learn, SpaCy, NLTK, BERT, Transformers

## Introduction
### Firefox bugs are the issues found in the Mozilla Firefox. Collected the data from the official website of the [Mozilla](https://bugzilla.mozilla.org/describecomponents.cgi)
#### Sample bug is displayed herein:

|Bug ID |	Type	| Summary	| Product	| Component |	Assignee |Status	| Resolution	| Updated
| --- |---| --- | --- | --- | --- | --- | --- | --- |
| 1536420	 | defect |	PDF uses lot of memory when decoding	| Firefox |	PDF Viewer	| nobody@mozilla.org	| UNCONFIRMED	| --- |	4/15/2022 21:22 |

---
Different types of components are shown herein:

  ![image](https://user-images.githubusercontent.com/25382680/211309632-be522684-4608-48d4-aff4-ee53d0f9741c.png)
  
  Figure 1: Componensts

## Proposed Method
![image](https://user-images.githubusercontent.com/25382680/211313493-64ebb374-ebfd-44bc-b44d-5ffe857528de.png)

Figure 2: Proposed Methodology
# ⬇ Firefox bug Classification Interface
**Using Streamlit**
![image](https://user-images.githubusercontent.com/25382680/189362485-354dffb9-8784-4287-a936-73f64e999c67.png)

## Results
![image](https://user-images.githubusercontent.com/25382680/211314729-072c5665-c780-4de5-a749-010cb6ebc6cb.png)

## Conclusion
It was concluded that SVM, Logistic Regression and the Random Forest are showing promising results for the bug classification system. BERT model is implemented on top of that and the results of BERT model is outperforming all the traditional models of machine learning for this research problem and the results generated full pledged. 

