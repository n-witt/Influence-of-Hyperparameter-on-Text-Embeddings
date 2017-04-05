# Understanding the Influence of Hyperparameters on Text Embeddings for Natural Language Processing Tasks

This is the accompanying material for the paper "Understanding the Influence of Hyperparameters on Text Embeddings for Natural Language Processing Tasks" by Nils Witt and Christin Seifert. The paper explores the influences of the various hyperpaprameters of a [doc2vec](https://radimrehurek.com/gensim/models/doc2vec.html)-based kNN-classifier on the accuracy of the model. For further details, please refer to the paper. 

## Repository structure
1. There are two notebooks that transform a dataset into a common format ([1](1.0_Amazon_corpus_to_pandas.ipynb), [2](1.1_20Newsgroups_to_pandas.ipynb))
2. [This](2_Hyperparameter_search.ipynb) notebook carries out grid search as well as Bayesian optimization.
3. The [last](3_Analysis.ipynb) notebook visualizeses the results for the previous step in several ways.

## Hardware requirements
This software is very demanding in terms of hardware specifications. While the actual demand depends on some parameters of the grid search (size of the training set and number parallel executed processees), it should be noted that, in general, a big machine (>128GB RAM, >12 CPU cores) is required. 

## Dependencies
The project is based on Python 3.5 and Jupyter notebooks. We recommend using the [Anaconda](https://www.continuum.io/downloads) distribution to install the environment. Furthermore, we are using the Python machine learning stack inclusing NumPy, Scikit Learn, Matplotlib, Pandas and Gensim. 

## Adapting new corpora
Incorporating new corpora into this framework is faily easy: to satisfy the input format a Pandas dataframe must be pickled to disk. The dataframe must contain the column `text` which comprises the text of one document per row as well as a column `category` which defines the membership of this document to a category.

| text                     | category         |
| ------------------------ |------------------|
| Lorem Ipsum...           | greek philosophy |
| Live long and prosper... | sci-fi           |
