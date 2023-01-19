# POS-Tagging

<p align="center">
<img src="pos-tagging-img.jpeg" alt="Alt text" height="400">
</p>

POS-tagging (**part-of-speech tagging**) is a process of assigning each word in a sentence a label
that indicates its part of speech, such as noun, verb, adjective, adverb, etc. 
It is a way of analyzing sentence terms and **assigning** them **a tag**, 
thus providing further information about the sentence structure and meaning.

Example:
<p align="center">
<img src="POS-tag-example.png" alt="Alt text" height="150">
</p>

### Collaborators
* Zorila Iulian
* Marini Daniele
* Davide Brescia

## Goal 
<a href="POS-tagging.ipynb">POS-tagging.ipynb</a>
<a target="_blank" href="https://colab.research.google.com/github/iulianzorila/POS-Tagging/blob/6b554a18df0f9f7aa88072c5074e87388d10e762/POS-tagging.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

The objective of this project is to automatically perform POS-tagging by the means of deep neural networks, using pretrained word-embeddings.

## Dataset
The dataset can be downloaded from <a href="https://raw.githubusercontent.com/nltk/nltk_data/gh-pages/packages/corpora/dependency_treebank.zip">here</a>, 
consisting of 200 files. We splitted them as such:
*  1-100 train set
*  101-150 validation set
*  151-199 test set

## Models
Each tested architecture includes the same Embedding and dense layer (used for classification of the 45 POS tags).
In particular we trained the following type of models:
*  Baseline with Bidirectional **LSTM** layer.
*  Variation with Bidirectional **GRU** layer.
*  Variation with **double** Bidirectional LSTM layer.
*  Variation with Bidirectional LSTM and **dense** layer.

To understand the best configuration of units per each layer, we performed a GridSearch over the number of units and trained a total of 60 models.
The process took around 1 hour using the Colab GPU.

## Results

<p align="center">
<img src="F1-score.png" alt="Alt text">
</p>
<p align="center">In the picture the numbers above each curve point specifies the number of trained epochs</p>


To evaluate each model we adopted the Macro F1 score and afterwords performed an in depth analysis to check the most common mistakes and overall performance.
