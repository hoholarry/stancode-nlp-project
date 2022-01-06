# stancode-nlp-project

Financial institutions must conduct Know Your Customers (KYC) in order to comply with Anti Money Laundering (AML) regulations.
In this process, KYC analysts input the targets name along with keywords that are often associated with money laundering ("drugs", "bribery") into search engines, returning news with the negative keywords. However, not all results are related to money laundering. For example, you might find a lot of results with the keyword "drug lord" when you search "Bryan Cranston", star of "Breaking Bad" where he plays the drug lord in the series.
Our goal is to build a model that can identify whether a piece of news is actually related to money laundering and not a "false hit".

At the beginning of this project, we struggled to find appropriate and preprocessed datasets because of the topic, since AML is a sentiment topic, we can’t find much open data to use, so we finally decided to make a good use of the resources available, Larry’s company and our own coding skill.
The language of news we want to classify is English, so we used an Google API to do the translation job for us.
The dataset used in our project includes 606 news articles which are labeled and collected by a start-up company named KryptoGO and get other 5,756 news articles from Ettoday website through a python web crawler made by ourselves and of course, labeled by the existing model from KryptoGO.
Dataset splits:
Train data: {0: 4,000, 1: 2,000}
Validation data: 10% of training data
Test data: {0: 181, 1: 181}

Model
Bert (Bidirectional Encoder Representations from Transformers)
A transformer-based pretrained model for NLP
Bert is a transformer encoder 

Transformer 
An encoder-decoder architecture that uses the attention mechanism
encoder: sequence → vector
decoder: vector → sequence

DistilBERT
40% less parameters (Bert: 340M)
60% faster
95% of BERT’s performances
Loss function Categorical Cross Entropy
Optimizer Adam

Results
sequence length: 500
Hyperparameters
Epoch: 2 / Batch: 4
Learning rate: 3e-5
Acc 
96.72 % on train
96 % on validation
96.68 % on test

Discussion and Conclusion
Model capable of predicting news is actually related to money laundering have been built and tested to achieve high accuracy (96.6%)
The length of the article need to be close to our training dataset to obtain highly accurate result.


Future Work
Using NER, implement a function to identify the main subject of the adverse news, and find the age, gender, nationality, occupation, and organization associated with the subject.
use a high length variance dataset to increase our performance on short articles.

References
ktrain: A Low-Code Library for Augmented Machine Learning Arun S. Maiya (arXiv:2004.10703)
DistilBERT, a distilled version of BERT: smaller, faster, cheaper and lighter Victor Sanh, Lysandre Debut, Julien Chaumond, Thomas Wolf (arXiv:1910.01108)
