# Commonsense Event Representation

This repository contains code for the EMNLP 2019 paper: *Event Representation Learning Enhanced with External Commonsense Knowledge*.

## Requirements

- Java 1.7, Scala 2.9.0 (for preprocessing NYT corpus)

- Python3

## Data

The original hard similarity dataset, the hard similarity dataset annotated by us, and the transitive sentence similarity dataset are released together with the code. The file format is processed for convenience.

NYT, ATOMIC and other datasets need to be downloaded separately.

The pretrained word embedding can be downloaded [here](https://drive.google.com/open?id=1Jw-X-mVci5VbKg0Gl0ZRRwhgfgyiZ7Vc). We add embeddings for word "PersonX" and "PersonY" to the original Glove word embedding.

## Preprocessing

See [this](https://github.com/MagiaSN/commonsense_event_repr_emnlp19/blob/master/preproc/README.md).

## Train

First, pretrain the event representation model on the NYT corpus using the method described in the AAAI 2018 paper *Event Representations with Tensor-based Compositions* (run either of the scripts below).

- `train_event_prediction_on_nyt.py` Pretrain the event representation model on the NYT corpus with "event prediction" objective.

- `train_word_prediction_on_nyt.py` Pretrain the event representation model on the NYT corpus with "word prediction" objective.

After pretraining on the NYT corpus, train the event representation model on the ATOMIC dataset, using the following script:

- `joint_train_on_atomic.py` Train the event representation model on the ATOMIC dataset, with additional intent prediction and sentiment classification objective.

## Test

For the hard similarity task, run this script:

- `eval_hard_similarity.py`

For the transitive sentence similarity task, run this script:

- `eval_transitive_sentence_similarity.py`

## Models

The best model for each task can be downloaded from: <TODO>
