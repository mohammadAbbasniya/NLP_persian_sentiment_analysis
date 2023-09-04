# Sentiment Analysis of Persian Comments
Implementation of NLP models for classification of the Persian comments' sentiment in Python.

### Requirements
see [requirements.txt](https://github.com/mohammadAbbasniya/NLP_persian_sentiment_analysis/blob/main/requirements.txt) and use `pip install -r requirements.txt` for installation.
1. `numpy` for some calculations
2. `pandas` for data read/write
3. `scikit-learn` for classfiers
4. `gensim` for Word2Vec model
<br><br>

## About Sentiment Analysis
Sentiment analysis (also known as opinion mining or emotion AI) is the use of natural language processing, text analysis, computational linguistics, and biometrics to systematically identify, extract, quantify, and study affective states and subjective information. Sentiment analysis is widely applied to voice of the customer materials such as reviews and survey responses, online and social media, and healthcare materials for applications that range from marketing to customer service to clinical medicine [[Wiki](https://en.wikipedia.org/wiki/Sentiment_analysis)]. Following figure shows the workflow of sentiment analysis [[monkeylearn](https://monkeylearn.com/sentiment-analysis)].
<p align='center'>
  <img alt="nlp-workflow" width="600" src="https://github.com/mohammadAbbasniya/NLP_persian_sentiment_analysis/blob/main/README.imgs/nlp-workflow.png">
</p> 

## Project structure 
- ### 📂 directory [sentiment_data]
  This directory contains data used in the project. `train.csv` has labeled comments for training (we split it into train-validation to find the best model). `test.csv` has unlabeled comments that we should predict the label of each row using our propused model and save the result in `test-labeled.csv`. 

- ### 📂 directory [nlp_files]
  This directory contains some files for being used in NLP models (e.g. stop-words).
  
- ### 📄 [phase1.ipynb]
  Contains steps for finding the best method for being applied to data. In this file, we only use `train.csv` and split it into train-validation sets. Here is the final result of all 18 models employed in this phase:

<div align="center">

  | Classifiers | TF-IDF |  Word2Vec |
  | --- | --- | --- |
  | KNN(n=4) | 0.4619	| 0.6131 |
  | KNN(n=8) | 0.6940	| 0.6298 |
  | KNN(n=16) | 0.7524 | 0.6238 |
  | SVM(linear) | 0.7905 | 0.4774 |
  | SVM(poly) | 0.6417 | 0.6452 |
  | SVM(rbf) | 0.7905 | 0.6810 | 
  | XGB(n=50) | 0.7214 | 0.6571 | 
  | XGB(n=100) | 0.7298	| 0.6786 |
  | XGB(n=150) | 0.7381 | 0.6714 |

</div>

- ### 📄 [phase2.ipynb]
  This file is the implementation of the proposed method found in phase1. The result of applying the proposed model on `test.csv` can be seen in [`test-labeled.csv`](https://github.com/mohammadAbbasniya/NLP_persian_sentiment_analysis/blob/main/sentiment_data/test-labeled.csv).



