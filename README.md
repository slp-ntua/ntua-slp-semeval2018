# Overview

This repository contains the source code of the models submitted 
by NTUA-SLP team in SemEval 2018 tasks 1, 2 and 3.
- Task 1: Affect in Tweets https://arxiv.org/abs/1804.06658
- Task 2: Multilingual Emoji Prediction https://arxiv.org/abs/1804.06657
- Task 3: Irony Detection in English Tweets https://arxiv.org/abs/1804.06659


## Prerequisites
Please follow the steps below in order to be able to train our models:

#### 1 - Install Requirements
```
pip install -r ./requirements.txt
```

#### 2 - Download our pre-trained word embeddings
The models were trained on top of word2vec embeddings pre-trained 
on a big collection of Twitter messages. We collected a big dataset of 
550M English Twitter messages posted from 12/2014 to 06/2017. 
For training the word embeddings we used 
[Gensim's implementation](https://radimrehurek.com/gensim/) 
of word2vec.
For preprocessing the tweets we used [ekphrasis](https://github.com/cbaziotis/ekphrasis).

You can download one of the following word embeddings:
- [twitter.50d.txt](https://mega.nz/#!zsQXmZYI!M_y65hkHdY88iC3I8Yeo7N9IRBI4D9mrpz016fqiXwQ): 50 dimensional embeddings
- [twitter.100d.txt](https://mega.nz/#!OsYTjIrQ!gLp6YLa0A3ncXjaUffbgL2RtUI74bvSkUKpflAS0OyQ): 100 dimensional embeddings
- [twitter.200d.txt](https://mega.nz/#!W5BXBISB!Vu19nme_shT3RjVL4Pplu8PuyaRH5M5WaNwTYK4Rxes): 200 dimensional embeddings
- [twitter.300d.txt](https://mega.nz/#!u4hFAJpK!UeZ5ERYod-SwrekW-qsPSsl-GYwLFQkh06lPTR7K93I): 300 dimensional embeddings

Place the file(s) in `/embeddings` folder, for the program to find it.

# Documentation 

### Project Structure
- `datasets`: contains the datasets for the pretrainig (SemEval 2017 - Task4A) 
- `dataloaders` - contains scripts for loading the datasets
              and for tasks 1, 2 and 3 
- `embeddings`: in this folder you should put the word embedding files.
- `logger`: contains the source code for the `Trainer` class 
            and the accompanying helper functions for experiment management,
            including experiment logging, checkpoint and early-stoping mechanism
            and visualization of the training process.
- `model`: experiment runner scripts (dataset loading, training pipeline etc).
    - `pretraining`: the scripts for training the TL models
    - `task1`: the scripts for running the models for Task 1
    - `task2`: the scripts for running the models for Task 2
    - `task3`: the scripts for running the models for Task 3
- `modules`: the source code of the PyTorch deep-learning models 
             and the baseline models.
    - `nn`: the source code of the PyTorch modules
    - `sklearn`: scikit-learn Transformers for implementing the baseline 
                bag-of-word and neural bag-of-words models
- `out`: this directory contains the generated model predictions and 
            their corresponding attention files
- `predict`: scripts for generating predictions from saved models.
- `trained`: this is where all the model checkpoints are saved.
- `utils`: contains helper functions

Full documentation of the source code will be posted soon.
