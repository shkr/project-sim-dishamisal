# The Problem: Classify Wikipedia Disease Articles

We provide a sample of articles taken from Wikipedia. There are lots of different kinds of articles, and one flavor is those that describe a disease. The data are html dumps of wikipedia articles. We give you a labelled set of disease articles (positives), and non-diseases articles (negatives).

*   **Part 1:** Use this data set to create a classifier that can accurately predict whether an article describes a disease.
*   **Part 2:** Extract the name of the disease. Optionally, include as much information as you can about the disease. E.g. information to consider are symptoms, causes, prognosis, prevention, treatment, relevant drugs, human/non-human susceptibility.

**The data:** The directory contains wikipedia article html dumps. There are direct wgets of the articles, e.g. [malaria](https://en.wikipedia.org/wiki/Malaria), [autism](https://en.wikipedia.org/wiki/Autism), [Parkinson's disease](https://en.wikipedia.org/wiki/Parkinson%27s_disease). They are organized into two directories: <tt>positive/</tt> and <tt>negative/</tt>. The positive dataset is 3,693 articles about diseases, and the negative dataset is 10,000 articles.

Here is the data set: [wikipedia_diseases.zip](http://challenge.20n.com/machine-learning/training.tar.gz)

**Edge cases:**

1.  Your classifier might misclassify drug articles as disease articles, e.g. [Penicillin](https://en.wikipedia.org/wiki/Penicillin), [Paracetamol](https://en.wikipedia.org/wiki/Paracetamol), [L-DOPA](https://en.wikipedia.org/wiki/L-DOPA), [Erythromycin](https://en.wikipedia.org/wiki/Erythromycin). Check if that is the case, and optionally try to fix that mis-classification.
2.  Exclude broad articles that talk about generic classes of diseases, e.g. [genetic disorders](https://en.wikipedia.org/wiki/Genetic_disorder), [infection](https://en.wikipedia.org/wiki/Infection), [bacteria](https://en.wikipedia.org/wiki/Bacteria), [virus](https://en.wikipedia.org/wiki/Virus), [mutation](https://en.wikipedia.org/wiki/Mutation). Fun: when you exclude these, what does your classifier do for [cancer](https://en.wikipedia.org/wiki/Cancer)?


## Solution

**Components:**
- *HTML Parsing*: Parse through the wikipedia article for sentences.
- *Baseline model*: Logistic Regression Classifier
- *DNN model*: Sequential model from Keras is used for both Part-A and Part-B (separate models for the same)


## Instructions to run

> Runner module is created and DNN model is pre-trained with a small subset of training data (in absense of adequate compute).

```sh
$ python runner.py
$ (enter text to be classified)
$ (if text is classified as disease, it would also try to identify the disease)
```
## Conclusions

Model performs satisfactorily well, but with caveats. Future scope includes:
- Experimentation with Word embeddings and Glove bag-of-words
- Convolutional Neural Networks and Deep-NLP

