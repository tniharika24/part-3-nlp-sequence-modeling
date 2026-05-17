# Part 3: NLP and Sequence Modeling Mini Project

## Project Overview
In this project, I worked on a text classification problem using a customer support
dataset. The goal was to classify customer messages into one of three sentiment categories:

- *positive*
- *neutral*
- *negative*

The main purpose of this assignment is to understand how text data is converted
into numerical form and why sequence modeling is important in NLP.

---

## Dataset Summary
- *File name:* customer_support_text_classification.csv
- *Input text column:* customer_message
- *Target column:* sentiment_label

### Target Classes
- positive
- neutral
- negative

### Other Useful Columns
- channel
- word_count
- urgent_flag

---

## Tasks Covered
This notebook includes the following tasks:

1. Dataset understanding
2. Text preprocessing
3. Text vectorization
4. Baseline model creation
5. Sequence model creation using LSTM
6. Reflection on attention and transformers

---

## Dataset Understanding
The dataset was explored by checking:
- number of records
- target classes
- sample customer messages
- average text length
- class distribution

This helps in understanding the structure of the dataset before building the models.

---

## Text Preprocessing
The following preprocessing steps were applied:
- lowercasing text
- removing special characters and digits
- removing extra spaces
- tokenization
- removing stopwords for the baseline model
- padding/truncating sequences for the LSTM model

---

## Text Vectorization
Text must be converted into numerical vectors because machine learning models
cannot directly understand raw text.

In this project, I used:
- *TF-IDF* for the baseline model
- *Tokenizer + padded sequences* for the sequence model

---

## Baseline Model
The baseline model used was:

- *Logistic Regression with TF-IDF*

This is a simple and strong traditional NLP baseline that performs well for many
text classification tasks.

---

## Sequence Model
A simple sequence-based deep learning model was built using:

- Embedding layer
- LSTM layer
- Dense output layer

This model helps preserve word order and context, which is something traditional
vectorization methods do not fully capture.

---

## Model Evaluation
The models were evaluated using:
- accuracy
- classification report
- confusion matrix
- sample predictions

The evaluation files are stored inside the results/ folder.

---

## Reflection

### Why do RNNs struggle with long-term dependencies?
RNNs process one word at a time, and over long sequences they may forget earlier
information. This makes it hard to capture long-range dependencies.

### How do LSTMs help with memory?
LSTMs use gates to decide what information to keep, forget, or update. This helps
them remember useful context for longer sequences.

### What problem does attention solve?
Attention allows the model to focus on the most relevant words in the input while
making predictions, instead of depending only on one compressed hidden state.

### Why are transformers important in modern NLP and Generative AI?
Transformers use self-attention and process tokens in parallel, which makes them
more powerful and efficient than older sequence models. They are the foundation
of modern NLP and generative AI systems.

---

## Repository Structure
```bash
part-3-nlp-sequence-modeling/
│
├── README.md
├── notebook.ipynb
├── requirements.txt
├── customer_support_text_classification.csv
└── results/
    ├── model_evaluation.csv
    └── sample_predictions.txt
